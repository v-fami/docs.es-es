---
title: Guía de la biblioteca .NET de código abierto
description: Procedimientos recomendados para desarrolladores a la hora de crear bibliotecas .NET de alta calidad
author: jamesnk
ms.author: mairaw
ms.date: 10/17/2018
ms.openlocfilehash: 85d76c8b2bd0f030e3fbc1987e6ff51d6da44e76
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644385"
---
# <a name="open-source-library-guidance"></a>Guía de la biblioteca de código abierto

En esta guía se ofrecen procedimientos recomendados para desarrolladores a la hora de crear bibliotecas .NET de alta calidad. Esta documentación se centra en el *qué* y el *porqué* de la compilación de una biblioteca .NET, no en el *cómo*.

Aspectos de las bibliotecas .NET de código abierto de alta calidad:

> [!div class="checklist"]
> * **Inclusivas**: las bibliotecas. NET de buena calidad deben estar diseñadas para admitir muchas plataformas, lenguajes de programación y aplicaciones.
> * **Estables**: las bibliotecas. NET de buena calidad deben coexistir en el ecosistema de .NET y ejecutarse en aplicaciones que se han compilado mediante muchas bibliotecas.
> * **Diseñadas para evolucionar**: las bibliotecas .NET deben mejorar y evolucionar a lo largo del tiempo, a la vez que deben ser compatibles para los usuarios existentes.
> * **Depurables**: las bibliotecas .NET deben usar las herramientas más recientes para ofrecer una buena experiencia de depuración a los usuarios.
> * **Confiables**: las bibliotecas .NET ganan la confianza de los desarrolladores publicando en NuGet de acuerdo con los procedimientos recomendados de seguridad.

> [!div class="nextstepaction"]
> [Primeros pasos](./get-started.md)

## <a name="types-of-recommendations"></a>Tipos de recomendaciones

Cada artículo presenta cuatro tipos de recomendaciones: **Debe**, **Es recomendable**, **Evite** y **No está permitido**. El tipo de recomendación indica hasta qué punto se deben seguir.

Casi siempre debe seguir una recomendación **Debe**. Por ejemplo:

**✔️ DEBE** distribuir las bibliotecas mediante un paquete NuGet.

Por otro lado, las recomendaciones de tipo **Es recomendable** generalmente deben seguirse, pero existen una serie de excepciones legítimas, por lo que no pasa nada si no sigue alguna de ellas:

**✔️ ES RECOMENDABLE** usar [SemVer 2.0.0](https://semver.org/) para crear versiones de los paquetes NuGet.

Las recomendaciones de tipo **Evite** mencionan prácticas que, en general, no son convenientes, aunque a veces tiene sentido no seguirlas:

**❌ EVITE** las referencias de paquetes NuGet que requieren una versión exacta.

Y, por último, las recomendaciones de tipo **No está permitido** indican qué no se puede hacer casi nunca:

**❌ NO ESTÁ PERMITIDO** publicar versiones de una biblioteca tanto con nombre seguro como sin él. Por ejemplo, `Contoso.Api` y `Contoso.Api.StrongNamed`.

>[!div class="step-by-step"]
>[Siguiente](get-started.md)
