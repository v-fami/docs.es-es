---
title: Efectuar operaciones aritméticas con fechas y horas
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], arithmetic operations
- dates [.NET Framework], arithmetic operations
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], comparing
- DateTime structure, arithmetic operations
- DateTimeOffset structure, arithmetic operations
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d5f807481468b61365c8b4d8412f12a4741ebb9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912761"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Efectuar operaciones aritméticas con fechas y horas

Aunque tanto la <xref:System.DateTime> y <xref:System.DateTimeOffset> proporcionan miembros que realizan operaciones aritméticas en sus valores, los resultados de las operaciones aritméticas son muy diferentes. En este tema examina estas diferencias, se relacionan con los grados de reconocimiento de la zona horaria en los datos de fecha y hora y se describe cómo realizar operaciones con conocimiento zona horaria mediante datos de fecha y hora de completamente.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Las comparaciones y operaciones aritméticas con valores de fecha y hora

El <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> propiedad permite un <xref:System.DateTimeKind> valor que se asignará a la fecha y hora para indicar si representa la hora local, hora Universal coordinada (UTC) o la hora en una zona horaria no especificada. Sin embargo, se omite esta información limitada de zona horaria al realizar comparaciones u operaciones de fecha y hora aritméticas en <xref:System.DateTimeKind> valores. Esto se muestra en el ejemplo siguiente, que compara la hora local actual con la hora UTC actual.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

El <xref:System.DateTime.CompareTo%28System.DateTime%29> método informa de que es anterior a la hora local (o menor que) la hora UTC y la operación de resta indica que la diferencia entre la hora UTC y la hora local para un sistema de la zona horaria del Pacífico es de siete horas. Pero, dado que estos dos valores proporcionan representaciones diferentes de un único punto en el tiempo, resulta evidente en este caso que este intervalo de tiempo es totalmente atribuible a la diferencia horaria de la zona horaria local respecto de la hora UTC.

Por lo general, el <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> propiedad no afecta a los resultados devueltos por <xref:System.DateTime.Kind> métodos aritméticos y de comparación (como indica la comparación de dos puntos idénticos en el tiempo), aunque puede afectar a la interpretación de los resultados. Por ejemplo:

* El resultado de cualquier operación aritmética realizada en dos valores de fecha y hora cuyas <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> igual a ambas propiedades <xref:System.DateTimeKind> refleja el intervalo de tiempo real entre los dos valores. Del mismo modo, la comparación de estos dos valores de fecha y hora refleja con exactitud la relación entre los tiempos.

* El resultado de cualquier operación aritmética o de comparación realizada en dos valores de fecha y hora cuyas <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> igual a ambas propiedades <xref:System.DateTimeKind> o en dos valores de fecha y hora con diferentes <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> los valores de propiedad refleja la diferencia de hora del reloj entre los dos valores.

* Las operaciones aritméticas o de comparación en valores de fecha y hora local no tienen en cuenta si un valor concreto es ambiguo o no válido, ni tienen en cuenta el efecto de las reglas de ajuste que son consecuencia de la transición de la zona horaria local hacia o desde el horario de verano.

* Las operaciones que comparen o calculen la diferencia entre la hora UTC y una hora local incluyen en el resultado un intervalo de tiempo igual a la diferencia horaria de la zona horaria local respecto de la hora UTC.

* Las operaciones que comparen o calculen la diferencia entre una hora no especificada y la hora UTC o la hora local reflejan la hora de reloj simple. No se consideran las diferencias de zona horaria y el resultado no refleja la aplicación de reglas de ajuste de zona horaria.

* Las operaciones que comparen o calculen la diferencia entre dos horas no especificadas pueden incluir un intervalo desconocido que refleje la diferencia entre la hora de dos zonas horarias diferentes.

