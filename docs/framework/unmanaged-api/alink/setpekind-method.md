---
title: SetPEKind (Método)
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dec04fa267c61798a3340e9d1e18150b812e9eaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949011"
---
# <a name="setpekind-method"></a>SetPEKind (Método)
Determina el tipo de ejecutable portable, específicas del equipo o independiente del equipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 Id. del ensamblado.  
  
 `FileToken`  
 Símbolo (token) de archivo para el que se establecerá el tipo de PE. Puede ser NULL si `AssemblyID` no indica un netmodule independiente.  
  
 `dwPEKind`  
 El tipo de PE, tal y como indica la [CorPEKind (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).  
  
 `dwMachine`  
 Arquitectura del equipo de destino, como se indica en el encabezado NT.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Vea también

- [GetPEKind (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)
- [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
