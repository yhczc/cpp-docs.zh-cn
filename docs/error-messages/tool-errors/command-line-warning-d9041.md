---
title: 命令行警告 D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: 2311c61c4d661d58302308f06b08971f94cdacab
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816303"
---
# <a name="command-line-warning-d9041"></a>命令行警告 D9041

无效的值 'value'。 / 选项;假设 'value';添加 / 分析命令行选项指定此警告时

代码分析警告编号已添加到 **/wd**， **/we**， **/wo**，或者 **/wl**但未指定命令行选项**分析 /** 命令行选项。 若要纠正此错误，请添加 **/analyze**命令行选项或从相应删除无效的警告编号 **/w**命令行选项。

## <a name="example"></a>示例

下面的命令行示例将生成警告 D9041:

```
cl /EHsc /LD /wd6001 filename.cpp
```

若要修复此警告，将添加**分析 /** 命令行选项。 如果 **/analyze**是你的编译器版本上不支持，删除从无效的警告编号 **/wd**选项。

## <a name="see-also"></a>请参阅

[命令行错误 D8000 - D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC 编译器选项](../../build/reference/compiler-options.md)