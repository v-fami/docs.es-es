---
title: Procedimiento Ordenar o filtrar los datos de texto por palabra o campo (LINQ) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9df137fe-335b-46e0-aecf-ea8a9eddd4e3
ms.openlocfilehash: 5d6a8d26f28feafecfbddfb8d2b538adc22f1b90
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592466"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-visual-basic"></a>Procedimiento Ordenar o filtrar los datos de texto por palabra o campo (LINQ) (Visual Basic)
En el ejemplo siguiente se muestra cómo ordenar líneas de texto estructurado, como valores separados por comas, por cualquier campo de la línea. El campo se puede especificar dinámicamente en tiempo de ejecución. Supongamos que los campos de scores.csv representan el número de identificación de un alumno, seguido de una serie de cuatro calificaciones.  
  
### <a name="to-create-a-file-that-contains-data"></a>Para crear un archivo que contenga datos  
  
1. Copie los datos de scores.csv desde el tema [Cómo: Combinar contenido de archivos no similares (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) y guárdelo en la carpeta de su solución.  
  
## <a name="example"></a>Ejemplo  
  
```vb  
Class SortLines  
  
    Shared Sub Main()  
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")  
  
        ' Change this to any value from 0 to 4  
        Dim sortField As Integer = 1  
  
        Console.WriteLine("Sorted highest to lowest by field " & sortField)  
  
        ' Demonstrates how to return query from a method.  
        ' The query is executed here.  
        For Each str As String In SortQuery(scores, sortField)  
            Console.WriteLine(str)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    Shared Function SortQuery(  
        ByVal source As IEnumerable(Of String),   
        ByVal num As Integer) As IEnumerable(Of String)  
  
        Dim scoreQuery = From line In source   
                         Let fields = line.Split(New Char() {","})   
                         Order By fields(num) Descending   
                         Select line  
  
        Return scoreQuery  
    End Function  
End Class  
' Output:  
' Sorted highest to lowest by field 1  
' 116, 99, 86, 90, 94  
' 120, 99, 82, 81, 79  
' 111, 97, 92, 81, 60  
' 114, 97, 89, 85, 82  
' 121, 96, 85, 91, 60  
' 122, 94, 92, 91, 91  
' 117, 93, 92, 80, 87  
' 118, 92, 90, 83, 78  
' 113, 88, 94, 65, 91  
' 112, 75, 84, 91, 39  
' 119, 68, 79, 88, 92  
' 115, 35, 72, 91, 70  
```  
  
 En este ejemplo también muestra cómo devolver una variable de consulta de una función.  
  
## <a name="compiling-the-code"></a>Compilar el código  
Cree un proyecto de aplicación de consola VB.NET, con un `Imports` instrucción del espacio de nombres System.Linq.
  
## <a name="see-also"></a>Vea también

- [LINQ y cadenas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
