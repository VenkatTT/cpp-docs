---
title: "Checking for Memory Overwrites"
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
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: 7
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
# Checking for Memory Overwrites
If you get an access violation on a call to a heap manipulation function, it is possible that your program has corrupted the heap. A common symptom of this situation would be:  
  
```  
Access Violation in _searchseg  
```  
  
 The [_heapchk](../VS_visualcpp/_heapchk.md) function is available in both debug and release builds (Windows NT only) for verifying the integrity of the run time library heap. You can use `_heapchk` in much the same way as the `AfxCheckMemory` function to isolate a heap overwrite, for example:  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 If this function ever fails, you need to isolate at which point the heap was corrupted.  
  
## See Also  
 [Fixing Release Build Problems](../VS_visualcpp/Fixing-Release-Build-Problems.md)