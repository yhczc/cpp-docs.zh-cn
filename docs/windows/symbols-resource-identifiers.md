---
title: 资源标识符 （符号） （c + +）
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.identifiers
helpviewer_keywords:
- symbols [C++], resource identifiers
- symbols [C++], creating
- resource symbols
- symbols [C++], editing
- resource editors [C++], resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
ms.openlocfilehash: 63971ba381394bcaf905d614496511b7aa0d01f3
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "57563311"
---
# <a name="resource-identifiers-symbols-c"></a>资源标识符 （符号） （c + +）

符号是一个资源标识符 (ID)，包括两个部分，例如映射为符号的值 （整数） 符号名 （文本字符串）：

```
IDC_EDITNAME = 5100
```

符号名通常称为标识符。

在资源编辑器中处理时，符号会在源代码中提供说明性方法来引用资源和用户界面对象。 可以使用 [资源符号对话框](../windows/viewing-resource-symbols.md)在一个方便的位置查看和操作符号。

随着应用程序大小和复杂度的增长，资源和符号的数量也随之增加。 跟踪分散在多个文件中的大量符号就变得尤为困难。 **资源符号**对话框通过提供一个中心工具，你可以通过它来简化符号管理：

- [创建符号](../windows/creating-new-symbols.md)

- [管理符号](../windows/changing-a-symbol-or-symbol-name-id.md)

- [查看预定义的符号 ID](../windows/predefined-symbol-ids.md)

创建新资源或资源对象时， [资源编辑器](../windows/resource-editors.md) 会提供资源的默认名称，例如 `IDC_RADIO1`，并向它分配一个值。 这种名称加值定义存储在`Resource.h`文件。

> [!NOTE]
> 从一个.rc 文件向另一个复制资源或资源对象时，Visual C++ 可更改传输资源的符号值，或同时更改符号名和符号值，以避免与现有文件中的符号名或符号值发生冲突。

## <a name="requirements"></a>要求

Win32

## <a name="see-also"></a>请参阅

[使用资源文件](../windows/working-with-resource-files.md)<br/>
[资源文件](../windows/resource-files-visual-studio.md)<br/>
[资源编辑器](../windows/resource-editors.md)<br/>