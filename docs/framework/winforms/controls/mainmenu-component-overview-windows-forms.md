---
title: Información general sobre MainMenu (Componente, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: da1b76a7019f364e7463a8345aa80d9a9bd6089e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012794"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Información general sobre MainMenu (Componente, formularios Windows Forms)
> [!IMPORTANT]
>  Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> controles de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan para compatibilidad con versiones anteriores y uso futuro, si elige.  
  
 Los formularios de Windows <xref:System.Windows.Forms.MainMenu> componente muestra un menú en tiempo de ejecución. Todos los submenús del menú principal y los elementos individuales son <xref:System.Windows.Forms.MenuItem> objetos.  
  
## <a name="key-properties"></a>Propiedades clave  
 Un elemento de menú puede designarse como el elemento predeterminado estableciendo la <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> propiedad `true`. El elemento predeterminado aparece en negrita cuando se hace clic en el menú. El elemento de menú <xref:System.Windows.Forms.MenuItem.Checked%2A> propiedad `true` o `false`e indica si se selecciona el elemento de menú. El elemento de menú <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> propiedad personaliza la apariencia del elemento seleccionado: si <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> está establecido en `true`, aparece un botón de radio junto al elemento; si <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> está establecido en `false`, aparece una marca de verificación situada junto al elemento.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
