---
title: Procedimiento para compartir datos enlazados entre formularios mediante el componente BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: 28eceaec72053d70885d54bc09179cff743ff71c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591440"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a>Procedimiento para compartir datos enlazados entre formularios mediante el componente BindingSource
Puede compartir datos fácilmente entre formularios con el componente <xref:System.Windows.Forms.BindingSource>. Por ejemplo, quizás quiera mostrar un formulario de solo lectura que resume los datos del origen de datos y otro formulario editable que contiene información detallada sobre el elemento seleccionado actualmente en el origen de datos. Este ejemplo muestra este escenario.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo compartir un <xref:System.Windows.Forms.BindingSource> y sus datos enlazados entre formularios. En este ejemplo, el <xref:System.Windows.Forms.BindingSource> compartido se pasa al constructor del formulario secundario. El formulario secundario permite al usuario editar los datos del elemento actualmente seleccionado en el formulario principal.  
  
> [!NOTE]
>  El evento <xref:System.Windows.Forms.BindingSource.BindingComplete> del componente <xref:System.Windows.Forms.BindingSource> se controla en el ejemplo para asegurarse de que los dos formularios permanecen sincronizadas. Para obtener más información acerca de por qué se hace esto, vea [Cómo: Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados](../multiple-controls-bound-to-data-source-synchronized.md).  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Windows.Forms, System.Drawing, System.Data y System.Xml.  
  
## <a name="see-also"></a>Vea también

- [Componente BindingSource](bindingsource-component.md)
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
- [Cómo: Controlar errores y excepciones que se producen con el enlace de datos](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
