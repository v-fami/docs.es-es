---
title: No se puede aplicar el atributo '<attributename>' más de una vez
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: da4a766e2617308cb33b9673a88db9e7a954152a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935322"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>Atributo '\<attributename >' no se puede aplicar varias veces
El atributo solo puede aplicarse una vez. El `AttributeUsage` atributo determina si un atributo se puede aplicar más de una vez.  
  
 **Identificador de error:** BC30663  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que el atributo sólo se aplica una vez.  
  
2. Si usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar sus `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.AttributeUsageAttribute>
- [Creación de atributos personalizados](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
