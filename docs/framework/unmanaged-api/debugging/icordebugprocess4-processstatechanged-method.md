---
title: Método ICorDebugProcess4::ProcessStateChanged
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 5e3a6714489e2051a09b5855ab9f911ef2f57450
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632282"
---
# <a name="icordebugprocess4processstatechanged-method"></a>Método ICorDebugProcess4::ProcessStateChanged

Notifica a la canalización ICorDebug que fuera del depurador de proceso continúa la ejecución del depurado.

## <a name="syntax"></a>Sintaxis

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parámetros

 `eChange`\
[in] Un miembro de la [enumeración CorDebugStateChange](cordebugstatechange-enumeration.md) que describe un cambio de estado de ejecución del proceso.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la `ICorDebugProcess4` interfaz y corresponde a la cuarta ranura de la tabla de métodos virtuales.

## <a name="requirements"></a>Requisitos

 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Encabezado**: Ninguna

 **Biblioteca:** Ninguna
 
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugProcess4](icordebugprocess4-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
