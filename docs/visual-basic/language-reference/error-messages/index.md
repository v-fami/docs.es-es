---
title: Mensajes de error (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- errors [Visual Basic]
- error messages
- trappable errors
- errors [Visual Basic], trappable
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
ms.openlocfilehash: 822c0f266e7dd68f063043d98a9f4af308ae93fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013821"
---
# <a name="error-messages-visual-basic"></a>Mensajes de error (Visual Basic)
Al escribir, compilar o ejecutar una aplicación de Visual Basic, pueden producirse los siguientes tipos de errores:  
  
1. Errores en tiempo de diseño, que se producen al escribir una aplicación en Visual Studio.  
  
2. Errores en tiempo de compilación, que se producen cuando se compila una aplicación en Visual Studio o en un símbolo del sistema.  
  
3. Errores en tiempo de ejecución, que se producen al ejecutar una aplicación en Visual Studio o como un archivo ejecutable independiente.  
  
 Para obtener información sobre cómo solucionar un error específico, vea [Recursos adicionales para programadores de Visual Basic](../../../visual-basic/getting-started/additional-resources.md).  
  
## <a name="run-time-errors"></a>Errores en tiempo de ejecución  
 Si una aplicación Visual Basic intenta realizar una acción que no se puede ejecutar el sistema, se produce un error de tiempo de ejecución y Visual Basic produce una `Exception` objeto. Visual Basic puede generar errores personalizados de cualquier dato de tipo, incluidos `Exception` objetos mediante el uso de la `Throw` instrucción. Una aplicación puede identificar el error y mostrar el número de error y el mensaje de una excepción detectada. Si no se detecta ningún error, la aplicación finaliza.  
  
 El código puede capturar y examinar los errores en tiempo de ejecución. Si se incluye el código que produce el error en un bloque `Try`, puede capturar cualquier error producido dentro de un bloque `Catch` coincidente. Para obtener información sobre cómo capturar errores en tiempo de ejecución y responder a ellos en el código, vea [Instrucción Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="compile-time-errors"></a>Errores en tiempo de compilación  
 Si el compilador de Visual Basic encuentra un problema en el código, se produce un error en tiempo de compilación. En el Editor de código, puede identificar fácilmente qué línea de código provocó el error porque aparece una línea ondulada debajo de la línea de código. Aparece el mensaje de error si selecciona la línea ondulada o abre la **lista de errores**, en la que también se muestran otros mensajes.  
  
 Si un identificador tiene un subrayado ondulado y aparece un subrayado corto debajo del carácter situado más a la derecha, puede generar un código auxiliar para la clase, el constructor, el método, la propiedad, el campo o la enumeración. Para más información, vea [Generar a partir del uso](/visualstudio/ide/visual-csharp-intellisense#generate-from-usage).
  
 Si resuelve las advertencias del compilador de Visual Basic, puede escribir código que se ejecuta con mayor rapidez y con menos errores. Estas advertencias identifican código que puede producir errores cuando se ejecuta la aplicación. Por ejemplo, el compilador generará una advertencia cuando intente invocar un miembro de una variable de objeto sin asignar, volver de una función sin establecer el valor devuelto o ejecutar un bloque `Try` con errores en la lógica para detectar excepciones. Para más información sobre advertencias, incluidas las formas de activarlas y desactivarlas, vea [Configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).
