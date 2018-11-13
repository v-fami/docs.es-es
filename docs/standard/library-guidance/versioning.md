---
title: Control de versiones y bibliotecas de .NET
description: Procedimientos recomendados para el control de versiones de las bibliotecas de .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: f95c8ade1f91af5c13184b839b327c9397c6fe5a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187863"
---
# <a name="versioning"></a><span data-ttu-id="86cf2-103">Control de versiones</span><span class="sxs-lookup"><span data-stu-id="86cf2-103">Versioning</span></span>

<span data-ttu-id="86cf2-104">Una biblioteca de software rara vez se completa en la versión 1.0.</span><span class="sxs-lookup"><span data-stu-id="86cf2-104">A software library is rarely complete in version 1.0.</span></span> <span data-ttu-id="86cf2-105">Las buenas bibliotecas evolucionan con el tiempo, agregando características, corrigiendo errores y mejorando el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="86cf2-105">Good libraries evolve over time, adding features, fixing bugs and improving performance.</span></span> <span data-ttu-id="86cf2-106">Es importante que pueda lanzar nuevas versiones de una biblioteca de .NET, proporcionando valor adicional con cada versión, sin interrumpir a los usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="86cf2-106">It is important that you can release new versions of a .NET library, providing additional value with each version, without breaking existing users.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="86cf2-107">Cambios importantes</span><span class="sxs-lookup"><span data-stu-id="86cf2-107">Breaking changes</span></span>

<span data-ttu-id="86cf2-108">Para información sobre el control de cambios importantes entre versiones, vea [cambios importantes](./breaking-changes.md).</span><span class="sxs-lookup"><span data-stu-id="86cf2-108">For information about handling breaking changes between versions, see [Breaking changes](./breaking-changes.md).</span></span>

## <a name="version-numbers"></a><span data-ttu-id="86cf2-109">Números de versión</span><span class="sxs-lookup"><span data-stu-id="86cf2-109">Version numbers</span></span>

<span data-ttu-id="86cf2-110">Una biblioteca de .NET tiene muchas maneras de especificar una versión.</span><span class="sxs-lookup"><span data-stu-id="86cf2-110">A .NET library has many ways to specify a version.</span></span> <span data-ttu-id="86cf2-111">Las versiones siguientes son las más importantes:</span><span class="sxs-lookup"><span data-stu-id="86cf2-111">These versions are the most important:</span></span>

### <a name="nuget-package-version"></a><span data-ttu-id="86cf2-112">Versión del paquete NuGet</span><span class="sxs-lookup"><span data-stu-id="86cf2-112">NuGet package version</span></span>

<span data-ttu-id="86cf2-113">La [versión del paquete NuGet](/nuget/reference/package-versioning) se muestra en NuGet.org, el administrador de paquetes NuGet de Visual Studio, y se agrega al código fuente cuando se usa el paquete.</span><span class="sxs-lookup"><span data-stu-id="86cf2-113">The [NuGet package version](/nuget/reference/package-versioning) is displayed on NuGet.org, the Visual Studio NuGet package manager, and is added to source code when the package is used.</span></span> <span data-ttu-id="86cf2-114">La versión del paquete de NuGet es el número de versión que los usuarios suelen ver, y se referirán a ella cuando hablen sobre la versión de una biblioteca que están usando.</span><span class="sxs-lookup"><span data-stu-id="86cf2-114">The NuGet package version is the version number users will commonly see, and they'll refer to it when they talk about the version of a library they're using.</span></span> <span data-ttu-id="86cf2-115">La versión del paquete de NuGet la usa NuGet y no tiene ningún efecto sobre el comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="86cf2-115">The NuGet package version is used by NuGet and has no effect on runtime behavior.</span></span>

```xml
<PackageVersion>1.0.0-alpha1</PackageVersion>
```

