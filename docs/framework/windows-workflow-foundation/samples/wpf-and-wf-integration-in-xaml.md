---
title: Integración de WPF y WF en XAML
ms.date: 03/30/2017
ms.assetid: a4f53b48-fc90-4315-bca0-ba009562f488
ms.openlocfilehash: 2e5387186be2006c2c6c3e14e7000a21ed88140f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639095"
---
# <a name="wpf-and-wf-integration-in-xaml"></a>Integración de WPF y WF en XAML
Este ejemplo muestra cómo crear una aplicación que usa las características de Windows Presentation Foundation (WPF) y Windows Workflow Foundation (WF) en un documento XAML único. Para lograr esto, el ejemplo utiliza la extensibilidad de Windows Workflow Foundation (WF) y XAML.

## <a name="sample-details"></a>Detalles del ejemplo
 El archivo ShowWindow.xaml se deserializa en una actividad <xref:System.Activities.Statements.Sequence> con dos variables de cadena que son manipuladas por las actividades de la secuencia: `ShowWindow` y `WriteLine`. La actividad <xref:System.Activities.Statements.WriteLine> genera en la ventana de la consola la expresión que asigna a la propiedad <xref:System.Activities.Statements.WriteLine.Text%2A>. La actividad `ShowWindow` muestra una ventana de [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] como parte de su lógica de ejecución. El objeto <xref:System.Activities.ActivityContext.DataContext%2A> de la ventana incluye las variables declaradas en la secuencia. Los controles de la ventana declarados en la actividad `ShowWindow` usan el enlace de datos para manipular esas variables. Por último, la ventana contiene un control de botón. El evento `Click` para el botón se controla mediante un <xref:System.Activities.ActivityDelegate> denominado `MarkupExtension` que contiene una actividad `CloseWindow`. `MarkUpExtension` invoca la actividad contenida que proporciona, como contexto, cualquier objeto identificado por `x:Name`, así como el <xref:System.Activities.ActivityContext.DataContext%2A> de la ventana contenedora. Por lo tanto, `CloseWindow.InArgument<Window>` se puede enlazar utilizando una expresión que haga referencia al nombre de la ventana.

 La actividad `ShowWindow` deriva de la clase <xref:System.Activities.AsyncCodeActivity%601> para mostrar una ventana de [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] y se completa cuando se cierra la ventana. La propiedad `Window` es de tipo `Func<Window>` que permite crear la ventana a petición para cada ejecución de la actividad. La propiedad `Window` utiliza <xref:System.Xaml.XamlDeferringLoader> para habilitar este modelo de evaluación diferida. `FuncFactoryDeferringLoader` permite capturar un `XamlReader` durante la serialización y, a continuación, leerlo durante la ejecución de la actividad.

 Una actividad bien escrita nunca bloquea el subproceso del programador. Sin embargo, la actividad `ShowWindow` no se puede completar hasta que se cierre la ventana que está mostrando. La actividad `ShowWindow` logra este comportamiento derivándose de <xref:System.Activities.AsyncCodeActivity>, llamando al método <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A> en el método <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> y mostrando la ventana modalmente. El delegado se invoca a través del WPF <xref:System.ServiceModel.InstanceContext.SynchronizationContext%2A>. La actividad `ShowWindow` asigna la propiedad <xref:System.Activities.ActivityContext.DataContext%2A> a la propiedad `Window.DataContext` para proporcionar acceso a los controles enlazados a datos a las variables en el ámbito.

 El último punto de interés de este ejemplo es un objeto <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension> denominado `DelegateActivityExtension`. El método `ProvideValue` de esta extensión de marcado devuelve un delegado que invoca una actividad incrustada. Esta actividad se ejecuta en un entorno que incluye el contexto de datos de [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] y cualquier valor `x:Name` en el ámbito. En el método `GenericInvoke`, este entorno se proporciona a la actividad a través de una extensión <xref:System.Activities.Hosting.SymbolResolver>. Esta extensión se agrega a <xref:System.Activities.WorkflowInvoker> que se utiliza a continuación para invocar la actividad incrustada cada vez que se invoca el delegado de la extensión de marcado.

> [!NOTE]
>  El diseñador predeterminado no admite la actividad ShowWindow; como tal, el archivo ShowWindow.Xaml no se muestra correctamente en el diseñador.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Con Visual Studio 2010, abra el archivo de solución de WPFWFIntegration.sln.

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

3. Presione F5 para ejecutar la solución.

4. Escriba su nombre y apellido en el diálogo.

5. Cierre el diálogo y la consola repetirá su nombre.

> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\WPFWFIntegration`
