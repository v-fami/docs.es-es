---
title: -referencia (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 2394a23ddd59d09ce53c78fc4486fc5bae9e8516
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583360"
---
# <a name="-reference-visual-basic"></a>-referencia (Visual Basic)
Hace que el compilador para que estén disponibles para el proyecto que se está compilando información de tipo de los ensamblados especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`fileList`|Obligatorio. Lista delimitada por comas de nombres de archivos de ensamblado. Si el nombre de archivo contiene un espacio, escríbalo entre comillas.|  
  
## <a name="remarks"></a>Comentarios  
 Los archivos importados deben contener metadatos de ensamblado. Solo los tipos públicos son visibles fuera del ensamblado. El [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opción importa metadatos de un módulo.  
  
 Si hace referencia a un ensamblado (ensamblado A) que a su vez hace referencia a otro ensamblado (ensamblado B), debe hacer referencia al ensamblado B si:  
  
- Un tipo del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.  
  
- Se invoca a un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.  
  
 Use [- libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.  
  
 Para que el compilador reconozca un tipo en un ensamblado (no un módulo), debe forzarse para resolver el tipo. Un ejemplo de cómo se puede hacer es definir una instancia del tipo. Hay otras formas resolver nombres de tipo en un ensamblado para el compilador. Por ejemplo, si se hereda de un tipo en un ensamblado, tipo conoce el nombre, a continuación, se convierte en el compilador.  
  
 El archivo de respuesta Vbc.rsp, que hace referencia normalmente usan ensamblados de .NET Framework, se usa de forma predeterminada. Usar `-noconfig` si no desea que el compilador utilice Vbc.rsp.  
  
 La forma abreviada de `-reference` es `/r`.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente compila el archivo de código fuente `Input.vb` y hacer referencia a ensamblados de `Metad1.dll` y `Metad2.dll` para producir `Out.exe`.  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
