---
title: "Compiler Error CS0828 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0828"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0828"
ms.assetid: e18ffe72-2fcc-436d-be7f-8c8365b86129
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Compiler Error CS0828
Cannot assign 'expression' to anonymous type property.  
  
 An anonymous type cannot be initialized with a null value or an unsafe type, or a method group or anonymous function.  
  
### To correct this error  
  
1.  Either add a type declaration to the left side of the assignment, or change the expression on the right side so that it has an acceptable type.  
  
## Example  
 The following code generates CS0828 because a member of an anonymous type cannot be initialized with a null value.  
  
```  
// cs0828.cs  
using System;  
  
public class C  
{  
    public static int Main()  
    {  
        var a = 1;  
        var c = new { p1 = null }; // CS0828  
        return 1;  
    }  
}  
```  
  
## See Also  
 [Implicitly Typed Local Variables](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)