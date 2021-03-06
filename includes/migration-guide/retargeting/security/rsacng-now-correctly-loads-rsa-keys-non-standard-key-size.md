---
ms.openlocfilehash: 4892f75e4ae673d9d9cc7e9eeb6fb9b1a73f572e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805123"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng ahora carga correctamente las claves RSA de tamaño de clave no estándar

|   |   |
|---|---|
|Detalles|En las versiones de .NET Framework anteriores a la 4.6.2, los clientes con tamaños de clave no estándar para los certificados RSA no podrán tener acceso a esas claves a través de los métodos de extensión <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> y <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name>.  Se iniciará una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> con el mensaje &quot;The requested key size is not supported&quot; (No se admite el tamaño de clave solicitado). Este problema se ha solucionado en .NET Framework 4.6.2. De forma similar, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> y <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> ahora funcionan con tamaños de clave no estándar sin iniciar una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>.|
|Sugerencia|Si no hay ninguna lógica de control de excepciones que se base en el comportamiento anterior en el que se inicia una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> cuando se usan tamaños de clave no estándar, considere la posibilidad de quitar la lógica.|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li></ul>|
