---
title: "Linker Tools Error LNK2008"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2008"
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
caps.latest.revision: 11
ms.author: "corob"
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
# Linker Tools Error LNK2008
Fixup target is not aligned 'symbol_name'  
  
 LINK found a fixup target in your object file that was not aligned properly.  
  
 This error can be caused by custom secton alignment (for example, #pragma [pack](../c/pack.md)), [align](../cpp/align--c---.md) modifier, or by using assembly language code that modifies secton alignment.  
  
 If your code does not use any of the above, this may be caused by the compiler.