---
title: Ejemplo de ejecución diferida (C#)
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 08125f8da54db18423f90564a51fcffad8db44c2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598021"
---
# <a name="deferred-execution-example-c"></a>Ejemplo de ejecución diferida (C#)
En este tema se muestra cómo la ejecución aplazada y la evaluación diferid afectan a la ejecución de las consultas de LINQ to XML.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra el orden de ejecución cuando se usa un método de extensión que utiliza la ejecución aplazada. El ejemplo declara una matriz de tres cadenas. A continuación recorre en iteración la recopilación devuelta por `ConvertCollectionToUpperCase`.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 Tenga en cuenta que durante el recorrido en iteración de la recopilación devuelta por `ConvertCollectionToUpperCase`, cada elemento se recupera de la matriz de cadenas de origen y se convierte a mayúsculas antes de que se recupere el siguiente elemento de la matriz de cadenas de origen.  
  
 Puede ver que no se convierte a mayúsculas toda la matriz de cadenas antes de que se procese cada elemento en el bucle `foreach` de `Main`.  
  
 En el siguiente tema de este tutorial se ilustra el encadenado de cadenas juntas:  
  
- [Chaining Queries Example (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md) (Ejemplo de encadenamiento de consultas (C#))  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Encadenar cadenas juntas (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
