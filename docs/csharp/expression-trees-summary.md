---
title: Resumen de árboles de expresión
description: Se resume cómo puede usar árboles de expresión para crear programas dinámicos que interpretan el código como datos y crean nuevas funciones basadas en ese código.
ms.date: 06/20/2016
ms.assetid: eb687ebd-1149-4453-9fc1-12a084495a66
ms.openlocfilehash: 99b9463df096d3aada19ed7995b04ef4bd41c179
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148634"
---
# <a name="expression-trees-summary"></a>Resumen de árboles de expresión

[Anterior: Traducción de expresiones](expression-trees-translating.md)

En esta serie, se vio cómo se pueden usar *árboles de expresión* para crear programas dinámicos que interpretan el código como datos y crean nueva funcionalidad basada en ese código.

Se pueden examinar los árboles de expresión para entender el propósito de un algoritmo. No se puede examinar solo ese código. Se pueden crear árboles de expresión nuevos que representen las versiones modificadas del código original.

También se pueden usar árboles de expresión para buscar en un algoritmo y traducirlo a otro lenguaje o entorno. 

## <a name="limitations"></a>Limitaciones

Hay algunos elementos de lenguaje de C# nuevos que no se traducen correctamente en árboles de expresión. Los árboles de expresión no pueden contener expresiones `await` ni expresiones lambda `async`. Muchas de las características agregadas en la versión 6 de C# no aparecen tal y como se escriben en árboles de expresión. En su lugar, se expondrán las características más recientes de los árboles de expresión en la sintaxis equivalente anterior. Es posible que esta limitación no sea tanta como podría parecer. De hecho, significa que el código que interpreta los árboles de expresión probablemente funcionará igual cuando se introduzcan las nuevas características de lenguaje.

Incluso con estas limitaciones, los árboles de expresión permiten crear algoritmos dinámicos que se basan en la interpretación y la modificación del código que se representa como una estructura de datos. Es una herramienta eficaz y es una de las características del ecosistema .NET que permite que las bibliotecas enriquecidas como Entity Framework realicen lo que hacen.
