---
title: "_free_locale"
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
  - _free_locale
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
  - api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
caps.latest.revision: 12
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
# _free_locale
Frees a locale object.  
  
## Syntax  
  
```  
void _free_locale(  
   _locale_t locale  
);  
```  
  
#### Parameters  
 `locale`  
 Locale object to free.  
  
## Remarks  
 The `_free_locale` function is used to free the locale object obtained from a call to `_get_current_locale` or `_create_locale`.  
  
 The previous name of this function, `__free_locale` (with two leading underscores) has been deprecated.  
  
## Requirements  
  
|`Routine`|Required header|  
|---------------|---------------------|  
|`_free_locale`|<locale.h>|  
  
 For more compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md) in the Introduction.  
  
## .NET Framework Equivalent  
 No equivalent.  
  
## See Also  
 [_get_current_locale](../VS_visualcpp/_get_current_locale.md)   
 [_create_locale, _wcreate_locale](../VS_visualcpp/_create_locale--_wcreate_locale.md)