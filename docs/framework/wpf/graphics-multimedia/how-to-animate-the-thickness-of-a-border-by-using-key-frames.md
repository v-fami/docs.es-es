---
title: Procedimiento Animar el grosor de un borde mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 101fd077bf125faadbd9a0186c2282e4b20ee78f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699037"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Procedimiento Animar el grosor de un borde mediante fotogramas clave
En este ejemplo se muestra cómo animar la <xref:System.Windows.Controls.Control.BorderThickness%2A> propiedad de un <xref:System.Windows.Controls.Border>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Controls.Control.BorderThickness%2A> propiedad de un <xref:System.Windows.Controls.Border>. Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1. Durante el primer medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> clase para aumentar gradualmente el grosor del borde. El ejemplo se utiliza <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> para crear un aumento lineal suavizado entre los valores.  
  
2. Al final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> clase para aumentar de repente el grosor del borde. Los fotogramas clave discretos como los derivan de <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> crean saltos súbitos entre los valores, es decir, el movimiento de la animación es brusco.  
  
3. Durante los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> clase para reducir el grosor del borde. Los fotogramas clave spline como los derivan de <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> crean una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> propiedad. En este fotograma clave, la animación se inicia lentamente y se va acelerando de forma exponencial hacia el final del segmento temporal.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
- [Animar el valor del grosor de un borde](../controls/how-to-animate-a-borderthickness-value.md)
