---
title: Utilizar transformaciones para ajustar la escala de los colores
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 9c8f2392137d04f56096120cec64b60c42c47419
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791162"
---
# <a name="using-transformations-to-scale-colors"></a>Utilizar transformaciones para ajustar la escala de los colores
Una transformación de escala multiplica uno o varios de los cuatro componentes de color por un número. En la siguiente tabla figuran las entradas de la matriz de color que representan el escalado.  
  
|Componente escalar|Entrada de matriz|  
|----------------------------|------------------|  
|Rojo|[0][0]|  
|Verde|[1][1]|  
|Azul|[2][2]|  
|Alpha|[3][3]|  
  
## <a name="scaling-one-color"></a>Una escala de Color  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars2.bmp. A continuación, el código ajusta el componente azul de cada píxel de la imagen en un factor de 2. Se dibuja la imagen original junto con la imagen transformada.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 La siguiente ilustración muestra la imagen original a la izquierda y la imagen de la derecha:  
  
 ![Captura de pantalla que compara los colores originales y se escalan.](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de ajustar el azul. Tenga en cuenta que el componente azul de la cuarta barra de color pasó de 0,8 a 0,6. Eso es porque [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] conserva sólo la parte fraccionaria del resultado. Por ejemplo, (2)(0.8) = 1.6, y la parte fraccionaria de 1,6 es 0,6. Conservar solo la parte fraccionaria garantiza que el resultado es siempre en el intervalo [0, 1].  
  
|Original|Escalar|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>Escalado de varios colores  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars2.bmp. A continuación, el código ajusta los componentes rojos, verde y azules de cada píxel de la imagen. Los componentes rojos se reducen a 25 por ciento, se escalan los componentes verde 35 por ciento y se escalan los componentes azules 50 por ciento.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 La siguiente ilustración muestra la imagen original a la izquierda y la imagen de la derecha:  
  
 ![Captura de pantalla que compara los colores originales y se escalan.](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la escala de color rojo, verde y azul.  
  
|Original|Escalar|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Cambiar el color de las imágenes](recoloring-images.md)
