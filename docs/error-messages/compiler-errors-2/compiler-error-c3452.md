---
title: "编译器错误 C3452 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3452
dev_langs:
- C++
helpviewer_keywords:
- C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0ff18842af11d82d28819b01cb7798a4ae49eff1
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3452"></a>编译器错误 C3452
列出不是常量的参数成员  
  
 参数被传递到一个特性，但此特性需要一个常量，即一个在编译时可计算出结果的值。  
  
## <a name="example"></a>示例  
 下面的示例生成 C3452。  
  
```  
// C3452.cpp  
// compile with: /c  
int i;  
[module( name="mod", type=dll, custom={i} ) ];   // C3452  
// try the following line instead  
// [module( name="mod", type=dll, custom={"a"} ) ];  
```