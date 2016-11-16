---
title: "Class &#39;&lt;classname1&gt;&#39; must declare a &#39;Sub New&#39; because its base class &#39;&lt;classname2&gt;&#39; has more than one accessible &#39;Sub New&#39; that can be called with no arguments | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32036"
  - "vbc32036"
helpviewer_keywords: 
  - "BC32036"
ms.assetid: 9b96387e-337e-4b2a-b49f-783c7e13811a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
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
# Class &#39;&lt;classname1&gt;&#39; must declare a &#39;Sub New&#39; because its base class &#39;&lt;classname2&gt;&#39; has more than one accessible &#39;Sub New&#39; that can be called with no arguments
A derived class does not declare a constructor, and [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] cannot generate one because it cannot determine which base class constructor to call.  
  
 When a derived class does not declare a constructor, [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] attempts to generate an implicit parameterless constructor that calls `MyBase.New()`. If there is no accessible constructor in the base class that can be called without arguments, or if there is more than one, [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] cannot generate an implicit constructor.  
  
 This situation can arise, for example, if one base class constructor has a single `Optional` argument and another has a single `ParamArray` argument. Each of these can be called with no arguments.  
  
 **Error ID:** BC32036  
  
### To correct this error  
  
1.  Declare and implement at least one `Sub New` constructor somewhere in the derived class.  
  
2.  Add a call to a base class constructor, `MyBase.New()`, as the first line of every `Sub New`.  
  
## See Also  
 [Object Lifetime: How Objects Are Created and Destroyed](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md)   
 [NOT IN BUILD: Using Constructors and Destructors](http://msdn.microsoft.com/en-us/548eebe1-86c4-4377-b2f5-447cb8be3d90)   
 [Optional](/dotnet/visual-basic/language-reference/modifiers/optional)   
 [ParamArray](/dotnet/visual-basic/language-reference/modifiers/paramarray)   
 [Optional Parameters](/dotnet/visual-basic/language-reference/procedures/optional-parameters)   
 [Parameter Arrays](/dotnet/visual-basic/language-reference/procedures/parameter-arrays)