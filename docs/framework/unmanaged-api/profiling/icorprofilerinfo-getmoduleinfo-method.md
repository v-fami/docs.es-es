---
title: ICorProfilerInfo::GetModuleInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleInfo
helpviewer_keywords:
- GetModuleInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleInfo method [.NET Framework profiling]
ms.assetid: 5a90d16f-7929-4987-8f83-a631becf564d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69db53c03d68e30507ff3ab2b11b663970d59af0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049601"
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a>ICorProfilerInfo::GetModuleInfo (Método)
A partir de un identificador de módulo, devuelve el nombre de archivo del módulo y el identificador del ensamblado primario del módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetModuleInfo(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 [in] Identificador del módulo para el que se recuperará la información.  
  
 `ppBaseLoadAddress`  
 [out] Dirección base en la que se carga el módulo.  
  
 `cchName`  
 [in] Longitud, en caracteres, del búfer de retorno `szName`.  
  
 `pcchName`  
 [out] Puntero a la longitud total de caracteres del nombre de archivo del módulo que se devuelve.  
  
 `szName`  
 [out] Búfer de caracteres anchos proporcionado por el llamador. Cuando el método vuelve, este búfer contiene el nombre de archivo del módulo.  
  
 `pAssemblyId`  
 [out] Puntero al identificador del ensamblado primario del módulo.  
  
## <a name="remarks"></a>Comentarios  
 Para los módulos dinámicos, el parámetro `szName` es una cadena vacía y la dirección base es 0 (cero).  
  
 Aunque el `GetModuleInfo` puede llamar al método tan pronto como el identificador del módulo existe, el identificador del ensamblado principal no estará disponible hasta que el generador de perfiles recibe el [ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) devolución de llamada.  
  
 Cuando `GetModuleInfo` vuelve, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre de archivo completo del módulo. Para ello, compare el valor al que `pcchName` apunta con el valor del parámetro `cchName`. Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetModuleInfo`.  
  
 También tiene la opción de llamar primero a `GetModuleInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto. Después, puede establecer el tamaño del búfer en el valor devuelto en `pcchName` y volver a llamar a `GetModuleInfo`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
- [GetModuleInfo2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)
