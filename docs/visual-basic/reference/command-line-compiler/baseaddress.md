---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: e8dfe95ef3385635f5839ecc96047911544a256e
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591453"
---
# <a name="-baseaddress"></a>-baseaddress
Especifica una dirección base predeterminada al crear un archivo DLL.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`address`|Obligatorio. La dirección base del archivo DLL. Esta dirección debe especificarse como un número hexadecimal.|  
  
## <a name="remarks"></a>Comentarios  
 La dirección base predeterminada para un archivo DLL se establece por .NET Framework.  
  
 Tenga en cuenta que la palabra de orden inferior en esta dirección se redondea. Por ejemplo, si especifica 0 x 11110001, se redondea a 0 x 11110000.  
  
 Para completar el proceso de firma de un archivo DLL, utilice el `–R` opción de la herramienta nombre seguro (Sn.exe).  
  
 Esta opción se omite si el destino no es un archivo DLL.  
  
|Para establecer - baseaddress en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en **Avanzado**.<br />4.  Modifique el valor en el **dirección base del archivo DLL:** cuadro. **Nota:**      El **dirección base del archivo DLL:** cuadro es de solo lectura a menos que el destino es un archivo DLL.|  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md))