Hay muchos escenarios en qué zona horaria diferencias no afectan a los cálculos de fecha y hora (para obtener una explicación de algunas de estas, consulte [elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) o en el que el contexto de la fecha y hora datos definen el significado de las operaciones aritméticas o de comparación.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Las comparaciones y operaciones aritméticas con valores de DateTimeOffset

Un <xref:System.DateTimeOffset> valor incluye no solo una fecha y hora, sino también un desplazamiento que se define sin ambigüedad esa fecha y hora con respecto a UTC. Esto permite definir la igualdad de forma ligeramente diferente que para <xref:System.DateTimeOffset> valores. Mientras que <xref:System.DateTime> los valores son iguales si tienen el misma valor fecha y hora, <xref:System.DateTimeOffset> valores son iguales si ambas hacen referencia al mismo punto en el tiempo. Esto hace que un <xref:System.DateTimeOffset> valor más preciso y necesite una menor interpretación cuando se usa en las comparaciones y en la mayoría de las operaciones aritmética que determinan el intervalo entre dos fechas y horas. El ejemplo siguiente, que es el <xref:System.DateTimeOffset> equivalente al ejemplo anterior que compara local y UTC <xref:System.DateTimeOffset> valores, se muestra esta diferencia de comportamiento.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

En este ejemplo, el <xref:System.DateTimeOffset.CompareTo%2A> método indica que la hora local actual y la hora UTC actual son iguales y resta de <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> valores indica que la diferencia entre las dos horas es <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.

La principal limitación de usar <xref:System.DateTimeOffset> valores de fecha y hora es que aunque <xref:System.DateTimeOffset> valores tienen alguna zona horaria, no son totalmente consciente de zona horaria. Aunque el <xref:System.DateTimeOffset> desplazamiento del valor refleja el desplazamiento de una zona horaria a la hora UTC cuando un <xref:System.DateTimeOffset> variable primero se asigna un valor, se desasocia de la zona horaria a partir de entonces. Dado que ya no está directamente asociada con una hora identificable, la suma y resta de intervalos de fecha y hora no tiene en cuenta las reglas de ajuste de una zona horaria.

Por ejemplo, la transición al horario de verano en la zona de la hora estándar central de los Estados Unidos se produce a las 2:00 a. m. del 9 de marzo de 2008. Esto significa que la suma de un intervalo de dos horas y media a la hora estándar central 1:30 a. m. del día 9 de marzo de 2008 debería generar la siguiente fecha y hora: 5:00 a. m. del 9 de marzo de 2008. Pero como se muestra en el ejemplo siguiente, el resultado de la suma es 4:00 a. m. del 9 de marzo de 2008. Observe que el resultado de esta operación representa el punto correcto en el tiempo, aunque no es la hora de la zona horaria que nos interesa (es decir, no tiene la diferencia horaria de la zona horaria esperada).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Operaciones aritméticas con horas de zonas horarias

La <xref:System.TimeZoneInfo> clase incluye una serie de métodos de conversión que se aplican automáticamente los ajustes cuando convierten las horas de una zona horaria a otra. Entre ellas se incluyen las siguientes:

* El <xref:System.TimeZoneInfo.ConvertTime%2A> y <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> métodos, que convierten las horas entre dos zonas horarias.

* El <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> y <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> métodos, que conversión la hora en una zona horaria determinada en hora UTC o conversión la hora UTC a la hora de una zona horaria determinada.

Para obtener más información, consulte [convertir horas entre zonas horarias](../../../docs/standard/datetime/converting-between-time-zones.md).

La <xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> clase no proporciona ningún método que se aplica automáticamente a las reglas de ajuste al realizar la fecha y hora aritmético. Para hacerlo, puede convertir la hora de una zona horaria a la hora UTC, realizar la operación aritmética y, después, convertir la hora UTC de nuevo a la hora de la zona horaria. Para obtener más detalles, vea [Cómo: Usar zonas horarias en fecha y hora aritmético](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).

Por ejemplo, el código siguiente se parece al código anterior que sumaba dos horas y media a la fecha y hora 2:00 a. m. del 9 de marzo de 2008. Pero, dado que convierte una hora estándar central a la hora UTC antes de realizar la operación aritmética de fecha y hora y, después, convierte el resultado en hora UTC de nuevo a la hora estándar central, la hora resultante refleja la transición de la zona de la hora estándar central al horario de verano.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Cómo: Usar zonas horarias en fecha y hora aritmético](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
