---
title: Procedimiento para permitir que los usuarios copien varias celdas en el Portapapeles desde el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: b220603adcaeae6f3380a2e3c10ea524c9a61f24
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591923"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a>Procedimiento para permitir que los usuarios copien varias celdas en el Portapapeles desde el control DataGridView de formularios Windows Forms
Cuando se habilita la copia de celdas, los datos de su control <xref:System.Windows.Forms.DataGridView> son más fácilmente accesibles para otras aplicaciones mediante el <xref:System.Windows.Forms.Clipboard>. Los valores de las celdas seleccionadas se convierten en cadenas y se agregan al Portapapeles como valores de texto delimitados por tabulaciones para pegarlos en aplicaciones como el Bloc de notas y Excel, y como una tabla con formato HTML para pegarlos en aplicaciones como Word.  
  
 Puede configurar la copia de celdas para copiar solo valores de celda, para incluir el texto de encabezado de filas y columnas en los datos del Portapapeles, o para incluir el texto de encabezado solo cuando los usuarios seleccionan filas o columnas completas.  
  
 Según el modo de selección, los usuarios pueden seleccionar varios grupos de celdas desconectados. Cuando el usuario copia las celdas en el Portapapeles, no se copian las filas y columnas que no tienen celdas seleccionadas. Todas las demás filas o columnas se convierten en filas y columnas de la tabla de datos que se copia en el Portapapeles. Las celdas no seleccionadas en estas filas o columnas se copian como marcadores de posición en blanco en el Portapapeles.  
  
### <a name="to-enable-cell-copying"></a>Para habilitar la copia de celdas  
  
- Establecer la propiedad <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código completo siguiente se muestra cómo se copian las celdas en el Portapapeles. Este ejemplo incluye un botón que copia las celdas seleccionadas en el Portapapeles usando el método <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> y muestra el contenido del Portapapeles en un cuadro de texto.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Este código requiere:  
  
- Referencias a los ensamblados N:System y N:System.Windows.Forms.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [Selección y uso del Portapapeles con el control DataGridView de Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
