---
title: 打印和打印预览
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
ms.openlocfilehash: 4ca6663aefce219fad4d2e3be74215d2a78206a8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263658"
---
# <a name="printing-and-print-preview"></a>打印和打印预览

MFC 支持打印和打印预览的应用程序的文档都能通过类[CView](../mfc/reference/cview-class.md)。 对于基本打印和打印预览，只需重写视图类的[OnDraw](../mfc/reference/cview-class.md#ondraw)成员函数，则仍必须执行操作。 该函数可以绘制到屏幕上，实际的打印机的打印机设备上下文视图，或用于模拟您在屏幕上的打印机设备上下文。

此外可以添加代码来管理多页文档打印和预览，若要分页打印的文档，并将页眉和页脚添加到它们。

此系列文章介绍如何在 Microsoft 基础类库 (MFC) 实现打印以及如何充分利用已内置到框架的打印体系结构。 文章还介绍了 MFC 如何支持轻松实现打印预览功能以及如何使用和修改该功能。

## <a name="what-do-you-want-to-know-more-about"></a>你想要了解更多信息

- [打印](../mfc/printing.md)

- [打印预览体系结构](../mfc/print-preview-architecture.md)

- [示例](../visual-cpp-samples.md)

## <a name="see-also"></a>请参阅

[用户界面元素](../mfc/user-interface-elements-mfc.md)
