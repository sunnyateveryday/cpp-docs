---
title: "-P (Preprocess to a File)"
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
  - "VC.Project.VCCLCompilerTool.GeneratePreprocessedFile"
  - "/p"
  - "VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/P compiler option [C++]"
  - "-P compiler option [C++]"
  - "P compiler option [C++]"
  - "output files, preprocessor"
  - "preprocessing output files"
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
caps.latest.revision: 12
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
# /P (Preprocess to a File)
Preprocesses C and C++ source files and writes the preprocessed output to a file.  
  
## Syntax  
  
```  
/P  
```  
  
## Remarks  
 The file has the same base name as the source file and an .i extension. In the process, all preprocessor directives are carried out, macro expansions are performed, and comments are removed. To preserve comments in the preprocessed output, use the [/C (Preserve Comments During Preprocessing)](../buildref/-c--preserve-comments-during-preprocessing-.md) option along with **/P**.  
  
 **/P** adds `#line` directives to the output, at the beginning and end of each included file and around lines removed by preprocessor directives for conditional compilation. These directives renumber the lines of the preprocessed file. As a result, errors generated during later stages of processing refer to the line numbers of the original source file rather than lines in the preprocessed file. To suppress the generation of `#line` directives, use [/EP (Preprocess to stdout Without #line Directives)](../buildref/-ep--preprocess-to-stdout-without-sharpline-directives-.md) as well as **/P**.  
  
 The **/P** option suppresses compilation. It does not produce an .obj file, even if you use [/Fo (Object File Name)](../buildref/-fo--object-file-name-.md). You must resubmit the preprocessed file for compilation. **/P** also suppresses the output files from the **/FA**, **/Fa**, and **/Fm** options. For more information, see [/FA, /Fa (Listing File)](../buildref/-fa---fa--listing-file-.md) and [/Fm (Name Mapfile)](../buildref/-fm--name-mapfile-.md).  
  
### To set this compiler option in the Visual Studio development environment  
  
1.  Open the project's **Property Pages** dialog box. For details, see [How to: Open Project Property Pages](../notintoc/how-to--open-project-property-pages.md).  
  
2.  Click the **C/C++** folder.  
  
3.  Click the **Preprocessor** property page.  
  
4.  Modify the **Generate Preprocessed File** property.  
  
### To set this compiler option programmatically  
  
-   See \<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile*>.  
  
## Example  
 The following command line preprocesses `ADD.C`, preserves comments, adds `#line` directives, and writes the result to a file, `ADD.I`:  
  
```  
CL /P /C ADD.C  
```  
  
## See Also  
 [Compiler Options](../buildref/compiler-options.md)   
 [Setting Compiler Options](../buildref/setting-compiler-options.md)   
 [/Fi (Preprocess Output File Name)](../buildref/-fi--preprocess-output-file-name-.md)