---
title: ICorDebugGCReferenceEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57f09a8974dc1e8cb20185975c42c1cb3ad86a5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647152"
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum (Interfaz)
Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|Obtiene el número especificado de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instancias que contienen información sobre los objetos que se pueden recolectar.|  
  
## <a name="remarks"></a>Comentarios  
 El `ICorDebugGCReferenceEnum` interfaz implementa la interfaz "ICorDebugEnum".  
  
 Un `ICorDebugGCReferenceEnum` instancia se rellena con [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instancias mediante una llamada a la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) método. [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) se pueden enumerar objetos mediante una llamada a la [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) método.  
  
 El [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objetos de la colección que se rellena mediante este método representan tres tipos de objetos:  
  
- Objetos de todas las pilas administradas. Esto incluye referencias activas en código administrado, así como los objetos creados por common language runtime.  
  
- Objetos de la tabla de identificadores. Esto incluye las referencias fuertes (`HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT`) y las variables estáticas en un módulo.  
  
- Objetos de la cola del finalizador. La cola del finalizador raíces objetos hasta que se ha ejecutado el finalizador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
