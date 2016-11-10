---
title: "_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
  - C
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
apiname: 
  - _mbsnbcnt_l
  - _mbsnccnt
  - _wcsncnt
  - _strncnt
  - _mbsnccnt_l
  - _mbsnbcnt
apilocation: 
  - msvcrt.dll
  - msvcr80.dll
  - msvcr90.dll
  - msvcr100.dll
  - msvcr100_clr0400.dll
  - msvcr110.dll
  - msvcr110_clr0400.dll
  - msvcr120.dll
  - msvcr120_clr0400.dll
  - ucrtbase.dll
  - api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
ms.assetid: 2a022e9e-a307-4acb-a66b-e56e5357f848
caps.latest.revision: 22
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
Returns the number of characters or bytes within a specified count.  
  
> [!IMPORTANT]
>  `_mbsnbcnt`, `_mbsnbcnt_l`, `_mbsnccnt`, and `_mbsnccnt_l` cannot be used in applications that execute in the Windows Runtime. For more information, see [CRT functions not supported with /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
size_t _strncnt(  
   const char *str,  
   size_t count  
);  
size_t _wcsncnt(  
   const wchar_t *str,  
   size_t count  
);  
size_t _mbsnbcnt(  
   const unsigned char *str,  
   size_t count   
);  
size_t _mbsnbcnt_l(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
size_t _mbsnccnt(  
   const unsigned char *str,  
   size_t count  
);  
size_t _mbsnccnt_l(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
  
```  
  
#### Parameters  
 `str`  
 String to be examined.  
  
 `count`  
 Number of characters or bytes to be examined in `str`.  
  
 `locale`  
 Locale to use.  
  
## Return Value  
 `_mbsnbcnt` and `_mbsnbcnt_l` return the number of bytes found in the first `count` of multibyte characters of `str`. `_mbsnccnt` and `_mbsnccnt_l` return the number of characters found in the first `count` of bytes of `str`. If a NULL character is encountered before the examination of `str` has completed, they return the number of bytes or characters found before the NULL character. If `str` consists of fewer than `count` characters or bytes, they return the number of characters or bytes in the string. If `count` is less than zero, they return 0. In previous versions, these functions had a return value of type `int` rather than `size_t`.  
  
 `_strncnt` returns the number of characters in the first `count` bytes of the single-byte string `str`. `_wcsncnt` returns the number of characters in the first `count` wide characters of the wide-character string `str`.  
  
## Remarks  
 `_mbsnbcnt` and `_mbsnbcnt_l` count the number of bytes found in the first `count` of multibyte characters of `str`. `_mbsnbcnt` and `_mbsnbcnt_l` replace `mtob` and should be used in place of `mtob`.  
  
 `_mbsnccnt` and `_mbsnccnt_l` count the number of characters found in the first `count` of bytes of `str`. If `_mbsnccnt` and `_mbsnccnt_l` encounter a NULL in the second byte of a double-byte character, the first byte is also considered to be NULL and is not included in the returned count value. `_mbsnccnt` and `_mbsnccnt_l` replace `btom` and should be used in place of `btom`.  
  
 If `str` is a null pointer or is `count` is 0, these functions invoke the invalid parameter handler as described in [Parameter Validation](../VS_visualcpp/Parameter-Validation.md), `errno` is set to `EINVAL`, and the function returns 0.  
  
 The output value is affected by the setting of the `LC_CTYPE` category setting of the locale; see [setlocale](../VS_visualcpp/setlocale--_wsetlocale.md) for more information. The versions of these functions without the `_l` suffix use the current locale for this locale-dependent behavior; the versions with the `_l` suffix are identical except that they use the locale parameter passed in instead. For more information, see [Locale](../VS_visualcpp/Locale.md).  
  
### Generic-Text Routine Mappings  
  
|Routine|_UNICODE and _MBCS not defined|_MBCS defined|_UNICODE defined|  
|-------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsnbcnt`|`_strncnt`|`_mbsnbcnt`|`_wcsncnt`|  
|`_tcsnccnt`|`_strncnt`|`_mbsnbcnt`|`n/a`|  
|`_wcsncnt`|`n/a`|`n/a`|`_mbsnbcnt`|  
|`_wcsncnt`|`n/a`|`n/a`|`_mbsnccnt`|  
|`n/a`|`n/a`|`_mbsnbcnt_l`|`_mbsnccnt_l`|  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|`_mbsnbcnt`|<mbstring.h>|  
|`_mbsnbcnt_l`|<mbstring.h>|  
|`_mbsnccnt`|<mbstring.h>|  
|`_mbsnccnt_l`|<mbstring.h>|  
|`_strncnt`|<tchar.h>|  
|`_wcsncnt`|<tchar.h>|  
  
 For more compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md).  
  
## Example  
  
```  
// crt_mbsnbcnt.c  
  
#include  <mbstring.h>  
#include  <stdio.h>  
  
int main( void )  
{  
   unsigned char str[] = "This is a multibyte-character string.";  
   unsigned int char_count, byte_count;  
   char_count = _mbsnccnt( str, 10 );  
   byte_count = _mbsnbcnt( str, 10 );  
   if ( byte_count - char_count )  
      printf( "The first 10 characters contain %d multibyte characters\n", char_count );  
   else  
      printf( "The first 10 characters are single-byte.\n");  
}  
```  
  
## Output  
  
```  
The first 10 characters are single-byte.  
```  
  
## .NET Framework Equivalent  
 Not applicable. To call the standard C function, use `PInvoke`. For more information, see [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## See Also  
 [String Manipulation](../VS_visualcpp/String-Manipulation--CRT-.md)   
 [Locale](../VS_visualcpp/Locale.md)   
 [Interpretation of Multibyte-Character Sequences](../VS_visualcpp/Interpretation-of-Multibyte-Character-Sequences.md)   
 [_mbsnbcat, _mbsnbcat_l](../VS_visualcpp/_mbsnbcat--_mbsnbcat_l.md)