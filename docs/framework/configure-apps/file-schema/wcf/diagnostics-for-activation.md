---
title: <diagnostics> para la activación
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 30456963a7d74a93e39bb1fddc0910daae97f039
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704263"
---
# <a name="diagnostics-for-activation"></a>\<diagnósticos > para la activación
Configura las funcionalidades del diagnóstico del agente de escucha de Windows Communication Foundation (WCF).  
  
 \<system.serviceModel.activation>  
\<diagnostics>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`performanceCountersEnabled`|Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
