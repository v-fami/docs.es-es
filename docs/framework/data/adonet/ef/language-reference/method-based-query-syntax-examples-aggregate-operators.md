---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Operadores de agregación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0e306067-5720-4782-9719-2286570a7e47
ms.openlocfilehash: 06609ce14edeb7e9306816b8a8d58d2212b61751
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760615"
---
# <a name="method-based-query-syntax-examples-aggregate-operators"></a>Ejemplos de sintaxis de consulta basada en métodos: Operadores de agregación
Los ejemplos de este tema muestran cómo usar el <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, y <xref:System.Linq.Enumerable.Sum%2A> métodos para consultar el [modelo AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) utilizando sintaxis de consulta basada en métodos. El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.  
  
 Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a>Average  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de los productos.  
  
 [!code-csharp[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de los productos de cada estilo.  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el importe total promedio a pagar.  
  
 [!code-csharp[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para obtener el importe total promedio a pagar de cada identificador de contacto.  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para obtener el pedido con el importe total promedio a pagar de cada contacto.  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a>Recuento  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de la tabla Product.  
  
 [!code-csharp[DP L2E Examples#Count](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#count)]
 [!code-vb[DP L2E Examples#Count](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver una lista de identificadores de contactos y el número de pedidos que tiene cada uno de ellos.  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se agrupan los productos por colores y se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de cada grupo de color.  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a>LongCount  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene el recuento de contactos como un entero largo.  
  
 [!code-csharp[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a>Máx.  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar.  
  
 [!code-csharp[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar de cada identificador de contacto.  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el pedido con el mayor importe total a pagar de cada identificador de contacto.  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a>Mín.  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar.  
  
 [!code-csharp[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar de cada identificador de contacto.  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el pedido con el menor importe total a pagar de cada contacto.  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a>Sum  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el número total de cantidades de pedido de la tabla SalesOrderDetail.  
  
 [!code-csharp[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumprojection_mq)]
 [!code-vb[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumprojection_mq)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el menor importe total a pagar de cada identificador de contacto.  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a>Vea también

- [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
