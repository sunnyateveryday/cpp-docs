---
title: "Directory Control | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [C++], directory"
  - "directory control routines"
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: 11
author: "corob-msft"
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
# Directory Control
These routines access, modify, and obtain information about the directory structure.  
  
### Directory-Control Routines  
  
|Routine|Use|  
|-------------|---------|  
|[_chdir, _wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Change current working directory|  
|[_chdrive](../c-runtime-library/reference/chdrive.md)|Change current drive|  
|[_getcwd, _wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Get current working directory for default drive|  
|[_getdcwd, _wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Get current working directory for specified drive|  
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Populates a `_diskfree_t` structure with information about a disk drive.|  
|[_getdrive](../c-runtime-library/reference/getdrive.md)|Get current (default) drive|  
|[_getdrives](../c-runtime-library/reference/getdrives.md)|Returns a bitmask representing the currently available disk drives.|  
|[_mkdir, _wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Make new directory|  
|[_rmdir, _wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Remove directory|  
|[_searchenv, _wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [_searchenv_s, _wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Search for given file on specified paths|  
  
## See Also  
 [Run-Time Routines by Category](../c-runtime-library/run-time-routines-by-category.md)   
 [File Handling](../c-runtime-library/file-handling.md)   
 [System Calls](../c-runtime-library/system-calls.md)