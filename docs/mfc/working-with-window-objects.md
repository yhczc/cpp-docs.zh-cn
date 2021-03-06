---
title: 使用窗口对象
ms.date: 11/04/2016
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
ms.openlocfilehash: c696d880ffa69b0a0399c5282621546c5783ebe4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265634"
---
# <a name="working-with-window-objects"></a>使用窗口对象

使用两种类型的活动的窗口调用：

- 处理 Windows 消息

- 在窗口中绘制

若要处理 Windows 消息在任何窗口，其中包括你自己的子窗口，请参阅[消息映射到函数](../mfc/reference/mapping-messages-to-functions.md)来将消息映射到 c + + 窗口类。 然后编写消息处理程序成员函数在类中。

Framework 应用程序中的大部分绘图发生在视图中，其[OnDraw](../mfc/reference/cview-class.md#ondraw)必须绘制窗口的内容时调用成员函数。 如果您的窗口是子节点的视图，您可能委派某些视图的绘制到子窗口通过让`OnDraw`调用其中一个窗口的成员函数。

在任何情况下，你将需要绘制的设备上下文。 可以使用常用的画笔、 画笔和与您的窗口相关联的设备上下文中包含的其他图形对象。 或者，可以修改这些对象，以获得所需的绘制效果。 与您根据需要设置的设备上下文，调用成员函数的类[CDC](../mfc/reference/cdc-class.md) （设备上下文类） 绘制线条、 形状和文本; 若要使用的颜色; 并使用同一个坐标系统。

## <a name="what-do-you-want-to-know-more-about"></a>你想要了解更多信息

- [消息处理和映射](../mfc/message-handling-and-mapping.md)

- [在视图中绘制](../mfc/drawing-in-a-view.md)

- [设备上下文](../mfc/device-contexts.md)

- [图形对象](../mfc/graphic-objects.md)

## <a name="see-also"></a>请参阅

[窗口对象](../mfc/window-objects.md)
