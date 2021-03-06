---
title: Seguridad del flujo de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], workflow security
ms.assetid: d712a566-f435-44c0-b8c0-49298e84b114
ms.openlocfilehash: b14dd600526612b6af8b9fad15f65a748eb0b368
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637533"
---
# <a name="workflow-security"></a>Seguridad del flujo de trabajo
Windows Workflow Foundation (WF) se integra con varias tecnologías diferentes, como Microsoft SQL Server y Windows Communication Foundation (WCF). Al interactuar con estas tecnologías, se pueden introducir problemas de seguridad en su flujo de trabajo si no se hace de manera correcta.

## <a name="persistence-security-concerns"></a>Problemas de seguridad de persistencia

1. Los flujos de trabajo que usan una actividad <xref:System.Activities.Statements.Delay> y persistencia se deben reactivar mediante un servicio. Windows AppFabric usa el Servicio de administración de flujos de trabajo (WMS) para reactivar flujos de trabajo con temporizadores expirados. WMS crea un <xref:System.ServiceModel.WorkflowServiceHost> para hospedar el flujo de trabajo reactivado. Si se detiene el servicio de WMS, los flujos de trabajo conservados no se reactivarán cuando sus temporizadores expiren.

2. El acceso a la creación de instancias duraderas debe protegerse contra entidades malintencionadas externas al dominio de aplicación. Además, los desarrolladores deben asegurarse de que el código malintencionado no se pueda ejecutar en el mismo dominio de aplicación que el código de creación de instancias duraderas.

3. La creación de instancias duraderas no se debe ejecutar con permisos elevados (administrador).

4. Los datos que se procesan fuera del dominio de aplicación deben ser protegidos.

5. Las aplicaciones que necesitan aislamiento de seguridad no deben compartir la misma instancia de abstracción de esquema. Dichas aplicaciones deben usar proveedores de almacén diferentes o proveedores de almacén configurados usar diferentes instancias de almacén.

## <a name="sql-server-security-concerns"></a>Problemas de seguridad de SQL Server

- Cuando se usan numerosas actividades secundarias, ubicaciones, marcadores, extensiones de host o ámbitos, o cuando se usan marcadores con grandes cantidades de carga, puede ocurrir que la memoria se acabe o que se asignen cantidades indebidas de espacio a la base de datos durante la persistencia. Este hecho se puede reducir usando la seguridad del nivel de objeto o de la base de datos.

- Al usar <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, se debe proteger el almacén de instancias. Para obtener más información, consulte [SQL Server Best Practices](https://go.microsoft.com/fwlink/?LinkId=164972).

- Se deberían cifrar los datos confidenciales del almacén de instancias. Para obtener más información, consulte [cifrado de seguridad de SQL](https://go.microsoft.com/fwlink/?LinkId=164976).

- Puesto que la cadena de conexión a bases de datos se suele incluir en un archivo de configuración, la seguridad de nivel de Windows (ACL) se debe usar para asegurarse de que el archivo de configuración (Web.Config normalmente) es seguro, y que la información de inicio de sesión y contraseña no se incluyen en la cadena de conexión. La autenticación de Windows se debe usar entre la base de datos y el servidor web en su lugar.

## <a name="considerations-for-workflowservicehost"></a>Consideraciones para WorkflowServiceHost

- Se deben proteger los extremos de Windows Communication Foundation (WCF) que se usan en flujos de trabajo. Para obtener más información, consulte [información general sobre la seguridad de WCF](https://go.microsoft.com/fwlink/?LinkID=164975).

- La autorización en el nivel de host puede implementarse mediante <xref:System.ServiceModel.ServiceAuthorizationManager>. Vea [Cómo: Crear un administrador de autorización personalizado para un servicio](https://go.microsoft.com/fwlink/?LinkId=192228) para obtener más información.

- El ServiceSecurityContext para el mensaje entrante también está disponible desde el flujo de trabajo mediante el acceso a OperationContext.

## <a name="wf-security-pack-ctp"></a>CTP del paquete de seguridad de WF
 El CTP 1 del paquete de seguridad de Microsoft WF es la primera versión de community technology preview (CTP) de un conjunto de actividades y su implementación basada en [Windows Workflow Foundation](index.md) en [.NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w0x726c2(v=vs.100)) (WF (4) y el [Windows Identity Foundation (WIF)](../security/index.md).  El CTP 1 del paquete de seguridad de Microsoft WF contiene ambas actividades y sus diseñadores que muestran cómo habilitar fácilmente diferentes escenarios relacionados con la seguridad usando el flujo de trabajo, incluidas:

1. Suplantar una identidad del cliente en el flujo de trabajo

2. Autorización en el flujo de trabajo, como PrincipalPermission y validación de notificaciones

3. Mensajería autenticada mediante ClientCredentials especificadas en el flujo de trabajo, como nombre de usuario/contraseña o un token recuperado de un Servicio de token de seguridad (STS)

4. Llevar un token de seguridad de cliente a un servicio de fondo (delegación basada en notificaciones) mediante ActAs de WS-Trust

Para obtener más información y descargar el CTP del paquete de seguridad de WF, vea: [CTP del paquete de seguridad WF](https://archive.codeplex.com/?p=wf)
