---
title: 编译器警告（等级 4）C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: f88a61a40a789c31e80875d785b95136ac69253c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466932"
---
# <a name="compiler-warning-level-4-c4481"></a>编译器警告（等级 4）C4481

使用了非标准扩展： 重写说明符 keyword

使用不在 c + + 标准，例如，一个还在 /clr 下有效的重写说明符的关键字。  有关详细信息，请参阅

- [/cgthreads（公共语言运行时编译）](../../build/reference/clr-common-language-runtime-compilation.md)

- [重写说明符](../../windows/override-specifiers-cpp-component-extensions.md)

## <a name="example"></a>示例

下面的示例生成 C4481。

```
// C4481.cpp
// compile with: /W4 /c
class B {
   virtual void f(unsigned);
};

class C : B {
   void f(unsigned) override;   // C4481
   void f2(unsigned);
};
```