<span data-ttu-id="86cf2-116">El identificador del paquete NuGet combinado con la versión de dicho paquete se usa para identificar un paquete en NuGet.</span><span class="sxs-lookup"><span data-stu-id="86cf2-116">The NuGet package identifier combined with the NuGet package version is used to identify a package in NuGet.</span></span> <span data-ttu-id="86cf2-117">Por ejemplo, `Newtonsoft.Json` + `11.0.2`.</span><span class="sxs-lookup"><span data-stu-id="86cf2-117">For example, `Newtonsoft.Json` + `11.0.2`.</span></span> <span data-ttu-id="86cf2-118">Un paquete con un sufijo es un paquete de versión preliminar y tiene un comportamiento especial que lo hace ideal para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="86cf2-118">A package with a suffix is a pre-release package and has special behavior that makes it ideal for testing.</span></span> <span data-ttu-id="86cf2-119">Para más información, consulte [Paquetes de versión preliminar](./nuget.md#pre-release-packages).</span><span class="sxs-lookup"><span data-stu-id="86cf2-119">For more information, see [Pre-release packages](./nuget.md#pre-release-packages).</span></span>

<span data-ttu-id="86cf2-120">Dado que la versión del paquete NuGet es la versión más visible para los desarrolladores, es una buena idea actualizarla mediante [Versionamiento Semántico (SemVer)](https://semver.org/).</span><span class="sxs-lookup"><span data-stu-id="86cf2-120">Because the NuGet package version is the most visible version to developers, it's a good idea to update it using [Semantic Versioning (SemVer)](https://semver.org/).</span></span> <span data-ttu-id="86cf2-121">SemVer indica la importancia de los cambios entre versiones y ayuda a los desarrolladores a tomar una decisión informada a la hora de elegir qué versión se debe usar.</span><span class="sxs-lookup"><span data-stu-id="86cf2-121">SemVer indicates the significance of changes between release and helps developers make an informed decision when choosing what version to use.</span></span> <span data-ttu-id="86cf2-122">Por ejemplo, pasar de `1.0` a `2.0` indica que hay cambios potencialmente importantes.</span><span class="sxs-lookup"><span data-stu-id="86cf2-122">For example, going from `1.0` to `2.0` indicates that there are potentially breaking changes.</span></span>

<span data-ttu-id="86cf2-123">**✔️ ES RECOMENDABLE** usar [SemVer 2.0.0](https://semver.org/) para crear versiones de los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="86cf2-123">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="86cf2-124">**✔️ DEBE** usar la versión del paquete NuGet en la documentación pública, ya que es el número de versión que normalmente verán los usuarios.</span><span class="sxs-lookup"><span data-stu-id="86cf2-124">**✔️ DO** use the NuGet package version in public documentation as it's the version number that users will commonly see.</span></span>

<span data-ttu-id="86cf2-125">**✔️ DEBE** incluir un sufijo de versión preliminar cuando publique un paquete que no sea estable.</span><span class="sxs-lookup"><span data-stu-id="86cf2-125">**✔️ DO** include a pre-release suffix when releasing a non-stable package.</span></span>

> <span data-ttu-id="86cf2-126">Los usuarios deben optar por obtener paquetes de versión preliminar, de forma que comprendan que el paquete no está completo.</span><span class="sxs-lookup"><span data-stu-id="86cf2-126">Users must opt in to getting pre-release packages, so they will understand that the package is not complete.</span></span>

### <a name="assembly-version"></a><span data-ttu-id="86cf2-127">Versión de ensamblado</span><span class="sxs-lookup"><span data-stu-id="86cf2-127">Assembly version</span></span>

<span data-ttu-id="86cf2-128">La versión del ensamblado es lo que CLR usa en tiempo de ejecución para seleccionar qué versión de un ensamblado se debe cargar.</span><span class="sxs-lookup"><span data-stu-id="86cf2-128">The assembly version is what the CLR uses at runtime to select which version of an assembly to load.</span></span> <span data-ttu-id="86cf2-129">La selección de un ensamblado mediante el control de versiones solo se aplica a los ensamblados con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="86cf2-129">Selecting an assembly using versioning only applies to assemblies with a strong name.</span></span>

```xml
<AssemblyVersion>1.0.0.0</AssemblyVersion>
```

<span data-ttu-id="86cf2-130">CLR de Windows .NET Framework exige una coincidencia exacta para cargar un ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="86cf2-130">The Windows .NET Framework CLR demands an exact match to load a strong named assembly.</span></span> <span data-ttu-id="86cf2-131">Por ejemplo, `Libary1, Version=1.0.0.0` se compiló con una referencia a `Newtonsoft.Json, Version=11.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="86cf2-131">For example, `Libary1, Version=1.0.0.0` was compiled with a reference to `Newtonsoft.Json, Version=11.0.0.0`.</span></span> <span data-ttu-id="86cf2-132">.NET Framework solo cargará esa versión exacta `11.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="86cf2-132">The .NET Framework will only load that exact version `11.0.0.0`.</span></span> <span data-ttu-id="86cf2-133">Para cargar una versión diferente en tiempo de ejecución, se debe agregar una redirección de enlace al archivo de configuración de la aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="86cf2-133">To load a different version at runtime, a binding redirect must be added to the .NET application's config file.</span></span>

<span data-ttu-id="86cf2-134">La asignación de nombres seguros junto con la versión de ensamblado permite la [carga de la versión de ensamblado estricta](../../framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="86cf2-134">Strong naming combined with assembly version enables [strict assembly version loading](../../framework/app-domains/assembly-versioning.md).</span></span> <span data-ttu-id="86cf2-135">Aunque la asignación de nombres seguros a una biblioteca una serie de ventajas, suele dar lugar a excepciones en tiempo de ejecución que un ensamblado no se puede encontrar y [requiere que las redirecciones de enlace](../../framework/configure-apps/redirect-assembly-versions.md) en `app.config`/`web.config` se corrijan.</span><span class="sxs-lookup"><span data-stu-id="86cf2-135">While strong naming a library has a number of benefits, it often results in runtime exceptions that an assembly can't be found and [requires binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) in `app.config`/`web.config` to be fixed.</span></span> <span data-ttu-id="86cf2-136">La carga de ensamblados de .NET Core se ha moderada y CLR de .NET Core cargará automáticamente los ensamblados en tiempo de ejecución con una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="86cf2-136">.NET Core assembly loading has been relaxed, and the .NET Core CLR will automatically load assemblies at runtime with a higher version.</span></span>

<span data-ttu-id="86cf2-137">**✔️ ES RECOMENDABLE** que solo incluya una versión principal en AssemblyVersion.</span><span class="sxs-lookup"><span data-stu-id="86cf2-137">**✔️ CONSIDER** only including a major version in the AssemblyVersion.</span></span>

> <span data-ttu-id="86cf2-138">Por ejemplo, tanto Library 1.0 como Library 1.0.1 tienen una AssemblyVersion de `1.0.0.0`, mientras que Library 2.0 tiene una AssemblyVersion de `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="86cf2-138">e.g. Library 1.0 and Library 1.0.1 both have an AssemblyVersion of `1.0.0.0`, while Library 2.0 has AssemblyVersion of `2.0.0.0`.</span></span> <span data-ttu-id="86cf2-139">Cuando la versión del ensamblado cambia con menos frecuencia, reduce las redirecciones de enlace.</span><span class="sxs-lookup"><span data-stu-id="86cf2-139">When the assembly version changes less often, it reduces binding redirects.</span></span>

<span data-ttu-id="86cf2-140">**✔️ ES RECOMENDABLE** mantener sincronizados el número de versión principal de AssemblyVersion y la versión del paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="86cf2-140">**✔️ CONSIDER** keeping the major version number of the AssemblyVersion and the NuGet package version in sync.</span></span>

> <span data-ttu-id="86cf2-141">AssemblyVersion se incluye en algunos mensajes informativos que se muestran al usuario, por ejemplo, el nombre del ensamblado y los nombres de tipo completos del ensamblado en los mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="86cf2-141">The AssemblyVersion is included in some informational messages displayed to the user, e.g. the assembly name and assembly qualified type names in exception messages.</span></span> <span data-ttu-id="86cf2-142">Mantener una relación entre las versiones proporciona más información a los desarrolladores sobre qué versión están usando.</span><span class="sxs-lookup"><span data-stu-id="86cf2-142">Maintaining a relationship between the versions provides more information to developers about which version they are using.</span></span>

<span data-ttu-id="86cf2-143">**❌ NO** tiene una AssemblyVersion fija.</span><span class="sxs-lookup"><span data-stu-id="86cf2-143">**❌ DO NOT** have a fixed AssemblyVersion.</span></span>

> <span data-ttu-id="86cf2-144">Aunque una AssemblyVersion invariable evita la necesidad de redirecciones de enlace, significa que se puede instalar solo una única versión del ensamblado en la memoria caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="86cf2-144">While an unchanging AssemblyVersion avoids the need for binding redirects, it means that only a single version of the assembly can be installed in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="86cf2-145">Además, las aplicaciones que hacen referencia al ensamblado en la memoria caché de ensamblados global se interrumpirán si otra aplicación actualiza el ensamblado de dicha memoria con cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="86cf2-145">Also, the applications that reference the assembly in the GAC will break if another application updates the GAC assembly with breaking changes.</span></span>

### <a name="assembly-file-version"></a><span data-ttu-id="86cf2-146">Versión del archivo de ensamblado</span><span class="sxs-lookup"><span data-stu-id="86cf2-146">Assembly file version</span></span>

<span data-ttu-id="86cf2-147">La versión del archivo de ensamblado se usa para mostrar una versión de archivo en Windows y no tiene ningún efecto sobre el comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="86cf2-147">The assembly file version is used to display a file version in Windows and has no effect on runtime behavior.</span></span> <span data-ttu-id="86cf2-148">La configuración de esta versión es opcional.</span><span class="sxs-lookup"><span data-stu-id="86cf2-148">Setting this version is optional.</span></span> <span data-ttu-id="86cf2-149">Está visible en el cuadro de diálogo Propiedades del archivo en el Explorador de Windows:</span><span class="sxs-lookup"><span data-stu-id="86cf2-149">It's visible in the File Properties dialog in Windows Explorer:</span></span>

```xml
<FileVersion>11.0.2.21924</FileVersion>
```

<span data-ttu-id="86cf2-150">![Explorador de Windows](./media/versioning/win-properties.png "Windows Explorer")</span><span class="sxs-lookup"><span data-stu-id="86cf2-150">![Windows Explorer](./media/versioning/win-properties.png "Windows Explorer")</span></span>

> [!NOTE]
> <span data-ttu-id="86cf2-151">Se produce una advertencia inofensiva de compilación si esta versión no sigue el formato `Major.Minor.Build.Revision`.</span><span class="sxs-lookup"><span data-stu-id="86cf2-151">An innocuous build warning is raised if this version does not follow the format `Major.Minor.Build.Revision`.</span></span> <span data-ttu-id="86cf2-152">La advertencia se puede omitir sin ningún problema.</span><span class="sxs-lookup"><span data-stu-id="86cf2-152">The warning can be safely ignored.</span></span>

<span data-ttu-id="86cf2-153">**✔️ ES RECOMENDABLE**  incluir un número de compilación de integración continua como la revisión AssemblyFileVersion.</span><span class="sxs-lookup"><span data-stu-id="86cf2-153">**✔️ CONSIDER** including a continuous integration build number as the AssemblyFileVersion revision.</span></span>

> <span data-ttu-id="86cf2-154">Por ejemplo, si va a compilar la versión 1.0.0 del proyecto y el número de compilación de integración continua es 99, su AssemblyFileVersion es 1.0.0.99.</span><span class="sxs-lookup"><span data-stu-id="86cf2-154">For example, you are building version 1.0.0 of your project, and the continuous integration build number is 99 so your AssemblyFileVersion is 1.0.0.99.</span></span>

### <a name="assembly-informational-version"></a><span data-ttu-id="86cf2-155">Versión informativa del ensamblado</span><span class="sxs-lookup"><span data-stu-id="86cf2-155">Assembly informational version</span></span>

<span data-ttu-id="86cf2-156">La versión informativa de ensamblado se usa para registrar información de versión adicional y no tiene ningún efecto sobre el comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="86cf2-156">The assembly informational version is used to record additional version information and has no effect on runtime behavior.</span></span> <span data-ttu-id="86cf2-157">La configuración de esta versión es opcional.</span><span class="sxs-lookup"><span data-stu-id="86cf2-157">Setting this version is optional.</span></span> <span data-ttu-id="86cf2-158">Si usa SourceLink, esta versión se establecerá en la compilación con la versión del paquete NuGet más una versión de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="86cf2-158">If you're using SourceLink, this version will be set on build with the NuGet package version plus a source control version.</span></span> <span data-ttu-id="86cf2-159">Por ejemplo, `1.0.0-beta1+204ff0a` incluye el hash de confirmación del código fuente a partir del que se compiló el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="86cf2-159">For example, `1.0.0-beta1+204ff0a` includes the commit hash of the source code the assembly was built from.</span></span> <span data-ttu-id="86cf2-160">Para más información, vea [SourceLink](./sourcelink.md).</span><span class="sxs-lookup"><span data-stu-id="86cf2-160">For more information, see [SourceLink](./sourcelink.md).</span></span>

```xml
<AssemblyInformationalVersion>The quick brown fox jumped over the lazy dog.</AssemblyInformationalVersion>
```

<span data-ttu-id="86cf2-161">**❌ EVITE** establecer usted mismo la versión informativa del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="86cf2-161">**❌ AVOID** setting the assembly informational version yourself.</span></span>

> <span data-ttu-id="86cf2-162">Permita que SourceLink genere automáticamente la versión que contiene los metadatos de control de código fuente y NuGet.</span><span class="sxs-lookup"><span data-stu-id="86cf2-162">Allow SourceLink to automatically generate the version containing NuGet and source control metadata.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="86cf2-163">[Anterior](./publish-nuget-package.md)
[Siguiente](./breaking-changes.md)</span><span class="sxs-lookup"><span data-stu-id="86cf2-163">[Previous](./publish-nuget-package.md)
[Next](./breaking-changes.md)</span></span>