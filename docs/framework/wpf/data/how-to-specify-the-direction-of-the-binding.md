---
title: Procedimiento Especificar la dirección del enlace
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 164fae937fc3935c7640a898c0c1908fd0a6b6b1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625325"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Procedimiento Especificar la dirección del enlace
En este ejemplo se muestra cómo especificar si los enlaces actualizan solo la propiedad de destino del enlace (destino), la propiedad de origen del enlace (origen), o las propiedades de destino y origen.  
  
## <a name="example"></a>Ejemplo  
 Usa el <xref:System.Windows.Data.Binding.Mode%2A> propiedad para especificar la dirección del enlace. La siguiente lista de enumeración muestra las opciones disponibles para las actualizaciones de enlace:  
  
- <xref:System.Windows.Data.BindingMode.TwoWay> actualiza la propiedad de destino o la propiedad cada vez que cambia la propiedad de destino o la propiedad de origen.  
  
- <xref:System.Windows.Data.BindingMode.OneWay> actualiza la propiedad de destino solo cuando cambia la propiedad de origen.  
  
- <xref:System.Windows.Data.BindingMode.OneTime> actualiza la propiedad de destino solo cuando se inicia la aplicación o cuando el <xref:System.Windows.FrameworkElement.DataContext%2A> sufre un cambio.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource> Actualiza la propiedad de origen cuando cambia la propiedad de destino.  
  
- <xref:System.Windows.Data.BindingMode.Default> hace que el valor predeterminado <xref:System.Windows.Data.Binding.Mode%2A> valor de propiedad de destino que se usará.  
  
 Para obtener más información, vea la enumeración <xref:System.Windows.Data.BindingMode>.  
  
 En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Para detectar los cambios del origen (aplicables a <xref:System.Windows.Data.BindingMode.OneWay> y <xref:System.Windows.Data.BindingMode.TwoWay> enlaces), el origen debe implementar un mecanismo de notificación de cambio de propiedad adecuado, como <xref:System.ComponentModel.INotifyPropertyChanged>. Consulte [implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md) para obtener un ejemplo de un <xref:System.ComponentModel.INotifyPropertyChanged> implementación.  
  
 Para <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces, puede controlar la temporización de las actualizaciones del origen estableciendo el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad. Vea <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> para obtener más información.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.Binding>
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
