---
title: No se puede hacer referencia a '<name>' porque es miembro del campo de tipo de valor '<name>' de la clase '<classname>' que tiene 'System.MarshalByRefObject' como clase base
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: 78b0a3131b6e77ed257f200523ecebd4dfce3691
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649938"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a>No se puede hacer referencia a '\<nombre >' porque es un miembro del campo de tipo de valor '\<nombre >' de la clase\<classname >' que tiene 'System.MarshalByRefObject' como clase base
La `System.MarshalByRefObject` clase permite que las aplicaciones que admiten el acceso remoto a los objetos entre límites de dominio de aplicación. Tipos deben heredar de la `MarshalByRejectObject` clase cuando el tipo se usa en los límites del dominio de aplicación. No se debe copiar el estado del objeto porque los miembros del objeto no se puede usar fuera del dominio de aplicación en el que se crearon.  
  
 **Identificador de error:** BC30310  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Compruebe la referencia para asegurarse de que el miembro que se hace referencia es válido.  
  
2. Califique explícitamente el miembro con el `Me` palabra clave.  
  
## <a name="see-also"></a>Vea también

- <xref:System.MarshalByRefObject>
- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)
