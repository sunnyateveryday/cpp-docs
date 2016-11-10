---
title: "CImage Class"
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
ms.topic: reference
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
caps.latest.revision: 15
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
# CImage Class
`CImage` provides enhanced bitmap support, including the ability to load and save images in JPEG, GIF, BMP, and Portable Network Graphics (PNG) formats.  
  
> [!IMPORTANT]
>  This class and its members cannot be used in applications that execute in the Windows Runtime.  
  
## Syntax  
  
```  
  
class CImage  
  
```  
  
## Members  
  
### Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CImage::CImage](#cimage__cimage)|The constructor.|  
  
### Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CImage::AlphaBlend](#cimage__alphablend)|Displays bitmaps that have transparent or semitransparent pixels.|  
|[CImage::Attach](#cimage__attach)|Attaches an                                         `HBITMAP` to a                                         `CImage` object. Can be used with either non-DIB section bitmaps or DIB section bitmaps.|  
|[CImage::BitBlt](#cimage__bitblt)|Copies a bitmap from the source device context to this current device context.|  
|[CImage::Create](#cimage__create)|Creates a DIB section bitmap and attaches it to the previously constructed                                         `CImage` object.|  
|[CImage::CreateEx](#cimage__createex)|Creates a DIB section bitmap (with additional parameters) and attaches it to the previously constructed                                         `CImage` object.|  
|[CImage::Destroy](#cimage__destroy)|Detaches the bitmap from the                                         `CImage` object and destroys the bitmap.|  
|[CImage::Detach](#cimage__detach)|Detaches the bitmap from a                                         `CImage` object.|  
|[CImage::Draw](#cimage__draw)|Copies a bitmap from a source rectangle into a destination rectangle.                                         **Draw** stretches or compresses the bitmap to fit the dimensions of the destination rectangle, if necessary, and handles alpha blending and transparent colors.|  
|[CImage::GetBits](#cimage__getbits)|Retrieves a pointer to the actual pixel values of the bitmap.|  
|[CImage::GetBPP](#cimage__getbpp)|Retrieves the bits per pixel.|  
|[CImage::GetColorTable](#cimage__getcolortable)|Retrieves red, green, blue (RGB) color values from a range of entries in the color table.|  
|[CImage::GetDC](#cimage__getdc)|Retrieves the device context into which the current bitmap is selected.|  
|[CImage::GetExporterFilterString](#cimage__getexporterfilterstring)|Finds the available image formats and their descriptions.|  
|[CImage::GetHeight](#cimage__getheight)|Retrieves the height of the current image in pixels.|  
|[CImage::GetImporterFilterString](#cimage__getimporterfilterstring)|Finds the available image formats and their descriptions.|  
|[CImage::GetMaxColorTableEntries](#cimage__getmaxcolortableentries)|Retrieves the maximum number of entries in the color table.|  
|[CImage::GetPitch](#cimage__getpitch)|Retrieves the pitch of the current image, in bytes.|  
|[CImage::GetPixel](#cimage__getpixel)|Retrieves the color of the pixel specified by                                         *x* and                                         *y*.|  
|[CImage::GetPixelAddress](#cimage__getpixeladdress)|Retrieves the address of a given pixel.|  
|[CImage::GetTransparentColor](#cimage__gettransparentcolor)|Retrieves the position of the transparent color in the color table.|  
|[CImage::GetWidth](#cimage__getwidth)|Retrieves the width of the current image in pixels.|  
|[CImage::IsDIBSection](#cimage__isdibsection)|Determines if the attached bitmap is a DIB section.|  
|[CImage::IsIndexed](#cimage__isindexed)|Indicates that a bitmap's colors are mapped to an indexed palette.|  
|[CImage::IsNull](#cimage__isnull)|Indicates if a source bitmap is currently loaded.|  
|[CImage::IsTransparencySupported](#cimage__istransparencysupported)|Indicates whether the application supports transparent bitmaps and was compiled for Windows 2000 or later.|  
|[CImage::Load](#cimage__load)|Loads an image from the specified file.|  
|[CImage::LoadFromResource](#cimage__loadfromresource)|Loads an image from the specified resource.|  
|[CImage::MaskBlt](#cimage__maskblt)|Combines the color data for the source and destination bitmaps using the specified mask and raster operation.|  
|[CImage::PlgBlt](#cimage__plgblt)|Performs a bit-block transfer from a rectangle in a source device context into a parallelogram in a destination device context.|  
|[CImage::ReleaseDC](#cimage__releasedc)|Releases the device context that was retrieved with                                         [CImage::GetDC](#cimage__getdc).|  
|[CImage::ReleaseGDIPlus](#cimage__releasegdiplus)|Releases resources used by GDI+. Must be called to free resources created by a global                                         `CImage` object.|  
|[CImage::Save](#cimage__save)|Saves an image as the specified type.                                         **Save** cannot specify image options.|  
|[CImage::SetColorTable](#cimage__setcolortable)|Sets red, green, blue RGB) color values in a range of entries in the color table of the DIB section.|  
|[CImage::SetPixel](#cimage__setpixel)|Sets the pixel at the specified coordinates to the specified color.|  
|[CImage::SetPixelIndexed](#cimage__setpixelindexed)|Sets the pixel at the specified coordinates to the color at the specified index of the palette.|  
|[CImage::SetPixelRGB](#cimage__setpixelrgb)|Sets the pixel at the specified coordinates to the specified red, green, blue (RGB) value.|  
|[CImage::SetTransparentColor](#cimage__settransparentcolor)|Sets the index of the color to be treated as transparent. Only one color in a palette can be transparent.|  
|[CImage::StretchBlt](#cimage__stretchblt)|Copies a bitmap from a source rectangle into a destination rectangle, stretching or compressing the bitmap to fit the dimensions of the destination rectangle, if necessary.|  
|[CImage::TransparentBlt](#cimage__transparentblt)|Copies a bitmap with transparent color from the source device context to this current device context.|  
  
### Public Operators  
  
|Name|Description|  
|----------|-----------------|  
|[CImage::operator HBITMAP](#cimage__operator_hbitmap)|Returns the Windows handle attached to the                                         `CImage` object.|  
  
## Remarks  
 `CImage` takes bitmaps that are either device-independent bitmap (DIB) sections or not; however, you can use                 [Create](#cimage__create) or                 [CImage::Load](#cimage__load) with only DIB sections. You can attach a non-DIB section bitmap to a                 `CImage` object using                 [Attach](#cimage__attach), but then you cannot use the following                 `CImage` methods, which support only DIB section bitmaps:  
  
-   [GetBits](#cimage__getbits)  
  
-   [GetColorTable](#cimage__getcolortable)  
  
-   [GetMaxColorTableEntries](#cimage__getmaxcolortableentries)  
  
-   [GetPitch](#cimage__getpitch)  
  
-   [GetPixelAddress](#cimage__getpixeladdress)  
  
-   [IsIndexed](#cimage__isindexed)  
  
-   [SetColorTable](#cimage__setcolortable)  
  
 To determine if an attached bitmap is a DIB section, call                 [IsDibSection](#cimage__isdibsection)**.**  
  
> [!NOTE]
>  **Note** In Visual Studio .NET 2003, this class keeps a count of the number of                     `CImage` objects created. Whenever the count goes to 0, the function                     [GdiplusShutdown](_gdiplus_func_gdiplusshutdown_) is automatically called to release resources used by GDI+. This ensures that any                     `CImage` objects created directly or indirectly by DLLs are always destroyed properly and that                     **GdiplusShutdown** is not called from                     `DllMain`.  
  
> [!NOTE]
>  Using global                     `CImage` objects in a DLL is not recommended. If you need to use a global                     `CImage` object in a DLL, call                     [CImage::ReleaseGDIPlus](#cimage__releasegdiplus) to explicitly release resources used by GDI+.  
  
 `CImage` cannot be selected into a new                 [CDC](../VS_visualcpp/CDC-Class.md).                 `CImage` creates its own                 **HDC** for the image. Because an                 `HBITMAP` can only be selected into one                 **HDC** at a time, the                 `HBITMAP` associated with the                 `CImage` cannot be selected into another                 **HDC**. If you need a                 `CDC`, retrieve the                 **HDC** from the                 `CImage` and give it to                 [CDC::FromHandle](../Topic/CDC::FromHandle.md).  
  
## Example  
 [!CODE [NVC_ATLMFC_Utilities#70](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#70)]  
  
 When you use                     `CImage` in an MFC project, note which member functions in your project expect a pointer to a                     [CBitmap](../VS_visualcpp/CBitmap-Class.md) object. If you want to use                     `CImage` with such a function, like                     [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md), use                     [CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md), pass it your                     `CImage` `HBITMAP`, and use the returned                     `CBitmap*`.  
  
## Example  
 [!CODE [NVC_ATLMFC_Utilities#71](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#71)]  
  
 Through                     `CImage`, you have access to the actual bits of a DIB section. You can use a                     `CImage` object anywhere you previously used a Win32 HBITMAP or DIB section.  
  
> [!NOTE]
>  The following                         `CImage` methods have limitations on their use:  
  
|Method|Limitation|  
|------------|----------------|  
|[PlgBlt](#cimage__plgblt)|Works with only Windows NT 4.0 or later. Will not work on applications running on Windows 95/98 or later.|  
|[MaskBlt](#cimage__maskblt)|Works with only Windows NT 4.0 or later. Will not work on applications running on Windows 95/98 or later.|  
|[AlphaBlend](#cimage__alphablend)|Works with only Windows 2000, Windows 98, and later systems.|  
|[TransparentBlt](#cimage__transparentblt)|Works with only Windows 2000, Windows 98, and later systems.|  
|[Draw](#cimage__draw)|Supports transparency with only Windows 2000, Windows 98, and later systems.|  
  
 See                     [CImage Limitations with Earlier Operating Systems](../VS_visualcpp/CImage-Limitations-with-Earlier-Operating-Systems.md) for more detailed information about the limitations on these methods.  
  
 You can use                     `CImage` from either MFC or ATL.  
  
> [!NOTE]
>  When you create a project using                         `CImage`, you must define                         `CString` before you include                         `atlimage.h`. If your project uses ATL without MFC, include                         `atlstr.h` before you include                         `atlimage.h`. If your project uses MFC (or if it is an ATL project with MFC support), include                         `afxstr.h` before you include                         `atlimage.h`.  
>   
>  Likewise, you must include                         `atlimage.h` before you include                         `atlimpl.cpp`. To accomplish this easily, include                         `atlimage.h` in your                         `stdafx.h`.  
  
## Requirements  
 **Header:** atlimage.h  
  
##  <a name="cimage__alphablend"></a>  CImage::AlphaBlend  
 Displays bitmaps that have transparent or semitransparent pixels.  
  
```  
  
BOOL AlphaBlend(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   BYTE   
bSrcAlpha  
 = 0xff,  
   BYTE   
bBlendOp  
 = AC_SRC_OVER   
) const throw( );  
BOOL AlphaBlend(  
   HDC   
hDestDC  
,  
   const POINT&   
pointDest  
,  
   BYTE   
bSrcAlpha  
 = 0xff,  
   BYTE   
bBlendOp  
 = AC_SRC_OVER   
) const throw( );  
BOOL AlphaBlend(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   int   
nDestWidth  
,  
   int   
nDestHeight  
,  
   int   
xSrc  
,  
   int   
ySrc  
,  
   int   
nSrcWidth  
,  
   int   
nSrcHeight  
,  
   BYTE   
bSrcAlpha  
 = 0xff,  
   BYTE   
bBlendOp  
 = AC_SRC_OVER   
);  
BOOL AlphaBlend(  
   HDC   
hDestDC  
,  
   const RECT&   
rectDest  
,  
   const RECT&   
rectSrc  
,  
   BYTE   
bSrcAlpha  
 = 0xff,  
   BYTE   
bBlendOp  
 = AC_SRC_OVER   
);  
  
```  
  
### Parameters  
 `hDestDC`  
 Handle to the destination device context.  
  
 `xDest`  
 The x-coordinate, in logical units, of the upper left corner of the destination rectangle.  
  
 `yDest`  
 The y-coordinate, in logical units, of the upper left corner of the destination rectangle.  
  
 *bSrcAlpha*  
 An alpha transparency value to be used on the entire source bitmap. The default 0xff (255) assumes that your image is opaque, and that you want to use per-pixel alpha values only.  
  
 `bBlendOp`  
 The alpha-blending function for source and destination bitmaps, a global alpha value to be applied to the entire source bitmap, and format information for the source bitmap. The source and destination blend functions are currently limited to                                 **AC_SRC_OVER**.  
  
 `pointDest`  
 A reference to a                                 [POINT](http://msdn.microsoft.com/library/windows/desktop/dd162805) structure that identifies the upper left corner of the destination rectangle, in logical units.  
  
 `nDestWidth`  
 The width, in logical units, of the destination rectangle.  
  
 `nDestHeight`  
 The height, in logical units, of the destination rectangle.  
  
 `xSrc`  
 The logical x-coordinate of the upper left corner of the source rectangle.  
  
 `ySrc`  
 The logical y-coordinate of the upper left corner of the source rectangle.  
  
 `nSrcWidth`  
 The width, in logical units, of the source rectangle.  
  
 `nSrcHeight`  
 The height, in logical units, of the source rectangle.  
  
 `rectDest`  
 A reference to a                                 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure, identifying the destination.  
  
 `rectSrc`  
 A reference to a                                 `RECT` structure, identifying the source.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 Alpha-blend bitmaps support color blending on a per-pixel basis.  
  
 When                         `bBlendOp` is set to the default of                         **AC_SRC_OVER**, the source bitmap is placed over the destination bitmap based on the alpha values of the source pixels.  
  
 This method is applicable to Microsoft Windows 2000, Windows 98, and later systems. See                         [AlphaBlend](http://msdn.microsoft.com/library/windows/desktop/dd183351) in the                         Windows SDK and                         [CImage Limitations with Earlier Operating Systems](../VS_visualcpp/CImage-Limitations-with-Earlier-Operating-Systems.md) for more detailed information.  
  
##  <a name="cimage__attach"></a>  CImage::Attach  
 Attaches                 `hBitmap` to a                 `CImage` object.  
  
```  
  
void Attach(  
   HBITMAP   
hBitmap,   
   DIBOrientation   
eOrientation  
 = DIBOR_DEFAULT  
) throw();  
  
```  
  
### Parameters  
 `hBitmap`  
 A handle to an                                 `HBITMAP`.  
  
 *eOrientation*  
 Specifies the orientation of the bitmap. Can be one of the following:  
  
-   **DIBOR_DEFAULT** The orientation of the bitmap is determined by the operating system. However, this may not always have the intended results on all operating systems. For more information on this, see the following Knowledge Base article (                                        **Q186586**): PRB: GetObject() Always Returns Positive Height For DIB Sections.  
  
-   **DIBOR_BOTTOMUP** The lines of the bitmap are in reverse order. This causes                                         [CImage::GetBits](#cimage__getbits) to return a pointer near the end of the bitmap buffer and                                         [CImage::GetPitch](#cimage__getpitch) to return a negative number.  
  
-   **DIBOR_TOPDOWN**  The lines of the bitmap are in top to bottom order. This causes                                         [CImage::GetBits](#cimage__getbits) to return a pointer to the first byte of the bitmap buffer and                                         [CImage::GetPitch](#cimage__getpitch) to return a positive number.  
  
### Remarks  
 The bitmap can be either a non-DIB section bitmap or a DIB section bitmap. See                         [IsDIBSection](#cimage__isdibsection) for a list of methods that you can use only with DIB section bitmaps.  
  
##  <a name="cimage__bitblt"></a>  CImage::BitBlt  
 Copies a bitmap from the source device context to this current device context.  
  
```  
  
BOOL BitBlt(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
BOOL BitBlt(  
   HDC   
hDestDC  
,  
   const POINT&   
pointDest  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
BOOL BitBlt(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   int   
nDestWidth  
,  
   int   
nDestHeight  
,  
   int   
xSrc  
,  
   int   
ySrc  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
BOOL BitBlt(  
   HDC   
hDestDC  
,  
   const RECT&   
rectDest  
,  
   const POINT&   
pointSrc  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
  
```  
  
### Parameters  
 `hDestDC`  
 The destination                                 **HDC**.  
  
 `xDest`  
 The logical x-coordinate of the upper left corner of the destination rectangle.  
  
 `yDest`  
 The logical y-coordinate of the upper left corner of the destination rectangle.  
  
 `dwROP`  
 The raster operation to be performed. Raster-operation codes define exactly how to combine the bits of the source, the destination, and the pattern (as defined by the currently selected brush) to form the destination. See                                 [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) in the                                 Windows SDK for a list of other raster-operation codes and their descriptions.  
  
 `pointDest`  
 A                                 [POINT](http://msdn.microsoft.com/library/windows/desktop/dd162805) structure indicating the upper left corner of the destination rectangle.  
  
 `nDestWidth`  
 The width, in logical units, of the destination rectangle.  
  
 `nDestHeight`  
 The height, in logical units, of the destination rectangle.  
  
 `xSrc`  
 The logical x-coordinate of the upper left corner of the source rectangle.  
  
 `ySrc`  
 The logical y-coordinate of the upper left corner of the source rectangle.  
  
 `rectDest`  
 A                                 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure indicating the destination rectangle.  
  
 `pointSrc`  
 A                                 **POINT** structure indicating the upper left corner of the source rectangle.  
  
### Return Value  
 Nonzero if successful; otherwise zero.  
  
### Remarks  
 For more information, see                         [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) in the                         Windows SDK.  
  
##  <a name="cimage__cimage"></a>  CImage::CImage  
 Constructs a                 `CImage` object.  
  
```  
  
CImage( ) throw( );  
  
```  
  
### Remarks  
 Once you have constructed the object, call                         [Create](#cimage__create),                         [Load](#cimage__load),                         [LoadFromResource](#cimage__loadfromresource), or                         [Attach](#cimage__attach) to attach a bitmap to the object.  
  
 **Note** In Visual Studio, this class keeps a count of the number of                         `CImage` objects created. Whenever the count goes to 0, the function                         [GdiplusShutdown](_gdiplus_func_gdiplusshutdown_) is automatically called to release resources used by GDI+. This ensures that any                         `CImage` objects created directly or indirectly by DLLs are always destroyed properly and that                         **GdiplusShutdown** is not called from DllMain.  
  
 Using global                         `CImage` objects in a DLL is not recommended. If you need to use a global                         `CImage` object in a DLL, call                         [CImage::ReleaseGDIPlus](#cimage__releasegdiplus) to explicitly release resources used by GDI+.  
  
##  <a name="cimage__create"></a>  CImage::Create  
 Creates a                 `CImage` bitmap and attach it to the previously constructed                 `CImage` object.  
  
```  
  
BOOL Create(  
   int   
nWidth  
,  
   int   
nHeight  
,  
   int   
nBPP  
,  
   DWORD   
dwFlags  
 = 0   
) throw( );  
  
```  
  
### Parameters  
 `nWidth`  
 The width of the                                 `CImage` bitmap, in pixels.  
  
 `nHeight`  
 The height of the                                 `CImage` bitmap, in pixels. If                                 `nHeight` is positive, the bitmap is a bottom-up DIB and its origin is the lower left corner. If                                 `nHeight` is negative, the bitmap is a top-down DIB and its origin is the upper left corner.  
  
 `nBPP`  
 The numbers of bits per pixel in the bitmap. Usually 4, 8, 16, 24, or 32. Can be 1 for monochrome bitmaps or masks.  
  
 `dwFlags`  
 Specifies if the bitmap object has an alpha channel. Can be a combination of zero or more of the following values:  
  
-   **createAlphaChannel** Can only be used if                                         `nBPP` is 32, and                                         `eCompression` is                                         **BI_RGB**. If specified, the created image has an alpha (transparency) value for each pixel, stored in the 4th byte of each pixel (unused in a non-alpha 32-bit image). This alpha channel is automatically used when calling                                         [CImage::AlphaBlend](#cimage__alphablend).  
  
> [!NOTE]
>  In calls to                                     [CImage::Draw](#cimage__draw), images with an alpha channel are automatically alpha blended to the destination.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="cimage__createex"></a>  CImage::CreateEx  
 Creates a                 `CImage` bitmap and attach it to the previously constructed                 `CImage` object.  
  
```  
  
BOOL CreateEx(  
   int   
nWidth  
,  
   int   
nHeight  
,  
   int   
nBPP  
,  
   DWORD   
eCompression  
,  
   const DWORD*   
pdwBitmasks  
 = NULL,  
   DWORD   
dwFlags  
 = 0   
) throw( );  
  
```  
  
### Parameters  
 `nWidth`  
 The width of the                                 `CImage` bitmap, in pixels.  
  
 `nHeight`  
 The height of the                                 `CImage` bitmap, in pixels. If                                 `nHeight` is positive, the bitmap is a bottom-up DIB and its origin is the lower left corner. If                                 `nHeight` is negative, the bitmap is a top-down DIB and its origin is the upper left corner.  
  
 `nBPP`  
 The numbers of bits per pixel in the bitmap. Usually 4, 8, 16, 24, or 32. Can be 1 for monochrome bitmaps or masks.  
  
 `eCompression`  
 Specifies the type of compression for a compressed bottom-up bitmap (top-down DIBs cannot be compressed). Can be one of the following values:  
  
-   **BI_RGB** The format is uncompressed. Specifying this value when calling                                         `CImage::CreateEx` is equivalent to calling                                         `CImage::Create`.  
  
-   **BI_BITFIELDS** The format is uncompressed and the color table consists of three                                         `DWORD` color masks that specify the red, green, and blue components, respectively, of each pixel. This is valid when used with 16- and 32-bpp bitmaps.  
  
 *pdwBitfields*  
 Only used if                                 `eCompression` is set to                                 **BI_BITFIELDS**, otherwise it must be                                 **NULL**. A pointer to an array of three                                 `DWORD` bitmasks, specifying which bits of each pixel are used for the red, green, and blue components of the color, respectively. For information on restrictions for the bitfields, see                                 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) in the                                 Windows SDK.  
  
 `dwFlags`  
 Specifies if the bitmap object has an alpha channel. Can be a combination of zero or more of the following values:  
  
-   **createAlphaChannel** Can only be used if                                         `nBPP` is 32, and                                         `eCompression` is                                         **BI_RGB**. If specified, the created image has an alpha (transparency) value for each pixel, stored in the 4th byte of each pixel (unused in a non-alpha 32-bit image). This alpha channel is automatically used when calling                                         [CImage::AlphaBlend](#cimage__alphablend).  
  
    > [!NOTE]
    >  In calls to                                             [CImage::Draw](#cimage__draw), images with an alpha channel are automatically alpha blended to the destination.  
  
### Return Value  
 **TRUE** if successful. Otherwise                         **FALSE**.  
  
### Example  
 The following example creates a 100x100 pixel bitmap, using 16 bits to encode each pixel. In a given 16-bit pixel, bits 0-3 encode the red component, bits 4-7 encode green, and bits 8-11 encode blue. The remaining 4 bits are unused.  
  
 [!CODE [NVC_ATLMFC_Utilities#69](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#69)]  
  
##  <a name="cimage__destroy"></a>  CImage::Destroy  
 Detaches the bitmap from the                 `CImage` object and destroys the bitmap.  
  
```  
  
void Destroy( ) throw( );  
  
```  
  
##  <a name="cimage__detach"></a>  CImage::Detach  
 Detaches a bitmap from a                 `CImage` object.  
  
```  
  
HBITMAP Detach( ) throw( );  
  
```  
  
### Return Value  
 A handle to the bitmap detached, or                         **NULL** if no bitmap is attached.  
  
##  <a name="cimage__draw"></a>  CImage::Draw  
 Copies a bitmap from the source device context to the current device context.  
  
```  
  
BOOL Draw(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   int   
nDestWidth  
,  
   int   
nDestHeight  
,  
   int   
xSrc  
,  
   int   
ySrc  
,  
   int   
nSrcWidth  
,  
   int   
nSrcHeight  
) const throw( );  
BOOL Draw(  
   HDC   
hDestDC  
,  
   const RECT&   
rectDest  
,  
   const RECT&   
rectSrc  
) const throw( );  
BOOL Draw(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
) const throw( );  
BOOL Draw(  
   HDC   
hDestDC  
,  
   const POINT&   
pointDest  
) const throw( );  
BOOL Draw(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   int   
nDestWidth  
,  
   int   
nDestHeight  
) const throw( );  
BOOL Draw(  
   HDC   
hDestDC  
,  
   const RECT&   
rectDest  
) const throw( );  
  
```  
  
### Parameters  
 `hDestDC`  
 A handle to the destination device context.  
  
 `xDest`  
 The x-coordinate, in logical units, of the upper left corner of the destination rectangle.  
  
 `yDest`  
 The y-coordinate, in logical units, of the upper left corner of the destination rectangle.  
  
 `nDestWidth`  
 The width, in logical units, of the destination rectangle.  
  
 `nDestHeight`  
 The height, in logical units, of the destination rectangle.  
  
 `xSrc`  
 The x-coordinate, in logical units, of the upper left corner of the source rectangle.  
  
 `ySrc`  
 The y-coordinate, in logical units, of the upper left corner of the source rectangle.  
  
 `nSrcWidth`  
 The width, in logical units, of the source rectangle.  
  
 `nSrcHeight`  
 The height, in logical units, of the source rectangle.  
  
 `rectDest`  
 A reference to a                                 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure, identifying the destination.  
  
 `rectSrc`  
 A reference to a                                 `RECT` structure, identifying the source.  
  
 `pointDest`  
 A reference to a                                 [POINT](http://msdn.microsoft.com/library/windows/desktop/dd162805) structure that identifies the upper left corner of the destination rectangle, in logical units.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 **Draw** performs the same operation as                         [StretchBlt](#cimage__stretchblt), unless the image contains a transparent color or alpha channel. In that case,                         **Draw** performs the same operation as either                         [TransparentBlt](#cimage__transparentblt) or                         [AlphaBlend](#cimage__alphablend) as required.  
  
 For versions of                         **Draw** that do not specify a source rectangle, the entire source image is the default. For the version of                         **Draw** that does not specify a size for the destination rectangle, the size of the source image is the default and no stretching or shrinking occurs.  
  
##  <a name="cimage__getbits"></a>  CImage::GetBits  
 Retrieves a pointer to the actual bit values of a given pixel in a bitmap.  
  
```  
  
void* GetBits( ) throw( );  
  
```  
  
### Return Value  
 A pointer to the bitmap buffer. If the bitmap is a bottom-up DIB, the pointer points near the end of the buffer. If the bitmap is a top-down DIB, the pointer points to the first byte of the buffer.  
  
### Remarks  
 Using this pointer, along with the value returned by                         [GetPitch](#cimage__getpitch), you can locate and change individual pixels in an image.  
  
> [!NOTE]
>  This method supports only DIB section bitmaps; consequently, you access the pixels of a                             `CImage` object the same way you would the pixels of a DIB section. The returned pointer points to the pixel at the location (0, 0).  
  
##  <a name="cimage__getbpp"></a>  CImage::GetBPP  
 Retrieves the bits-per-pixel value.  
  
```  
  
int GetBPP( ) const throw( );  
  
```  
  
### Return Value  
 The number of bits per pixel.  
  
### Remarks  
 This value determines the number of bits that define each pixel and the maximum number of colors in the bitmap.  
  
 The bits per pixel is usually 1, 4, 8, 16, 24, or 32. See the                         **biBitCount** member of                         [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) in the                         Windows SDK for more information about this value.  
  
##  <a name="cimage__getcolortable"></a>  CImage::GetColorTable  
 Retrieves red, green, blue (RGB) color values from a range of entries in the palette of the DIB section.  
  
```  
  
void GetColorTable(  
   UINT   
iFirstColor  
,  
   UINT   
nColors  
,  
   RGBQUAD*   
prgbColors  
) const throw( );  
  
```  
  
### Parameters  
 `iFirstColor`  
 The color table index of the first entry to retrieve.  
  
 `nColors`  
 The number of color table entries to retrieve.  
  
 `prgbColors`  
 A pointer to the array of                                 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) structures to retrieve the color table entries.  
  
##  <a name="cimage__getdc"></a>  CImage::GetDC  
 Retrieves the device context that currently has the image selected into it.  
  
```  
  
HDC GetDC( ) const throw( );  
  
```  
  
### Return Value  
 A handle to a device context.  
  
### Remarks  
 For each call to                         `GetDC`, you must have a subsequent call to                         [ReleaseDC](#cimage__releasedc).  
  
##  <a name="cimage__getexporterfilterstring"></a>  CImage::GetExporterFilterString  
 Finds image formats available for saving images.  
  
```  
  
static HRESULT GetExporterFilterString(  
   CSimpleString&   
strExporters  
,  
   CSimpleArray< GUID >&   
aguidFileTypes  
,  
   LPCTSTR   
pszAllFilesDescription =                 NULL,  
   DWORD   
dwExclude =                 excludeDefaultSave,  
   TCHAR   
chSeparator =                 _T( '|' )  
);  
  
```  
  
### Parameters  
 *strExporters*  
 A reference to a                                 **CSimpleString** object. See                                 **Remarks** for more information.  
  
 `aguidFileTypes`  
 An array of GUIDs, with each element corresponding to one of the file types in the string. In the example in                                 `pszAllFilesDescription` below,                                 `aguidFileTypes`[0] is                                 `GUID_NULL` and the remaining array values are the image file formats supported by the current operating system.  
  
> [!NOTE]
>  For a complete list of constants, see                                     [Image File Format Constants](_gdiplus_constant_image_file_format_constants) in the                                     Windows SDK.  
  
 `pszAllFilesDescription`  
 If this parameter is not                                 **NULL**, the filter string will have one additional filter at the beginning of the list. This filter will have the current value of                                 `pszAllFilesDescription` for its description, and accepts files of any extension supported by any other exporter in the list.  
  
 For example:  
  
 [!CODE [NVC_ATLMFC_Utilities#73](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#73)]  
  
 `dwExclude`  
 Set of bit flags specifying which file types to exclude from the list. Allowable flags are:  
  
-   **excludeGIF** = 0x01   Excludes GIF files.  
  
-   **excludeBMP** = 0x02   Excludes BMP (Windows Bitmap) files.  
  
-   **excludeEMF** = 0x04   Excludes EMF (Enhanced Metafile) files.  
  
-   **excludeWMF** = 0x08   Excludes WMF (Windows Metafile) files.  
  
-   **excludeJPEG** = 0x10   Excludes JPEG files.  
  
-   **excludePNG** = 0x20   Excludes PNG files.  
  
-   **excludeTIFF** = 0x40   Excludes TIFF files.  
  
-   **excludeIcon** = 0x80   Excludes ICO (Windows Icon) files.  
  
-   **excludeOther** = 0x80000000   Excludes any other file type not listed above.  
  
-   **excludeDefaultLoad** = 0   For load, all file types are included by default  
  
-   **excludeDefaultSave** =                                         **excludeIcon &#124; excludeEMF &#124; excludeWMF** For saving, these files are excluded by default because they usually have special requirements.  
  
 `chSeparator`  
 The separator used between the image formats. See                                 **Remarks** for more information.  
  
### Return Value  
 A standard                         `HRESULT`.  
  
### Remarks  
 You can pass the resulting format string to your MFC                         [CFileDialog](../VS_visualcpp/CFileDialog-Class.md) object to expose the file extensions of the available image formats in the File Save As dialog box.  
  
 The parameter                         *strExporter* has the format:  
  
 file description0&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;...file description                        *n*&#124;\*.ext                        *n*&#124;&#124;  
  
 where '&#124;' is the separator character specified by                         `chSeparator`. For example:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Use the default separator '&#124;' if you pass this string to an MFC                         `CFileDialog` object. Use the null separator '\0' if you pass this string to a common File Save dialog box.  
  
##  <a name="cimage__getheight"></a>  CImage::GetHeight  
 Retrieves the height, in pixels, of an image.  
  
```  
  
int GetHeight( ) const throw( );  
  
```  
  
### Return Value  
 The height, in pixels, of an image.  
  
##  <a name="cimage__getimporterfilterstring"></a>  CImage::GetImporterFilterString  
 Finds image formats available for loading images.  
  
```  
  
static HRESULT GetImporterFilterString(  
   CSimpleString&   
strImporters  
,  
   CSimpleArray< GUID >&   
aguidFileTypes  
,  
   LPCTSTR   
pszAllFilesDescription   
= NULL,  
   DWORD   
dwExclude  
 = excludeDefaultLoad,  
   TCHAR   
chSeparator  
 = _T( '|' )  
);  
  
```  
  
### Parameters  
 *strImporters*  
 A reference to a                                 **CSimpleString** object. See                                 **Remarks** for more information.  
  
 `aguidFileTypes`  
 An array of GUIDs, with each element corresponding to one of the file types in the string. In the example in                                 `pszAllFilesDescription` below,                                 `aguidFileTypes`[0] is                                 `GUID_NULL` with the remaining array values are the image file formats supported by the current operating system.  
  
> [!NOTE]
>  For a complete list of constants, see                                     [Image File Format Constants](_gdiplus_constant_image_file_format_constants) in the                                     Windows SDK.  
  
 `pszAllFilesDescription`  
 If this parameter is not                                 **NULL**, the filter string will have one additional filter at the beginning of the list. This filter will have the current value of                                 `pszAllFilesDescription` for its description, and accepts files of any extension supported by any other exporter in the list.  
  
 For example:  
  
 [!CODE [NVC_ATLMFC_Utilities#74](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#74)]  
  
 `dwExclude`  
 Set of bit flags specifying which file types to exclude from the list. Allowable flags are:  
  
-   **excludeGIF** = 0x01   Excludes GIF files.  
  
-   **excludeBMP** = 0x02   Excludes BMP (Windows Bitmap) files.  
  
-   **excludeEMF** = 0x04   Excludes EMF (Enhanced Metafile) files.  
  
-   **excludeWMF** = 0x08   Excludes WMF (Windows Metafile) files.  
  
-   **excludeJPEG** = 0x10   Excludes JPEG files.  
  
-   **excludePNG** = 0x20   Excludes PNG files.  
  
-   **excludeTIFF** = 0x40   Excludes TIFF files.  
  
-   **excludeIcon** = 0x80   Excludes ICO (Windows Icon) files.  
  
-   **excludeOther** = 0x80000000   Excludes any other file type not listed above.  
  
-   **excludeDefaultLoad** = 0   For load, all file types are included by default  
  
-   **excludeDefaultSave** =                                         **excludeIcon &#124; excludeEMF &#124; excludeWMF** For saving, these files are excluded by default because they usually have special requirements.  
  
 `chSeparator`  
 The separator used between the image formats. See                                 **Remarks** for more information.  
  
### Remarks  
 You can pass the resulting format string to your MFC                         [CFileDialog](../VS_visualcpp/CFileDialog-Class.md) object to expose the file extensions of the available image formats in the                         **File Open** dialog box.  
  
 The parameter                         *strImporter* has the format:  
  
 file description0&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;...file description                        *n*&#124;\*.ext                        *n*&#124;&#124;  
  
 where '&#124;' is the separator character specified by                         `chSeparator`. For example:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Use the default separator '&#124;' if you pass this string to an MFC                         `CFileDialog` object. Use the null separator '\0' if you pass this string to a common                         **File Open** dialog box.  
  
##  <a name="cimage__getmaxcolortableentries"></a>  CImage::GetMaxColorTableEntries  
 Retrieves the maximum number of entries in the color table.  
  
```  
  
int GetMaxColorTableEntries( ) const throw( );  
  
```  
  
### Return Value  
 The number of entries in the color table.  
  
### Remarks  
 This method supports only DIB section bitmaps.  
  
##  <a name="cimage__getpitch"></a>  CImage::GetPitch  
 Retrieves the pitch of an image.  
  
```  
  
int GetPitch( ) const throw( );  
  
```  
  
### Return Value  
 The pitch of the image. If the return value is negative, the bitmap is a bottom-up DIB and its origin is the lower left corner. If the return value is positive, the bitmap is a top-down DIB and its origin is the upper left corner.  
  
### Remarks  
 The pitch is the distance, in bytes, between two memory addresses that represent the beginning of one bitmap line and the beginning of the next bitmap line. Because pitch is measured in bytes, the pitch of an image helps you to determine the pixel format. The pitch can also include additional memory, reserved for the bitmap.  
  
 Use                         `GetPitch` with                         [GetBits](#cimage__getbits) to find individual pixels of an image.  
  
> [!NOTE]
>  This method supports only DIB section bitmaps.  
  
##  <a name="cimage__getpixel"></a>  CImage::GetPixel  
 Retrieves the color of the pixel at the location specified by                 *x* and                 *y*.  
  
```  
  
COLORREF GetPixel(  
   int   
x  
,  
   int   
y  
) const throw( );  
  
```  
  
### Parameters  
 *x*  
 The x-coordinate of the pixel.  
  
 *y*  
 The y-coordinate of the pixel.  
  
### Return Value  
 The red, green, blue (RGB) value of the pixel. If the pixel is outside of the current clipping region, the return value is                         **CLR_INVALID**.  
  
##  <a name="cimage__getpixeladdress"></a>  CImage::GetPixelAddress  
 Retrieves the exact address of a pixel.  
  
```  
  
void* GetPixelAddress(  
   int   
x  
,  
   int   
y  
) throw( );  
  
```  
  
### Parameters  
 *x*  
 The x-coordinate of the pixel.  
  
 *y*  
 The y-coordinate of the pixel.  
  
### Remarks  
 The address is determined according to the coordinates of a pixel, the pitch of the bitmap, and the bits per pixel.  
  
 For formats that have less than 8 bits per pixel, this method returns the address of the byte containing the pixel. For example, if your image format has 4 bits per pixel,                         `GetPixelAddress` returns the address of the first pixel in the byte, and you must calculate for 2 pixels per byte.  
  
> [!NOTE]
>  This method supports only DIB section bitmaps.  
  
##  <a name="cimage__gettransparentcolor"></a>  CImage::GetTransparentColor  
 Retrieves the indexed location of the transparent color in the color palette.  
  
```  
  
LONG GetTransparentColor( ) const throw( );  
  
```  
  
### Return Value  
 The index of the transparent color.  
  
##  <a name="cimage__getwidth"></a>  CImage::GetWidth  
 Retrieves the width, in pixels, of an image.  
  
```  
  
int GetWidth( ) const throw( );  
  
```  
  
### Return Value  
 The width of the bitmap, in pixels.  
  
##  <a name="cimage__isdibsection"></a>  CImage::IsDIBSection  
 Determines if the attached bitmap is a DIB section.  
  
```  
  
bool IsDIBSection( ) const throw( );  
  
```  
  
### Return Value  
 **true** if the attached bitmap is a DIB section. Otherwise                         **false**.  
  
### Remarks  
 If the bitmap is not a DIB section, you cannot use the following                         `CImage` methods, which support only DIB section bitmaps:  
  
-   [GetBits](#cimage__getbits)  
  
-   [GetColorTable](#cimage__getcolortable)  
  
-   [GetMaxColorTableEntries](#cimage__getmaxcolortableentries)  
  
-   [GetPitch](#cimage__getpitch)  
  
-   [GetPixelAddress](#cimage__getpixeladdress)  
  
-   [IsIndexed](#cimage__isindexed)  
  
-   [SetColorTable](#cimage__setcolortable)  
  
##  <a name="cimage__isindexed"></a>  CImage::IsIndexed  
 Determines whether a bitmap's pixels are mapped to a color palette.  
  
```  
  
bool IsIndexed( ) const throw( );  
  
```  
  
### Return Value  
 **true** if indexed; otherwise                         **false**.  
  
### Remarks  
 This method returns                         **true** only if the bitmap is 8-bit (256 colors) or less.  
  
> [!NOTE]
>  This method supports only DIB section bitmaps.  
  
##  <a name="cimage__isnull"></a>  CImage::IsNull  
 Determines if a bitmap is currently loaded.  
  
```  
  
bool IsNull( ) const throw( );  
  
```  
  
### Remarks  
 This method returns                         **True** if a bitmap is not currently loaded; otherwise                         **False**.  
  
##  <a name="cimage__istransparencysupported"></a>  CImage::IsTransparencySupported  
 Indicates whether the application supports transparent bitmaps and was compiled for Windows 2000 or later.  
  
```  
  
static BOOL IsTransparencySupported( ) throw( );  
  
```  
  
### Return Value  
 Nonzero if the current platform supports transparency. Otherwise 0.  
  
### Remarks  
 If the return value is nonzero, and transparency is supported, a call to                         [AlphaBlend](#cimage__alphablend),                         [TransparentBlt](#cimage__transparentblt), or                         [Draw](#cimage__draw) will handle transparent colors.  
  
 If the application is compiled for use with operating systems before Windows 2000 or Windows 98, this method will always return 0, even on newer operating systems.  
  
 See                         [CImage Limitations with Earlier Operating Systems](../VS_visualcpp/CImage-Limitations-with-Earlier-Operating-Systems.md) for more detailed information.  
  
##  <a name="cimage__load"></a>  CImage::Load  
 Loads an image.  
  
```  
  
HRESULT Load(  
   LPCTSTR   
pszFileName  
) throw( );  
HRESULT Load(  
   IStream*   
pStream  
) throw();  
  
```  
  
### Parameters  
 `pszFileName`  
 A pointer to a string containing the name of the image file to load.  
  
 `pStream`  
 A pointer to a stream containing the name of the image file to load.  
  
### Return Value  
 A standard                         `HRESULT`.  
  
### Remarks  
 Loads the image specified by                         *pszFileName* or                         `pStream`.  
  
 Valid image types are BMP, GIF, JPEG, PNG, and TIFF.  
  
##  <a name="cimage__loadfromresource"></a>  CImage::LoadFromResource  
 Loads an image from a                 `BITMAP` resource.  
  
```  
  
void LoadFromResource(  
   HINSTANCE   
hInstance  
,  
   LPCTSTR   
pszResourceName  
) throw();  
void LoadFromResource(  
   HINSTANCE   
hInstance  
,  
   UINT   
nIDResource  
) throw();  
  
```  
  
### Parameters  
 `hInstance`  
 Handle to an instance of the module that contains the image to be loaded.  
  
 `pszResourceName`  
 A pointer to the string containing the name of the resource containing the image to load.  
  
 `nIDResource`  
 The ID of the resource to load.  
  
### Remarks  
 The resource must be of type                         `BITMAP`.  
  
##  <a name="cimage__maskblt"></a>  CImage::MaskBlt  
 Combines the color data for the source and destination bitmaps using the specified mask and raster operation.  
  
```  
  
BOOL MaskBlt(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   int   
nDestWidth  
,  
   int   
nDestHeight  
,  
   int   
xSrc  
,  
   int   
ySrc  
,  
   HBITMAP   
hbmMask  
,  
   int   
xMask  
,  
   int   
yMask  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
BOOL MaskBlt(  
   HDC   
hDestDC  
,  
   const RECT&   
rectDest  
,  
   const POINT&   
pointSrc  
,  
   HBITMAP   
hbmMask  
,  
   const POINT&   
pointMask  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
BOOL MaskBlt(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   HBITMAP   
hbmMask  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
BOOL MaskBlt(  
   HDC   
hDestDC  
,  
   const POINT&   
pointDest  
,  
   HBITMAP   
hbmMask  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
  
```  
  
### Parameters  
 `hDestDC`  
 The handle to the module whose executable contains the resource.  
  
 `xDest`  
 The x-coordinate, in logical units, of the upper left corner of the destination rectangle.  
  
 `yDest`  
 The y-coordinate, in logical units, of the upper left corner of the destination rectangle.  
  
 `nDestWidth`  
 The width, in logical units, of the destination rectangle and source bitmap.  
  
 `nDestHeight`  
 The height, in logical units, of the destination rectangle and source bitmap.  
  
 `xSrc`  
 The logical x-coordinate of the upper left corner of the source bitmap.  
  
 `ySrc`  
 The logical y-coordinate of the upper left corner of the source bitmap.  
  
 `hbmMask`  
 Handle to the monochrome mask bitmap combined with the color bitmap in the source device context.  
  
 `xMask`  
 The horizontal pixel offset for the mask bitmap specified by the                                 `hbmMask` parameter.  
  
 `yMask`  
 The vertical pixel offset for the mask bitmap specified by the                                 `hbmMask` parameter.  
  
 `dwROP`  
 Specifies both foreground and background ternary raster operation codes that the method uses to control the combination of source and destination data. The background raster operation code is stored in the high-order byte of the high-order word of this value; the foreground raster operation code is stored in the low-order byte of the high-order word of this value; the low-order word of this value is ignored, and should be zero. For a discussion of foreground and background in the context of this method, see                                 `MaskBlt` in the                                 Windows SDK. For a list of common raster operation codes, see                                 `BitBlt` in the                                 Windows SDK.  
  
 `rectDest`  
 A reference to a                                 `RECT` structure, identifying the destination.  
  
 `pointSrc`  
 A                                 `POINT` structure indicating the upper left corner of the source rectangle.  
  
 `pointMask`  
 A                                 **POINT** structure indicating the upper left corner of the mask bitmap.  
  
 `pointDest`  
 A reference to a                                 **POINT** structure that identifies the upper left corner of the destination rectangle, in logical units.  
  
### Return Value  
 Nonzero if successful, otherwise 0.  
  
### Remarks  
 This method applies to Windows NT, versions 4.0 and later only.  
  
 See                         `MaskBlt` in the                         Windows SDK and                         [CImage Limitations with Earlier Operating Systems](../VS_visualcpp/CImage-Limitations-with-Earlier-Operating-Systems.md) for more detailed information.  
  
##  <a name="cimage__operator_hbitmap"></a>  CImage::operator HBITMAP  
 Use this operator to get the attached Windows GDI handle of the                 `CImage` object. This operator is a casting operator, which supports direct use of an                 `HBITMAP` object.  
  
##  <a name="cimage__plgblt"></a>  CImage::PlgBlt  
 Performs a bit-block transfer from a rectangle in a source device context into a parallelogram in a destination device context.  
  
```  
  
BOOL PlgBlt(  
   HDC   
hDestDC  
,  
   const POINT*   
pPoints  
,  
   HBITMAP   
hbmMask  
 = NULL   
) const throw( );  
BOOL PlgBlt(  
   HDC   
hDestDC  
,  
   const POINT*   
pPoints  
,  
   int   
xSrc  
,  
   int   
ySrc  
,  
   int   
nSrcWidth  
,  
   int   
nSrcHeight  
,  
   HBITMAP   
hbmMask  
 = NULL,  
   int   
xMask  
 = 0,  
   int   
yMask  
 = 0   
) const throw( );  
BOOL PlgBlt(  
   HDC   
hDestDC  
,  
   const POINT*   
pPoints  
,  
   const RECT&   
rectSrc  
,  
   HBITMAP   
hbmMask  
 = NULL,  
   const POINT&   
pointMask  
 = CPoint(  
   0, 0 )   
) const throw( );  
  
```  
  
### Parameters  
 `hDestDC`  
 A handle to the destination device context.  
  
 *pPoints*  
 A pointer to an array of three points in logical space that identify three corners of the destination parallelogram. The upper left corner of the source rectangle is mapped to the first point in this array, the upper-right corner to the second point in this array, and the lower left corner to the third point. The lower-right corner of the source rectangle is mapped to the implicit fourth point in the parallelogram.  
  
 `hbmMask`  
 A handle to an optional monochrome bitmap that is used to mask the colors of the source rectangle.  
  
 `xSrc`  
 The x-coordinate, in logical units, of the upper left corner of the source rectangle.  
  
 `ySrc`  
 The y-coordinate, in logical units, of the upper left corner of the source rectangle.  
  
 `nSrcWidth`  
 The width, in logical units, of the source rectangle.  
  
 `nSrcHeight`  
 The height, in logical units, of the source rectangle.  
  
 `xMask`  
 The x-coordinate of the upper left corner of the monochrome bitmap.  
  
 `yMask`  
 The y-coordinate of the upper left corner of the monochrome bitmap.  
  
 `rectSrc`  
 A reference to a                                 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure specifying the coordinates of the source rectangle.  
  
 `pointMask`  
 A                                 [POINT](http://msdn.microsoft.com/library/windows/desktop/dd162805) structure indicating the upper left corner of the mask bitmap.  
  
### Return Value  
 Nonzero if successful, otherwise 0.  
  
### Remarks  
 If                         `hbmMask` identifies a valid monochrome bitmap,                         **PlgBit** uses this bitmap to mask the bits of color data from the source rectangle.  
  
 This method applies to Windows NT, versions 4.0 and later only. See                         [PlgBlt](http://msdn.microsoft.com/library/windows/desktop/dd162804) in the                         Windows SDK and                         [CImage Limitations with Earlier Operating Systems](../VS_visualcpp/CImage-Limitations-with-Earlier-Operating-Systems.md) for more detailed information.  
  
##  <a name="cimage__releasedc"></a>  CImage::ReleaseDC  
 Releases the device context.  
  
```  
  
void ReleaseDC( ) const throw( );  
  
```  
  
### Remarks  
 Because only one bitmap can be selected into a device context at a time, you must call                         `ReleaseDC` for each call to                         [GetDC](#cimage__getdc).  
  
##  <a name="cimage__releasegdiplus"></a>  CImage::ReleaseGDIPlus  
 Releases resources used by GDI+.  
  
```  
  
void ReleaseGDIPlus() throw();  
  
```  
  
### Remarks  
 This method must be called to free resources allocated by a global                         `CImage` object. See                         [CImage::CImage](#cimage__cimage).  
  
##  <a name="cimage__save"></a>  CImage::Save  
 Saves an image to the specified stream or file on disk.  
  
```  
  
HRESULT Save(  
   IStream*   
pStream  
,  
   REFGUID   
guidFileType  
) const throw();  
HRESULT Save(  
   LPCTSTR   
pszFileName  
,  
   REFGUID   
guidFileType=                 GUID_NULL  
) const throw();  
  
```  
  
### Parameters  
 `pStream`  
 A pointer to a COM IStream object containing the file image data.  
  
 *pszFileName*  
 A pointer to the file name for the image.  
  
 `guidFileType`  
 The file type to save the image as. Can be one of the following:  
  
-   **ImageFormatBMP** An uncompressed bitmap image.  
  
-   **ImageFormatPNG** A Portable Network Graphic (PNG) compressed image.  
  
-   **ImageFormatJPEG** A JPEG compressed image.  
  
-   **ImageFormatGIF** A GIF compressed image.  
  
> [!NOTE]
>  For a complete list of constants, see                                     [Image File Format Constants](_gdiplus_constant_image_file_format_constants) in the                                     Windows SDK.  
  
### Return Value  
 A standard                         `HRESULT`.  
  
### Remarks  
 Call this function to save the image using a specified name and type. If the                         `guidFileType` parameter is not included, the file name's file extension will be used to determine the image format. If no extension is provided, the image will be saved in BMP format.  
  
##  <a name="cimage__setcolortable"></a>  CImage::SetColorTable  
 Sets the red, green, blue (RGB) color values for a range of entries in the palette of the DIB section.  
  
```  
  
void SetColorTable(  
   UINT   
iFirstColor  
,  
   UINT   
nColors  
,  
   const RGBQUAD*   
prgbColors  
) throw( );  
  
```  
  
### Parameters  
 `iFirstColor`  
 The color table index of the first entry to set.  
  
 `nColors`  
 The number of color table entries to set.  
  
 `prgbColors`  
 A pointer to the array of                                 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) structures to set the color table entries.  
  
### Remarks  
 This method supports only DIB section bitmaps.  
  
##  <a name="cimage__setpixel"></a>  CImage::SetPixel  
 Sets the color of a pixel at a given location in the bitmap.  
  
```  
  
void SetPixel(  
   int   
x  
,  
   int   
y  
,  
   COLORREF   
color  
) throw( );  
  
```  
  
### Parameters  
 *x*  
 The horizontal location of the pixel to set.  
  
 *y*  
 The vertical location of the pixel to set.  
  
 `color`  
 The color to which you set the pixel.  
  
### Remarks  
 This method fails if the pixel coordinates lie outside of the selected clipping region.  
  
##  <a name="cimage__setpixelindexed"></a>  CImage::SetPixelIndexed  
 Sets the pixel color to the color located at                 `iIndex` in the color palette.  
  
```  
  
void SetPixelIndexed(  
   int   
x  
,  
   int   
y  
,  
   int   
iIndex  
) throw( );  
  
```  
  
### Parameters  
 *x*  
 The horizontal location of the pixel to set.  
  
 *y*  
 The vertical location of the pixel to set.  
  
 `iIndex`  
 The index of a color in the color palette.  
  
##  <a name="cimage__setpixelrgb"></a>  CImage::SetPixelRGB  
 Sets the pixel at the locations specified by                 *x* and                 *y* to the colors indicated by                 *r*,                 *g*, and                 *b*, in a red, green, blue (RGB) image.  
  
```  
  
void SetPixelRGB(  
   int   
x  
,  
   int   
y  
,  
   BYTE   
r  
,  
   BYTE   
g  
,  
   BYTE   
b  
) throw( );  
  
```  
  
### Parameters  
 *x*  
 The horizontal location of the pixel to set.  
  
 *y*  
 The vertical location of the pixel to set.  
  
 *r*  
 The intensity of the red color.  
  
 *g*  
 The intensity of the green color.  
  
 *b*  
 The intensity of the blue color.  
  
### Remarks  
 The red, green, and blue parameters are each represented by a number between 0 and 255. If you set all three parameters to zero, the combined resulting color is black. If you set all three parameters to 255, the combined resulting color is white.  
  
##  <a name="cimage__settransparentcolor"></a>  CImage::SetTransparentColor  
 Sets a color at a given indexed location as transparent.  
  
```  
  
LONG SetTransparentColor(  
   LONG   
iTransparentColor  
) throw( );  
  
```  
  
### Parameters  
 *iTransparentColor*  
 The index, in a color palette, of the color to set to transparent. If –1, no color is set to transparent.  
  
### Return Value  
 The index of the color previously set as transparent.  
  
##  <a name="cimage__stretchblt"></a>  CImage::StretchBlt  
 Copies a bitmap from the source device context to this current device context.  
  
```  
  
BOOL StretchBlt(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   int   
nDestWidth  
,  
   int   
nDestHeight  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
BOOL StretchBlt(  
   HDC   
hDestDC  
,  
   const RECT&   
rectDest  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
BOOL StretchBlt(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   int   
nDestWidth  
,  
   int   
nDestHeight  
,  
   int   
xSrc  
,  
   int   
ySrc  
,  
   int   
nSrcWidth  
,  
   int   
nSrcHeight  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
BOOL StretchBlt(  
   HDC   
hDestDC  
,  
   const RECT&   
rectDest  
,  
   const RECT&   
rectSrc  
,  
   DWORD   
dwROP  
 = SRCCOPY   
) const throw( );  
  
```  
  
### Parameters  
 `hDestDC`  
 A handle to the destination device context.  
  
 `xDest`  
 The x-coordinate, in logical units, of the upper left corner of the destination rectangle.  
  
 `yDest`  
 The y-coordinate, in logical units, of the upper left corner of the destination rectangle.  
  
 `nDestWidth`  
 The width, in logical units, of the destination rectangle.  
  
 `nDestHeight`  
 The height, in logical units, of the destination rectangle.  
  
 `dwROP`  
 The raster operation to be performed. Raster-operation codes define exactly how to combine the bits of the source, the destination, and the pattern (as defined by the currently selected brush) to form the destination. See                                 [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) in the                                 Windows SDK for a list of other raster-operation codes and their descriptions.  
  
 `rectDest`  
 A reference to a                                 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure, identifying the destination.  
  
 `xSrc`  
 The x-coordinate, in logical units, of the upper left corner of the source rectangle.  
  
 `ySrc`  
 The y-coordinate, in logical units, of the upper left corner of the source rectangle.  
  
 `nSrcWidth`  
 The width, in logical units, of the source rectangle.  
  
 `nSrcHeight`  
 The height, in logical units, of the source rectangle.  
  
 `rectSrc`  
 A reference to a                                 `RECT` structure, identifying the source.  
  
### Return Value  
 Nonzero if successful, otherwise 0.  
  
### Remarks  
 For more information, see                         [StretchBlt](http://msdn.microsoft.com/library/windows/desktop/dd145120) in the                         Windows SDK.  
  
##  <a name="cimage__transparentblt"></a>  CImage::TransparentBlt  
 Copies a bitmap from the source device context to this current device context.  
  
```  
  
BOOL TransparentBlt(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   int   
nDestWidth  
,  
   int   
nDestHeight  
,  
   UINT   
crTransparent  
 = CLR_INVALID   
) const throw( );  
BOOL TransparentBlt(  
   HDC   
hDestDC  
,  
   const RECT&   
rectDest  
,  
   UINT   
crTransparent  
 = CLR_INVALID   
) const throw( );  
BOOL TransparentBlt(  
   HDC   
hDestDC  
,  
   int   
xDest  
,  
   int   
yDest  
,  
   int   
nDestWidth  
,  
   int   
nDestHeight  
,  
   int   
xSrc  
,  
   int   
ySrc  
,  
   int   
nSrcWidth  
,  
   int   
nSrcHeight  
,  
   UINT   
crTransparent  
 = CLR_INVALID   
) const throw( );  
BOOL TransparentBlt(  
   HDC   
hDestDC  
,  
   const RECT&   
rectDest  
,  
   const RECT&   
rectSrc  
,  
   UINT   
crTransparent  
 = CLR_INVALID   
) const throw( );  
  
```  
  
### Parameters  
 `hDestDC`  
 A handle to the destination device context.  
  
 `xDest`  
 The x-coordinate, in logical units, of the upper left corner of the destination rectangle.  
  
 `yDest`  
 The y-coordinate, in logical units, of the upper left corner of the destination rectangle.  
  
 `nDestWidth`  
 The width, in logical units, of the destination rectangle.  
  
 `nDestHeight`  
 The height, in logical units, of the destination rectangle.  
  
 *crTransparent*  
 The color in the source bitmap to treat as transparent. By default,                                 **CLR_INVALID**, indicating that the color currently set as the transparent color of the image should be used.  
  
 `rectDest`  
 A reference to a                                 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure, identifying the destination.  
  
 `xSrc`  
 The x-coordinate, in logical units, of the upper left corner of the source rectangle.  
  
 `ySrc`  
 The y-coordinate, in logical units, of the upper left corner of the source rectangle.  
  
 `nSrcWidth`  
 The width, in logical units, of the source rectangle.  
  
 `nSrcHeight`  
 The height, in logical units, of the source rectangle.  
  
 `rectSrc`  
 A reference to a                                 `RECT` structure, identifying the source.  
  
### Return Value  
 **TRUE** if successful, otherwise                         **FALSE**.  
  
### Remarks  
 `TransparentBlt` is supported for source bitmaps of 4 bits per pixel and 8 bits per pixel. Use                         [CImage::AlphaBlend](#cimage__alphablend) to specify 32 bits-per-pixel bitmaps with transparency.  
  
 This method is applicable to Microsoft Windows 2000, Windows 98, and later systems. See                         [TransparentBlt](http://msdn.microsoft.com/library/windows/desktop/dd145141) in the                         Windows SDK and                         [CImage Limitations with Earlier Operating Systems](../VS_visualcpp/CImage-Limitations-with-Earlier-Operating-Systems.md) for more detailed information.  
  
### Example  
 [!CODE [NVC_ATLMFC_Utilities#199](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#199)]  
  
## See Also  
 [MMXSwarm Sample](../VS_visualcpp/Visual-C---Samples.md)   
 [SimpleImage Sample](../VS_visualcpp/Visual-C---Samples.md)   
 [Device-Independent Bitmaps](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM Desktop Components](../VS_visualcpp/ATL-COM-Desktop-Components.md)