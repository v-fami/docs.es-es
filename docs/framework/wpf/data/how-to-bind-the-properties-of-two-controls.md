---
title: Procedimiento Enlazar las propiedades de dos controles
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 332e8e0dfa30ff7aff27c95652f07446baf6511a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754052"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Procedimiento Enlazar las propiedades de dos controles
En este ejemplo se muestra cómo enlazar la propiedad de un control con instancias a la de otra mediante el <xref:System.Windows.Data.Binding.ElementName%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo enlazar la <xref:System.Windows.Controls.Panel.Background%2A> propiedad de un <xref:System.Windows.Controls.Canvas> a la <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> propiedad de un <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Cuando se representa este ejemplo, tiene un aspecto similar a lo siguiente:  
  
![Captura de pantalla que muestra a un cuadro combinado casilla con el valor de color verde y un cuadrado de color verde.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> La propiedad de destino de enlace (en este ejemplo, el <xref:System.Windows.Controls.Panel.Background%2A> propiedad) debe ser una propiedad de dependencia. Para obtener más información, consulte [Información general sobre el enlace de datos](data-binding-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Especificación del origen de enlace](how-to-specify-the-binding-source.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
