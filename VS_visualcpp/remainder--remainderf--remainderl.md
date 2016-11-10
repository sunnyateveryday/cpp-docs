---
title: "remainder, remainderf, remainderl"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
apiname: 
  - remainderl
  - remainder
  - remainderf
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
  - api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
caps.latest.revision: 6
manager: ghogen
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# remainder, remainderf, remainderl
Computes the remainder of the quotient of two floating-point values, rounded to the nearest integral value.  
  
## Syntax  
  
```  
double remainder(   
   double numer,  
   double denom  
);  
float remainder(   
   float numer,  
   float denom  
); /* C++ only */  
long double remainder(   
   long double numer,  
   long double denom  
); /* C++ only */  
float remainderf(   
   float numer,  
   float denom  
);  
long double remainderl(   
   long double numer,  
   long double denom  
);  
  
```  
  
#### Parameters  
 `numer`  
 The numerator.  
  
 `denom`  
 The denominator.  
  
## Return Value  
 The floating-point remainder of `x` / `y`. If the value of `y` is 0.0, `remainder` returns a quiet NaN. For information about the representation of a quiet NaN by the `printf` family, see [printf, _printf_l, wprintf, _wprintf_l](../VS_visualcpp/printf--_printf_l--wprintf--_wprintf_l.md).  
  
## Remarks  
 The `remainder` function calculates the floating-point remainder `r` of `x` / `y` such that `x` = `n` * `y` + `r`, where `n` is the integer nearest in value to `x` / `y` and `n` is even whenever &#124; `n` - `x` / `y` &#124; = 1/2. When `r` = 0, `r` has the same sign as `x`.  
  
 Because C++ allows overloading, you can call overloads of `remainder` that take and return `float` or `long double` values. In a C program, `remainder` always takes two doubles and returns a double.  
  
## Requirements  
  
|Function|Required header|  
|--------------|---------------------|  
|`remainder`, `remainderf`, `remainderl`|<math.h>|  
  
 For compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md).  
  
## Example  
  
```c  
// crt_remainder.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = remainder(w, x);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
}  
```  
  
 **The remainder of -10.00 / 3.00 is -1.000000**   
## .NET Framework Equivalent  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## See Also  
 [Floating-Point Support](../VS_visualcpp/Floating-Point-Support.md)   
 [ldiv, lldiv](../VS_visualcpp/ldiv--lldiv.md)   
 [imaxdiv](../VS_visualcpp/imaxdiv.md)   
 [fmod, fmodf](../VS_visualcpp/fmod--fmodf.md)   
 [remquo, remquof, remquol](../VS_visualcpp/remquo--remquof--remquol.md)