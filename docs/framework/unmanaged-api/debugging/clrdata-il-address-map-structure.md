---
title: Estructura CLRDATA_IL_ADDRESS_MAP
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 94ebef007cf2893b63383aa4657d382728d3c759
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416536"
---
# <a name="clrdatailaddressmap-structure"></a><span data-ttu-id="f7c3b-102">Estructura CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="f7c3b-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="f7c3b-103">Define un IL para asignación de direcciones.</span><span class="sxs-lookup"><span data-stu-id="f7c3b-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f7c3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7c3b-104">Syntax</span></span>

```
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="f7c3b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f7c3b-105">Members</span></span>

| <span data-ttu-id="f7c3b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f7c3b-106">Member</span></span>         | <span data-ttu-id="f7c3b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7c3b-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="f7c3b-108">Desplazamiento IL para el intervalo de direcciones independientes</span><span class="sxs-lookup"><span data-stu-id="f7c3b-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="f7c3b-109">La dirección de inicio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="f7c3b-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="f7c3b-110">La dirección final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="f7c3b-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="f7c3b-111">Tipo de los datos.</span><span class="sxs-lookup"><span data-stu-id="f7c3b-111">The type of the data.</span></span> <span data-ttu-id="f7c3b-112">Este valor no se usa actualmente</span><span class="sxs-lookup"><span data-stu-id="f7c3b-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="f7c3b-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7c3b-113">Remarks</span></span>

<span data-ttu-id="f7c3b-114">Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f7c3b-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="f7c3b-115">Para ello, defina la estructura según lo especificado anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="f7c3b-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="f7c3b-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7c3b-116">Requirements</span></span>

<span data-ttu-id="f7c3b-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7c3b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f7c3b-118">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="f7c3b-118">**Header:** None</span></span>  
<span data-ttu-id="f7c3b-119">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f7c3b-119">**Library:** None</span></span>   
<span data-ttu-id="f7c3b-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f7c3b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f7c3b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7c3b-121">See Also</span></span>

- [<span data-ttu-id="f7c3b-122">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="f7c3b-122">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="f7c3b-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="f7c3b-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="f7c3b-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="f7c3b-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)