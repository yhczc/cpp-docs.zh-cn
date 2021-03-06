---
title: 编译器警告（等级 1）C4627
ms.date: 09/09/2018
f1_keywords:
- C4627
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
ms.openlocfilehash: ef00d6691195fa5fb925448dce9513d1ecb08b6d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809946"
---
# <a name="compiler-warning-level-1-c4627"></a>编译器警告（等级 1）C4627

> '*header_file*： 在查找预编译标头使用时跳过

如果当前源文件[/Yu\(使用预编译头文件)](../../build/reference/yu-use-precompiled-header-file.md)选项集，则编译器将忽略该文件中的所有内容，包含预编译标头之前。 警告**C4627**如果在 Visual Studio 2015 及更早版本中生成*header_file*包含之前预编译的头文件中，如果预编译标头还包括*header_file*。

## <a name="example"></a>示例

此示例演示如何错误不会发生，并演示如何修复此错误：

```cpp
// c4627.cpp
#include <iostream>       // C4627 - iostream not included by pch.h
#include "pch.h"          // precompiled header file that does not include iostream
// #include <iostream>    // To fix, move the iostream header include here from above
int main()
{
    std::cout << "std::cout is defined!\n";
}
```

## <a name="see-also"></a>请参阅

[创建预编译标头文件](../../build/creating-precompiled-header-files.md)
