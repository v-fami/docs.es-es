---
title: Autenticación básica e implícita
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], classes
- Basic authentication
- authentication [.NET Framework], basic
- client authentication, basic
- user authentication, basic
- authentication [.NET Framework], digest
- receiving data, authentication
- client authentication, digest
- Internet, authentication
- digest authentication
- sending data, authentication
- network resources, authentication
- user authentication, digest
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
ms.openlocfilehash: 4f70d2aef3bb064a3df9db9c87671040776332a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089827"
---
# <a name="basic-and-digest-authentication"></a>Autenticación básica e implícita
La implementación <xref:System.Net> de autenticación básica e implícita se ajusta al estándar RFC2617 – HTTP Authentication: Basic and Digest Authentication (Autenticación HTTP: autenticación básica e implícita), disponible en el sitio web del [World Wide Web Consortium](https://www.w3.org).  
  
 Para usar autenticación básica e implícita, una aplicación debe proporcionar un nombre de usuario y una contraseña en la propiedad <xref:System.Net.WebRequest.Credentials%2A> del objeto <xref:System.Net.WebRequest> que usa para solicitar datos de Internet, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
WReq.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword);  
```  
  
> [!CAUTION]
>  Los datos enviados con la autenticación básica e implícita no se cifran. Por tanto, los puede ver un adversario. Además, las credenciales de autenticación básica (nombre de usuario y contraseña) se envían en texto no cifrado y se pueden interceptar.  
  
## <a name="see-also"></a>Vea también

- [Autenticación NTLM y Kerberos](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)
- [Autenticación de Internet](../../../docs/framework/network-programming/internet-authentication.md)
