---
title: ICorProfilerThreadEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44595229eaefa0d8fc8ca7bf15a88d0fbf1ee0d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787912"
---
# <a name="icorprofilerthreadenumnext-method"></a>ICorProfilerThreadEnum::Next (Método)
Obtiene el número especificado de subprocesos contiguos de una colección secuencial de subprocesos, comenzando en la posición actual del enumerador en la secuencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `celt`  
 [in] El número de subprocesos para recuperar.  
  
 `ids`  
 [out] Matriz de valores `ThreadID`, cada uno de los cuales representa un subproceso recuperado.  
  
 `pceltFetched`  
 [out] Puntero al número de subprocesos realmente devueltos en la matriz `ids`.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|Se devolvieron `celt` elementos.|  
|S_FALSE|Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerThreadEnum (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
