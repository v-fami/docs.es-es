---
title: ICLRSyncManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3e4affa363083ce55ac3764c26412a0d60ba3f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763599"
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager (Interfaz)
Define métodos que permiten al host para obtener información sobre las tareas solicitadas y detectar interbloqueos en su implementación de la sincronización.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator (método)](iclrsyncmanager-createrwlockowneriterator-method.md)|Solicita que common language runtime (CLR) crea un iterador para el host se utiliza para determinar el conjunto de tareas que esperan en un bloqueo de lector y escritor.|  
|[DeleteRWLockOwnerIterator (método)](iclrsyncmanager-deleterwlockowneriterator-method.md)|Solicita que el CLR destruya un iterador que se creó mediante una llamada a `CreateRWLockOwnerIterator`.|  
|[GetMonitorOwner (método)](iclrsyncmanager-getmonitorowner-method.md)|Obtiene la tarea que posee al monitor especificado.|  
|[GetRWLockOwnerNext (método)](iclrsyncmanager-getrwlockownernext-method.md)|Obtiene la siguiente tarea está esperando el bloqueo de lector y escritor actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Thread>
- [IHostSyncManager (interfaz)](ihostsyncmanager-interface.md)
- [Subprocesamiento administrado y](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [Interfaces de hospedaje](hosting-interfaces.md)
