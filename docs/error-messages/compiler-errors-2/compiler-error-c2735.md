---
title: 编译器错误 C2735
ms.date: 11/04/2016
f1_keywords:
- C2735
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
ms.openlocfilehash: 73d5f61b5f86153db74a970d97b4656fb662bdad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447852"
---
# <a name="compiler-error-c2735"></a>编译器错误 C2735

形参类型说明符中不允许使用 keyword 关键字

关键字在此上下文中无效。

下面的示例生成 C2735:

```
// C2735.cpp
void f(inline int){}   // C2735
```