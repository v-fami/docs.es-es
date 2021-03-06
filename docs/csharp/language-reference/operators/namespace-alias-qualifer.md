---
title: 'Operador ::: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 5bd43bb60736bbcaf8034cc2b369c34f977319ac
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633919"
---
# <a name="-operator-c-reference"></a>Operador :: (Referencia de C#)

El calificador de alias de espacio de nombres (`::`) se usa para buscar identificadores. Siempre se coloca entre dos identificadores, como en este ejemplo:

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

El operador `::` también puede utilizarse con una *directiva de alias using*:

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a>Comentarios

El calificador de alias de espacio de nombres puede ser `global`. Este invoca una búsqueda del espacio de nombres global, en lugar de un espacio de nombres con alias.

## <a name="for-more-information"></a>Para obtener más información

Para obtener un ejemplo de cómo usar el operador `::`, vea la siguiente sección:

- [Cómo: Utilizar el alias del espacio de nombres global](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Palabras clave del espacio de nombres](../keywords/namespace-keywords.md)
- [Operador .](member-access-operators.md#member-access-operator-)
- [extern alias](../keywords/extern-alias.md)
