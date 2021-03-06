---
title: 链接器工具警告 LNK4078
ms.date: 11/04/2016
f1_keywords:
- LNK4078
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
ms.openlocfilehash: d20eb0523ffebe9229d05b6316772259661f6020
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614144"
---
# <a name="linker-tools-warning-lnk4078"></a>链接器工具警告 LNK4078

找到具有不同的属性的多个 section name 节

链接找到了两个或更多部分具有相同名称但不同的属性。

已创建的以前版本的链接或 LIB 的导入库或导出文件可以导致此警告。

重新创建文件并重新链接。

## <a name="example"></a>示例

LNK4078 也由一项重大更改： 命名的节[init_seg](../../preprocessor/init-seg.md) x86 上已读/写，现在只读的。

下面的示例生成 LNK4078。

```
// LNK4078.cpp
// compile with: /W1
// LNK4078 expected
#include <stdio.h>
#pragma warning(disable : 4075)
typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors to call
PF pfx[200];   // pointers to destructors.

struct A { A() {} };

int myexit (PF pf) { return 0; }

#pragma section(".mine$a", read, write)
// try the following line instead
// #pragma section(".mine$a", read)
__declspec(allocate(".mine$a")) int ii = 1;

#pragma section(".mine$z", read, write)
// try the following line instead
// #pragma section(".mine$z", read)
__declspec(allocate(".mine$z")) int i = 1;

#pragma data_seg()
#pragma init_seg(".mine$m", myexit)
A bbbb;
A cccc;
int main() {}
```