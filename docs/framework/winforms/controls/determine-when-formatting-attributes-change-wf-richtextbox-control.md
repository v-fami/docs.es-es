---
title: Procedimiento para determinar cuándo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: a90affde9de36f1c83d5b7c21b40580cdf53402e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972294"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Procedimiento para determinar cuándo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms
Un uso común de los formularios de Windows <xref:System.Windows.Forms.RichTextBox> control es dar formato al texto con atributos tales como las opciones de fuente o estilos de párrafo. La aplicación puede necesitar realizar un seguimiento de los cambios en el formato del texto para mostrar una barra de herramientas, como en muchas aplicaciones de procesamiento de texto.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Para responder a cambios en atributos de formato  
  
1. Escribir código en el <xref:System.Windows.Forms.RichTextBox.SelectionChanged> controlador de eventos para realizar las acciones adecuadas según el valor del atributo. En el ejemplo siguiente se cambia la apariencia de un botón de barra de herramientas, dependiendo del valor de la <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> propiedad. El botón de barra de herramientas sólo se actualizará cuando se mueve el punto de inserción en el control.  
  
     El ejemplo siguiente se da por supuesto un formulario con un <xref:System.Windows.Forms.RichTextBox> control y un <xref:System.Windows.Forms.ToolBar> control que contiene un botón de barra de herramientas. Para obtener más información acerca de las barras de herramientas y botones de barra de herramientas, vea [Cómo: Agregar botones a un Control de barra de herramientas](how-to-add-buttons-to-a-toolbar-control.md).  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
