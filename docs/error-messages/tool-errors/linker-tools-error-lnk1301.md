---
title: 链接器工具错误 LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: 6a82d7756f1460c56d87a3d7b1360c140de19827
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812091"
---
# <a name="linker-tools-error-lnk1301"></a>链接器工具错误 LNK1301

发现，与 /LTCG:parameter 不兼容 LTCG clr 模块

使用 /clr 和 /GL 编译的模块传递给链接器，以及按配置优化 (PGO) 参数的 /LTCG。

/Clr 模块不支持按配置优化。

有关详细信息，请参见:

- [/GL（全程序优化）](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG（链接时间代码生成）](../../build/reference/ltcg-link-time-code-generation.md)

- [/cgthreads（公共语言运行时编译）](../../build/reference/clr-common-language-runtime-compilation.md)

- [按配置文件优化](../../build/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>更正此错误

1. 不使用 /clr 编译或不链接与 /LTCG 的 PGO 参数之一。

## <a name="example"></a>示例

下面的示例生成 LNK1301:

```
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```