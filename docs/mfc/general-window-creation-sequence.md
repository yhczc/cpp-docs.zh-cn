---
title: 常用窗口创建序列
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: 949cf72910654b502ca4b57be72bedc2db63c315
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269222"
---
# <a name="general-window-creation-sequence"></a>常用窗口创建序列

当创建你自己，如子窗口的窗口时，框架使用得相同的过程中所述[文档/视图创建](../mfc/document-view-creation.md)。

提供的 MFC 使用的所有窗口类[两阶段构造](../mfc/one-stage-and-two-stage-construction-of-objects.md)。 也就是说，在 c + + 的调用期间**新**运算符，构造函数分配并初始化 c + + 对象但不会创建相应的 Windows 窗口。 可稍后通过调用[创建](../mfc/reference/cwnd-class.md#create)窗口对象的成员函数。

`Create`成员函数才可使 Windows 窗口，并将存储其`HWND`中 c + + 对象的公共数据成员[m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd)。 `Create` 提供创建参数通过完整的灵活性。 然后再调用`Create`，你可能想要的窗口类注册全局函数[AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)要设置帧的图标和类样式。

对于框架窗口，可以使用[LoadFrame](../mfc/reference/cframewnd-class.md#loadframe)成员函数而不是`Create`。 `LoadFrame` 可以使用较少的参数的 Windows 窗口。 它从资源，包括帧的标题、 图标、 快捷键对应表和菜单获取许多默认值。

> [!NOTE]
>  图标、 快捷键对应表和菜单资源必须具有公用的资源 ID，如**IDR_MAINFRAME**，才能由 LoadFrame 加载。

## <a name="what-do-you-want-to-know-more-about"></a>你想要了解更多信息

- [窗口对象](../mfc/window-objects.md)

- [注册窗口"类"](../mfc/registering-window-classes.md)

- [销毁窗口对象](../mfc/destroying-window-objects.md)

- [创建文档框架窗口](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>请参阅

[创建窗口](../mfc/creating-windows.md)
