---
title: Objetos DataSet con tipo
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 92ed3f8fd392238785fd2d205668f14fe477f2b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607131"
---
# <a name="typed-datasets"></a>Objetos DataSet con tipo
Además del acceso en tiempo de ejecución a valores mediante variables débilmente tipadas, el <xref:System.Data.DataSet> proporciona acceso a los datos mediante una metáfora fuertemente tipada. Tablas y columnas que forman parte de la **DataSet** se puede acceder mediante nombres descriptivos y variables fuertemente tipadas.  
  
 Un tipo **DataSet** es una clase que deriva de un **DataSet**. Como tal, hereda todos los eventos, métodos y propiedades de un **DataSet**. Además, un tipo **DataSet** proporciona propiedades, eventos y métodos fuertemente tipados. Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección. Además de mejorar la legibilidad del código, con tipo **DataSet** también permite que el código de Visual Studio .NET editor complete automáticamente las líneas mientras escribe.  
  
 Además, fuertemente tipado **DataSet** proporciona acceso a los valores del tipo correcto en tiempo de compilación. Con fuertemente tipado **DataSet**, errores de falta de coincidencia de tipos se interceptan cuando el código se compila en lugar de en tiempo de ejecución.  
  
## <a name="in-this-section"></a>En esta sección  
 [Generación de conjuntos de datos fuertemente tipados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 Describe cómo crear y usar fuertemente tipado **DataSet**.  
  
 [Anotación de conjuntos de datos con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 Describe cómo anotar el esquema de XML Schema definition language (XSD) utilizado para generar un fuertemente tipado **DataSet**, para proporcionar a **DataSet** nombres descriptivos de los elementos sin modificar el esquema subyacente.  
  
## <a name="see-also"></a>Vea también

- [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
