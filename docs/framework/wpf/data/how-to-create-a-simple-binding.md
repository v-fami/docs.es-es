---
title: Procedimiento Crear un enlace sencillo
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: d617c8b97aa679398ed2d061a652f5164f1e499b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931576"
---
# <a name="how-to-create-a-simple-binding"></a>Procedimiento Crear un enlace sencillo
En este ejemplo se muestra cómo crear una sencilla <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, tiene un `Person` objeto con una propiedad de cadena denominada `PersonName`. El `Person` objeto está definido en el espacio de nombres denominado `SDKSample`.  
  
 La línea resaltada que contiene el `<src>` crea una instancia de elemento en el ejemplo siguiente la `Person` objeto con un `PersonName` el valor de propiedad `Joe`. Esto se hace en el `Resources` sección y asigna un `x:Key`.  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 La línea resaltada que contiene el `<TextBlock>` elemento, a continuación, enlaza la <xref:System.Windows.Controls.TextBlock> el control a la `PersonName` propiedad. Como resultado, el <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
