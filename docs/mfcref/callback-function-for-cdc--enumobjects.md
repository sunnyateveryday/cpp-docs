---
title: "Callback Function for CDC::EnumObjects"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "Callback Function for CDC::EnumObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "callback functions, for CDC::EnumObjects"
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
caps.latest.revision: 8
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
# Callback Function for CDC::EnumObjects
The *ObjectFunc* name is a placeholder for the application-supplied function name.  
  
## Syntax  
  
```  
  
      int CALLBACK EXPORT ObjectFunc(   
   LPSTR lpszLogObject,   
   LPSTR* lpData    
);  
```  
  
#### Parameters  
 *lpszLogObject*  
 Points to a [LOGPEN](../mfcref/logpen-structure.md) or [LOGBRUSH](../mfcref/logbrush-structure.md) data structure that contains information about the logical attributes of the object.  
  
 `lpData`  
 Points to the application-supplied data passed to the `EnumObjects` function.  
  
## Return Value  
 The callback function returns an `int`. The value of this return is user-defined. If the callback function returns 0, `EnumObjects` stops enumeration early.  
  
## Remarks  
 The actual name must be exported.  
  
## Requirements  
 **Header:** afxwin.h  
  
## See Also  
 [Structures, Styles, Callbacks, and Message Maps](../mfcref/structures--styles--callbacks--and-message-maps.md)   
 [CDC::EnumObjects](../Topic/CDC::EnumObjects.md)