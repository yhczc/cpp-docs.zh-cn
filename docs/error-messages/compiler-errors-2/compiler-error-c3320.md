---
title: 编译器错误 C3320
ms.date: 11/04/2016
f1_keywords:
- C3320
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
ms.openlocfilehash: 622e7366dda4cd6693d9b6128855fa0966e07952
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581462"
---
# <a name="compiler-error-c3320"></a>编译器错误 C3320

“type”：类型不能和模块的“name”属性同名

导出的用户定义的类型 (UDT)，这可能是结构、 类、 枚举或联合，不能将相同的名称作为参数传递给[模块](../../windows/module-cpp.md)特性的名称属性。

## <a name="example"></a>示例

以下示例生成 C3320：

```cpp
// C3320.cpp
#include "unknwn.h"
[module(name="xx")];

[export] struct xx {   // C3320
// Try the following line instead
// [export] struct yy {
   int i;
};
```