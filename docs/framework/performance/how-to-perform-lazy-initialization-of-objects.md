---
title: Procedimiento para realizar la inicialización diferida de objetos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, how to perform
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28463bfd3e54e49461d9ce785d26e5dfca62e438
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61722996"
---
# <a name="how-to-perform-lazy-initialization-of-objects"></a>Procedimiento para realizar la inicialización diferida de objetos
La clase <xref:System.Lazy%601?displayProperty=nameWithType> simplifica el trabajo de creación de instancias e inicialización diferida de los objetos. Al inicializar los objetos de manera diferida, se puede evitar su creación en caso de que no sean necesarios o se puede aplazar su inicialización hasta el primer acceso. Para obtener más información, vea [Inicialización diferida](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se muestra cómo inicializar un valor con <xref:System.Lazy%601>. Es posible que la variable Lazy no sea necesaria, dependiendo de si otro código establece la variable `someCondition` en True o False.  
  
```vb  
Dim someCondition As Boolean = False  
  
Sub Main()  
    'Initializing a value with a big computation, computed in parallel  
    Dim _data As Lazy(Of Integer) = New Lazy(Of Integer)(Function()  
                                                             Dim result =  
                                                                 ParallelEnumerable.Range(0, 1000).  
                                                                 Aggregate(Function(x, y)  
                                                                               Return x + y  
                                                                           End Function)  
                                                             Return result  
                                                         End Function)  
  
    '  do work that may or may not set someCondition to True  
    ' ...  
    '  Initialize the data only if needed  
    If someCondition = True Then  
  
        If (_data.Value > 100) Then  
  
            Console.WriteLine("Good data")  
        End If  
    End If  
End Sub  
```  
  
```csharp  
  static bool someCondition = false;    
  //Initializing a value with a big computation, computed in parallel  
  Lazy<int> _data = new Lazy<int>(delegate  
  {  
      return ParallelEnumerable.Range(0, 1000).  
          Select(i => Compute(i)).Aggregate((x,y) => x + y);  
  }, LazyExecutionMode.EnsureSingleThreadSafeExecution);  
  
  // Do some work that may or may not set someCondition to true.  
  //  ...  
  // Initialize the data only if necessary  
  if (someCondition)  
  {  
    if (_data.Value > 100)  
      {  
          Console.WriteLine("Good data");  
      }  
  }  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> para inicializar un tipo que solo es visible en la instancia de objeto actual en el subproceso actual.  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.LazyInitializer?displayProperty=nameWithType>
- [Inicialización diferida](../../../docs/framework/performance/lazy-initialization.md)
