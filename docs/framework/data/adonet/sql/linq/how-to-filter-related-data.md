---
title: Procedimiento para filtrar datos relacionados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: 3dbedfb7065ac4b1a570a3f6cdbcdcc2177f20cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037796"
---
# <a name="how-to-filter-related-data"></a>Procedimiento para filtrar datos relacionados
Utilice el método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> para especificar subconsultas para limitar la cantidad de los datos recuperados.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> limita los `Orders` recuperados a los que no se han enviado hoy. Sin este enfoque, se habrían recuperado todos los `Orders` aunque sólo se requiere un subconjunto.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Consulta de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
