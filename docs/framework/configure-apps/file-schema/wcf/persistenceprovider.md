---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dc8dea0ddd1ea074c08952e3e2ebfef2d12f7183
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783297"
---
# <a name="persistenceprovider"></a>\<persistenceProvider>
Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors>  
\<comportamiento >  
\<persistenceProvider>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|persistenceOperationTimeout|Un valor <xref:System.TimeSpan> que especifica el tiempo de espera usado en las operaciones de persistencia. El valor predeterminado es "00: 00:30".|  
|type|Una cadena que especifica el tipo del generador del proveedor de persistencia que se va a usar.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento especifica el proveedor de persistencia que se va a utilizar para serializar el estado de un servicio WCF. Se debería utilizar junto con `wsHttpContextBinding` que pasa la información de estado en encabezados HTTP.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
