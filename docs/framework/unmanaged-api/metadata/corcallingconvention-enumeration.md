---
title: CorCallingConvention (Enumeración)
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44a4b5903cec2249eb1e176381fe3d8e600dd5e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046116"
---
# <a name="corcallingconvention-enumeration"></a>CorCallingConvention (Enumeración)
Contiene valores que describen los tipos de convenciones de llamada que se realizan en código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|Indica una convención de llamada predeterminada.|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|Indica que el método toma un número variable de parámetros.|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|Indica que la llamada es a un campo.|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|Indica que la llamada es a un método local.|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|Indica que la llamada es a una propiedad.|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|Indica que la llamada no administrada.|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|Indica la creación de instancias de un método genérico.|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|Indica una llamada PInvoke de 64 bits a un método que toma un número variable de parámetros.|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|Describe un valor de 4 bits no válido.|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|Indica que la convención de llamada se describe en los cuatro bits inferiores.|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|Indica que el bit superior describe un `this` parámetro.|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|Indica que un `this` es describir explícitamente en la firma del parámetro.|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|Indica una firma de método genérico con un número de argumentos de tipo explícito. Esto precede a un número de parámetros ordinarios.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
