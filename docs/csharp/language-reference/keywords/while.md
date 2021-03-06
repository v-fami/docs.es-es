---
title: while - Referencia de C#
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 2cf58e2edc5685032c2b9e590bc456e3a4e4d79b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633075"
---
# <a name="while-c-reference"></a>while (Referencia de C#)

La instrucción `while` ejecuta una instrucción o un bloque de instrucciones mientras una expresión booleana especificada se evalúa como `true`. Como esa expresión se evalúa antes de cada ejecución del bucle, un bucle `while` se ejecuta cero o varias veces. Esto es diferente del bucle [do](do.md) que se ejecuta una o varias veces.

En cualquier punto del bloque de instrucciones `while`, se puede salir del bucle mediante la instrucción [break](break.md).

Puede ir directamente a la evaluación de la expresión `while` mediante la instrucción [continue](continue.md). Si la expresión se evalúa como `true`, la ejecución continúa en la primera instrucción del bucle. En caso contrario, la ejecución continúa en la primera instrucción después del bucle.

También se puede salir de un bucle `while` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra el uso de la instrucción `while`. Haga clic en **Ejecutar** para ejecutar el código de ejemplo. Después, puede modificar el código y volver a ejecutarlo.

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección [La instrucción while](~/_csharplang/spec/statements.md#the-while-statement) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Instrucciones de iteración](iteration-statements.md)
- [do (instrucción)](do.md)
