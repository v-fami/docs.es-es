---
title: 'Punto de conexión: Flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916258"
---
# <a name="endpoint-transactions-flowed-per-second"></a>Punto de conexión: Flujo de transacciones por segundo
Nombre del contador: Flujo de transacciones por segundo.  
  
## <a name="description"></a>Descripción  
 Número de transacciones de flujo a las operaciones en este extremo en un segundo. Este contador se incrementa siempre que se encuentra un id. de transacción en un mensaje enviado al extremo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
