---
title: Esquema de configuración web
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
ms.openlocfilehash: 1f0241b65c915dd5703ceea97dd5b07f88832003
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698490"
---
# <a name="web-settings-schema"></a>Esquema de configuración web
La configuración web especifica la configuración de la CPU y de ASP.NET de nivel de ejecución que se aplica al comportamiento de todo el proceso administrado por el nivel de hospedaje de ASP.NET. Esta configuración difiere de la del tipo de dominio de la aplicación que se especifica en el archivo Web.config de una aplicación ASP.NET.  
  
 La configuración web se incluye en los archivos Aspnet.config, que se encuentran en las carpetas de instalación de las versiones de .NET Framework. Por ejemplo, el archivo Aspnet.config para [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] está en la carpeta siguiente:  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 La configuración web no se usa en otros archivos de configuración, como el archivo machine.config, el archivo raíz Web.config o los archivos Web.config de nivel de aplicación.  
  
 [Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [Elemento \<system.web> (configuración web)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [Elemento \<applicationPool> (configuración web)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Contiene información usada por el nivel de hospedaje de ASP.NET.|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Especifica la configuración de la CPU y de ASP.NET de nivel de ejecución que se aplica al comportamiento de todo el proceso, administrado por el nivel de hospedaje de ASP.NET.|  
  
## <a name="see-also"></a>Vea también

- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
