---
title: "while 语句 (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: while
dev_langs: C++
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5f8157d4006d3f2a53e2f32a87d8923baf73628f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="while-statement-c"></a>While 语句 (C)
利用 `while` 语句，您可以重复语句直到指定的表达式变为 false。  
  
## <a name="syntax"></a>语法  
 *iteration-statement*:  
 while (  expression  )  statement  
  
 expression 必须具有算法或指针类型。 执行过程如下所示：  
  
1.  计算 expression。  
  
2.  如果 expression 最初为 false，则绝不执行 `while` 语句体，并且控制从 `while` 语句到程序中下一语句的传递。  
  
     如果 expression 为 true（非零），则执行语句体，并且此过程从第 1 步开始重复。  
  
 `while` 语句还可在执行语句体中的 break、`goto` 或 `return` 时终止。 使用 continue 语句可在不退出 `while` 循环的情况下终止迭代。 continue 语句将控制传递给 `while` 语句的下一个迭代。  
  
 以下是 `while` 语句的示例：  
  
```  
while ( i >= 0 )   
{  
    string1[i] = string2[i];  
    i--;  
}  
```  
  
 此示例将 `string2` 中的字符复制到 `string1`。 如果 `i` 大于或等于 0，则 `string2[i]` 将赋给 `string1[i]`，并且 `i` 将递减。 当 `i` 达到 0 或小于 0 时，`while` 语句的执行将终止。  
  
## <a name="see-also"></a>另请参阅  
 [while 语句 (C++)](../cpp/while-statement-cpp.md)