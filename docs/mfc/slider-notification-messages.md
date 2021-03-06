---
title: 滑块通知消息
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
ms.openlocfilehash: bee2d602512ea1a6af39b0bb218ee7333b399c80
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294223"
---
# <a name="slider-notification-messages"></a>滑块通知消息

滑块控件通知用户操作其父窗口发送 WM_HSCROLL 或 WM_VSCROLL 消息，具体取决于方向的滑块控件的父级。 若要处理这些消息，请将 WM_HSCROLL 和 WM_VSCROLL 消息的处理程序添加到父窗口。 [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll)并[OnVScroll](../mfc/reference/cwnd-class.md#onvscroll)成员函数将通知代码、 滑块和指向指针的位置传递[CSliderCtrl](../mfc/reference/csliderctrl-class.md)对象。 请注意，指针为类型`CScrollBar *`即使它指向`CSliderCtrl`对象。 您可能需要类型转换此指针，如果您需要处理滑块控件。

而不是使用滚动条通知代码，滑块控件将发送一组不同的通知代码。 仅当用户使用键盘与滑块控件交互时，滑块控件将发送 TB_BOTTOM、 TB_LINEDOWN、 TB_LINEUP 和 TB_TOP 通知代码。 当用户使用鼠标时仅发送 TB_THUMBPOSITION 和 TB_THUMBTRACK 通知消息。 在这两种情况下发送 TB_ENDTRACK、 TB_PAGEDOWN 和 TB_PAGEUP 通知代码。

下表列出了滑块控件通知消息和导致发送通知的事件 （虚拟键代码或鼠标事件）。 （有关标准虚拟键代码的列表，请参见 Winuser.h。）

|通知消息|导致发送通知的事件|
|--------------------------|-------------------------------------------|
|TB_BOTTOM|VK_END|
|TB_ENDTRACK|WM_KEYUP （用户发布发送相关的虚拟键代码的密钥）|
|TB_LINEDOWN|VK_RIGHT 或 VK_DOWN|
|TB_LINEUP|VK_LEFT 或 VK_UP|
|TB_PAGEDOWN|VK_NEXT （用户已单击下方或右侧的滑块的通道）|
|TB_PAGEUP|VK_PRIOR （用户单击的上方或左侧的滑块的通道）|
|TB_THUMBPOSITION|WM_LBUTTONUP 以下 TB_THUMBTRACK 通知消息|
|TB_THUMBTRACK|（用户通过拖动滑块） 的滑块移动|
|TB_TOP|VK_HOME|

## <a name="see-also"></a>请参阅

[使用 CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
