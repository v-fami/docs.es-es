---
title: Diferencias entre realizar consultas de un XDocument Un XElement (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
ms.openlocfilehash: 500b1e58663ef6aca052850ad7994687e2cc36f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766498"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a>Diferencias entre realizar consultas de un XDocument Un XElement (Visual Basic)
Cuando carga un documento mediante <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, observará que es necesario escribir las consultas de forma ligeramente diferente a como lo haría en caso de cargar el documento mediante <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>Comparación entre XDocument.Load y XElement.Load  
 Cuando carga un documento XML en un <xref:System.Xml.Linq.XElement> mediante <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, el <xref:System.Xml.Linq.XElement> situado en la raíz del árbol XML contiene al elemento raíz del documento que se ha cargado. Sin embargo, cuando carga el mismo documento XML en un <xref:System.Xml.Linq.XDocument> mediante <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, la raíz del árbol es un nodo <xref:System.Xml.Linq.XDocument> el elemento raíz del documento cargado es el nodo secundario permitido <xref:System.Xml.Linq.XElement> de <xref:System.Xml.Linq.XDocument>. Los ejes de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] funcionan en relación al nodo raíz.  
  
 Este primer ejemplo carga un árbol XML utilizando <xref:System.Xml.Linq.XElement.Load%2A>. A continuación, consulta los elementos secundarios de la raíz del árbol.  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XElement.Load")  
Console.WriteLine("----")  
Dim doc As XElement = XElement.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Como cabe esperar, este ejemplo genera el siguiente resultado:  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 El siguiente ejemplo es igual al anterior, con la diferencia de que el árbol XML se carga en un <xref:System.Xml.Linq.XDocument> en vez de un <xref:System.Xml.Linq.XElement>.  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 Observe que la misma consulta devolvió el nodo `Root` en vez de los tres nodos secundarios.  
  
 Una forma de afrontar este asunto es utilizar la propiedad <xref:System.Xml.Linq.XDocument.Root%2A> antes de obtener acceso a los métodos de los ejes, tal y como se indica a continuación:  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Root.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Ahora, esta consulta genera el mismo resultado que la consulta del árbol cuya raíz comienza en <xref:System.Xml.Linq.XElement>. El ejemplo genera el siguiente resultado:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a>Vea también

- [Consultas básicas (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
