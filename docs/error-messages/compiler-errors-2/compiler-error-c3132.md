---
title: 编译器错误 C3132
ms.date: 11/04/2016
f1_keywords:
- C3132
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
ms.openlocfilehash: 1a97e04747cb92909380e66d1f4ea8ca62183054
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424166"
---
# <a name="compiler-error-c3132"></a>编译器错误 C3132

函数参数： 参数数组只能应用到一维托管数组类型的形式自变量

<xref:System.ParamArrayAttribute>特性已应用于一个参数，它不是单维数组。

下面的示例生成 C3132:

```
// C3132.cpp
// compile with: /clr /c
using namespace System;
void f( [ParamArray] Int32[,] );   // C3132
void g( [ParamArray] Int32[] );   // C3132

void h( [ParamArray] array<Char ^> ^ MyArray );   // OK
```