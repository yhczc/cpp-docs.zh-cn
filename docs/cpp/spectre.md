---
title: spectre
ms.date: 1/23/2018
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
ms.openlocfilehash: 2377a3c23be1e27bfe4f2df23eb00823635fa05d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592005"
---
# <a name="spectre"></a>spectre

**Microsoft 专用**

告知编译器不要插入 Spectre 变体 1 推理执行屏障的函数的说明。

## <a name="syntax"></a>语法

> **__declspec( spectre(nomitigation) )**

## <a name="remarks"></a>备注

[/Qspectre](../build/reference/qspectre.md)编译器选项将导致编译器插入推理执行屏障说明的分析表明存在 Spectre 变体 1 安全漏洞。 发出的具体说明取决于处理器。 这些说明应该对代码大小或性能的影响最小，可能有你的代码不受此漏洞，并且需要最大性能。

专家分析可能确定函数是安全从 Spectre 变体 1 边界检查绕过缺陷。 在这种情况下，可以通过应用取消生成函数内的缓解代码`__declspec(spectre(nomitigation))`至函数声明。

> [!CAUTION]
> **/Qspectre**推理执行屏障指令提供重要的安全保护，并且对性能的影响微不足道。 因此，我们建议您不要取消它们，但在以下罕见的情况下除外：函数的性能至关重要，并且已经知道函数是安全的。

## <a name="example"></a>示例

下面的代码演示如何使用 `__declspec(spectre(nomitigation))`。

```cpp
// compile with: /c /Qspectre
static __declspec(spectre(nomitigation))
int noSpectreIssues() {
    // No Spectre variant 1 vulnerability here
    // ...
    return 0;
}

int main() {
    noSpectreIssues();
    return 0;
}
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__declspec](../cpp/declspec.md)<br/>
[关键字](../cpp/keywords-cpp.md)<br/>
[/Qspectre](../build/reference/qspectre.md)
