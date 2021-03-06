---
title: "Editing Parts of an Image (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Image editor [C++], editing images"
  - "Clipboard [C++], pasting"
  - "images [C++], editing"
  - "images [C++], deleting selected parts"
  - "images [C++], copying selected parts"
  - "images [C++], moving selected parts"
  - "images [C++], dragging and replicating selected parts"
  - "images [C++], pasting into"
  - "graphics [C++], editing"
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Editing Parts of an Image (Image Editor for Icons)
You can perform standard editing operations — cutting, copying, clearing, and moving — on a [selection](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), whether the selection is the entire image or just a part of it. Because the Image editor uses the Windows Clipboard, you can transfer images between the Image editor and other applications for Windows.  
  
 In addition, you can resize the selection, whether it includes the entire image or just a part.  
  
### To cut the current selection and move it to the clipboard  
  
1.  Click **Cut** on the **Edit** menu.  
  
### To copy the selection  
  
1.  Position the pointer inside the selection border or anywhere on it except the sizing handles.  
  
2.  Hold down the **CTRL** key as you drag the selection to a new location. The area of the original selection is unchanged.  
  
3.  To copy the selection into the image at its current location, click outside the selection cursor.  
  
### To paste the clipboard contents into an image  
  
1.  From the **Edit** menu, choose **Paste**.  
  
     The Clipboard contents, surrounded by the selection border, appear in the upper-left corner of the pane.  
  
2.  Position the pointer within the selection border and drag the image to the desired location on the image.  
  
3.  To anchor the image at its new location, click outside of the selection border.  
  
### To delete the current selection without moving it to the clipboard  
  
1.  From the **Edit** menu, choose **Delete**.  
  
     The original area of the selection is filled with the current background color.  
  
    > [!NOTE]
    >  You can access the Cut, Copy, Paste, and Delete commands by right clicking in the Resource View window.  
  
### To move the selection  
  
1.  Position the pointer inside the selection border or anywhere on it except the sizing handles.  
  
2.  Drag the selection to its new location.  
  
3.  To anchor the selection in the image at its new location, click outside the selection border.  
  
 For more information on drawing with a selection, see [Creating a Custom Brush](../windows/creating-a-custom-brush-image-editor-for-icons.md).  
  
 For information on adding resources to managed projects, please see [Resources in Desktop Apps](https://msdn.microsoft.com/library/f45fce5x.aspx) in the *.NET Framework Developer's Guide.* For information on manually adding resource files to managed projects, accessing resources, displaying static resources, and assigning resource strings to properties, see [Creating Resource Files for Desktop Apps](https://msdn.microsoft.com/library/xbx3z216.aspx). For information on globalization and localization of resources in managed apps, see [Globalizing and Localizing .NET Framework Applications](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Requirements  
  
 None  
  
## See Also  
 [Accelerator Keys](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../windows/image-editor-for-icons.md)

