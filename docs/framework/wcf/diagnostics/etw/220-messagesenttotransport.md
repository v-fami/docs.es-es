---
title: 220 - MessageSentToTransport
ms.date: 03/30/2017
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
ms.openlocfilehash: 92ec664aead15470fbed576bf157d64d984ddebf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781750"
---
# <a name="220---messagesenttotransport"></a>220 - MessageSentToTransport
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|220|  
|Palabras clave|EndToEndMonitoring, Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Este evento se emite cuando el modelo de servicio envía un mensaje al transporte.  
  
> [!NOTE]
>  Este evento no se emitirá para transportes unidireccionales.  
  
## <a name="message"></a>Mensaje  
 El distribuidor envió un mensaje al transporte. Id. de correlación == '%1'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Correlation ID|`xs:GUID`|El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ". Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
