---
title: Procedimiento Convertir una matriz de Bytes en una cadena en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 50acfdbfb9b093f719928f68d90a40f09da5ade5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665369"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a>Procedimiento Convertir una matriz de Bytes en una cadena en Visual Basic
En este tema se muestra cómo convertir los bytes de una matriz de bytes en una cadena.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Text.Encoding.GetString%2A> método de la <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> clase para convertir todos los bytes de una matriz de bytes en una cadena de codificación.  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 Puede elegir entre varias opciones de codificación para convertir una matriz de bytes en una cadena:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Obtiene una codificación para el juego de caracteres ASCII (de 7 bits).  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes big-endian.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Obtiene una codificación para la página de códigos ANSI actual del sistema.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes little-endian.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-32 utilizando el orden de bytes little-endian.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-7.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-8.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [Cómo: Convertir cadenas en una matriz de Bytes en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
