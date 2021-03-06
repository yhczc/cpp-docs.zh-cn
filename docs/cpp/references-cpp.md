---
title: 引用 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- objects [C++], referencing
- references [C++]
- references, to pointers
- declarations, references
- references, declaring
- referencing objects, declarator syntax
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
ms.openlocfilehash: aafc582299402eabab2736ac7d07b6c4c397413c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616437"
---
# <a name="references-c"></a>引用 (C++)

与指针相似的是，引用将存储位于内存中其他位置的对象的地址。 与指针不同的是，初始化之后的引用无法引用不同的对象或设置为 null。 有两种类型的引用： 左值引用，后者是指已命名的变量和右值引用后者是指[临时对象](../cpp/temporary-objects.md)。 & 运算符表示左值引用，&& 运算符根据上下文表示右值引用或通用引用（右值引用或左值引用）。

可以通过以下语法声明引用：

> \[*存储类说明符*] \[ *cv 限定符*]*类型说明符* \[ *ms 修饰符*] *声明符* \[ **=** *表达式*]**;**

可以使用指定引用的任何有效声明符。 除非引用是对函数或数组类型的引用，否则应用以下简化语法：

> \[*存储类说明符*] \[ *cv 限定符*]*类型说明符* \[ **&** 或**&&**] \[ *cv 限定符*]*标识符* \[ **=** *表达式*]**;**

使用以下序列声明引用：

1. 声明说明符：

   - 可选存储类说明符。

   - 可选**const**和/或**易失性**限定符。

   - 类型说明符：类型的名称。

1. 声明符：

   - 可选的 Microsoft 专用修饰符。 有关详细信息，请参阅[Microsoft 专用的修饰符](../cpp/microsoft-specific-modifiers.md)。

   - **&** 运算符或**&&** 运算符。

   - 可选**const**和/或**易失性**限定符。

   - 标识符。

1. 可选初始值设定项。

指向数组和函数的更复杂声明符形式也适用于对数组和函数的引用。 有关详细信息，请参阅[指针](../cpp/pointers-cpp.md)。

多个声明符和初始值设定项可能出现在一个声明说明符后面的逗号分隔的列表中。 例如：

```cpp
int &i;
int &i, &j;
```

引用、指针和对象可以一起声明：

```cpp
int &ref, *ptr, k;
```

引用保留对象的地址，但语法行为与对象一样。

在下面的程序中，请注意对象的名称 `s` 和对象的引用 `SRef` 可在程序中以相同的方式使用：

## <a name="example"></a>示例

```cpp
// references.cpp
#include <stdio.h>
struct S {
   short i;
};

int main() {
   S  s;   // Declare the object.
   S& SRef = s;   // Declare the reference.
   s.i = 3;

   printf_s("%d\n", s.i);
   printf_s("%d\n", SRef.i);

   SRef.i = 4;
   printf_s("%d\n", s.i);
   printf_s("%d\n", SRef.i);
}
```

```Output
3
3
4
4
```

## <a name="see-also"></a>请参阅

[引用类型函数自变量](../cpp/reference-type-function-arguments.md)<br/>
[引用类型函数返回](../cpp/reference-type-function-returns.md)<br/>
[对指针的引用](../cpp/references-to-pointers.md)
