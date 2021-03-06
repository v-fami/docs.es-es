---
title: Inspección del árbol de actividades
ms.date: 03/30/2017
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
ms.openlocfilehash: 014795b79b3536b387096e4de64266e26649da21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774156"
---
# <a name="activity-tree-inspection"></a>Inspección del árbol de actividades
Los autores de la aplicación de flujo de trabajo usan la inspección del árbol de actividad para inspeccionar los flujos de trabajo hospedados por la aplicación. Al usar <xref:System.Activities.WorkflowInspectionServices>, se pueden buscar actividades secundarias concretas en flujos de trabajo, se pueden enumerar las actividades individuales y sus propiedades, y los metadatos en tiempo de ejecución de las actividades pueden estar almacenados en memoria caché en un momento concreto. En este tema se proporciona información general de <xref:System.Activities.WorkflowInspectionServices> y cómo usarlo para inspeccionar un árbol de actividad.  
  
## <a name="using-workflowinspectionservices"></a>Usar WorkflowInspectionServices  
 El método <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> se usa para enumerar todas las actividades en el árbol de actividad especificado. <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> devuelve un enumerable que toca todas las actividades dentro del árbol como elementos secundarios, controladores delegados, valores predeterminados, variables y expresiones de argumento. En el ejemplo siguiente, se crea una definición de flujo de trabajo mediante <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.WriteLine> y expresiones. Una vez creada la definición de flujo de trabajo, se invoca y, a continuación, se llama al método `InspectActivity`.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 Se llama a <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> en la actividad raíz para enumerar las actividades y de nuevo de forma recursiva en cada actividad devuelta. En el siguiente ejemplo, el <xref:System.Activities.Activity.DisplayName%2A> de cada actividad y expresión en el árbol de actividad se escribe en la consola.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 Este código de ejemplo proporciona el siguiente resultado:  
  
 **Elemento de lista 1**  
**Elemento 2 de lista**   
**Elemento de lista 3**   
**Elemento de lista 4**   
**Elemento de lista 5**   
**Elementos agregados a la colección.**   
**Secuencia**   
 **Literal < lista\<cadena >>**  
 **While**  
 **AddToCollection\<String>**  
 **VariableValue<ICollection\<String>>**  
 **LambdaValue\<String>**  
 **LocationReferenceValue<List\<String>>**  
 **LambdaValue\<Boolean>**  
 **LocationReferenceValue<List\<String>>**  
 **ForEach\<String>**  
 **VariableValue<IEnumerable\<String>>**  
 **WriteLine**  
 **DelegateArgumentValue\<String>**  
 **Sequence**  
 **WriteLine**  
 **Literal\<cadena >** para recuperar una actividad específica en lugar de enumerar todas las actividades, <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> se utiliza. <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> y <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> realizan el almacenamiento en la memoria caché de los metadatos si no se ha llamado previamente a `WorkflowInspectionServices.CacheMetadata`. Si se ha llamado a <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>, <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> se basará en los metadatos existentes. Por consiguiente, si se han realizado cambios en el árbol desde la última llamada a <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>, los resultados de <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> podrían ser inesperados. Si se han realizado cambios en el flujo de trabajo después de llamar a <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>, los metadatos pueden almacenarse en caché volver a mediante una llamada a la <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> método. En la sección siguiente se trata el almacenamiento en la memoria caché de los metadatos.  
  
### <a name="caching-metadata"></a>Almacenar en memoria caché los metadatos  
 Almacenar en memoria caché los metadatos para una actividad compila y valida una descripción de los argumentos de la actividad, las variables, las actividades secundarias y los delegados de la actividad. De manera predeterminada, el tiempo de ejecución almacena los metadatos en la memoria caché cuando se prepara una actividad para que se ejecute. Si un autor de host de flujo de trabajo desea almacenar en memoria caché los metadatos para una actividad o árbol de actividad antes de esto como, por ejemplo, para calcular el costo inicial, se puede usar <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> para almacenar en memoria caché los metadatos en el momento deseado.
