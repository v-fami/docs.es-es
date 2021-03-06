---
title: 'Expresiones condicionales: if... then... else'
description: Obtenga información sobre cómo escribir expresiones condicionales F# para ejecutar distintas bifurcaciones de código.
ms.date: 05/16/2016
ms.openlocfilehash: db2d5ce5b75ecda171f2623c986878dcee1cf4d9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641986"
---
# <a name="conditional-expressions-ifthenelse"></a>Expresiones condicionales: `if...then...else`

El `if...then...else` expresión ejecuta diferentes ramas de código y también se evalúa como un valor distinto según la expresión booleana especificada.

## <a name="syntax"></a>Sintaxis

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *expression1* se ejecuta cuando la expresión booleana se evalúa como `true`; en caso contrario, *expression2* se ejecuta.

A diferencia de otros lenguajes, la `if...then...else` construcción es una expresión, no una instrucción. Esto significa que genera un valor, que es el valor de la última expresión en la rama que se ejecuta. Deben coincidir con los tipos de los valores generados en cada rama. Si hay explícita no `else` rama, su tipo es `unit`. Por lo tanto, si el tipo de la `then` rama es cualquier tipo distinto `unit`, debe haber un `else` rama con el mismo tipo de valor devuelto. Cuando se encadenan `if...then...else` juntas, puede usar la palabra clave expresiones `elif` en lugar de `else if`; son equivalentes.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo usar el `if...then...else` expresión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
