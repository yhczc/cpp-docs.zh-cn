---
title: WM_ 消息：T - Z
ms.date: 11/04/2016
f1_keywords:
- ON_WM_TCARD
- ON_WM_WININICHANGE
- ON_WM_VSCROLLCLIPBOARD
- ON_WM_VSCROLL
- ON_WM_WINDOWPOSCHANGED
- ON_WM_TIMECHANGE
- ON_WM_TIMER
- ON_WM_VKEYTOITEM
- ON_WM_WINDOWPOSCHANGING
helpviewer_keywords:
- ON_WM_VSCROLLCLIPBOARD [MFC]
- ON_WM_WININICHANGE [MFC]
- ON_WM_WINDOWPOSCHANGED [MFC]
- ON_WM_TCARD [MFC]
- ON_WM_TIMECHANGE [MFC]
- ON_WM_TIMER [MFC]
- WM_ messages [MFC]
- ON_WM_WINDOWPOSCHANGING [MFC]
- ON_WM_VKEYTOITEM [MFC]
- ON_WM_VSCROLL
ms.assetid: c528bb2e-ddb5-4da6-b652-432a387408b8
ms.openlocfilehash: 7b5dbcb52ef7a61712f2c59c217a71f533799f67
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271848"
---
# <a name="wm-messages-t---z"></a>WM_ 消息：T - Z

下面的映射条目对应于函数原型：

|映射条目|函数原型|
|---------------|------------------------|
|ON_WM_TCARD()|afx_msg void [OnTCard](../../mfc/reference/cwnd-class.md#ontcard)( UINT, DWORD );|
|ON_WM_TIMECHANGE()|afx_msg void [OnTimeChange](../../mfc/reference/cwnd-class.md#ontimechange)( );|
|ON_WM_TIMER()|afx_msg void [OnTimer](../../mfc/reference/cwnd-class.md#ontimer)( UINT_PTR );|
|ON_WM_UNICHAR()|afx_msg void [OnUniChar](../../mfc/reference/cwnd-class.md#onunichar)( UINT, UINT, UINT );|
|ON_WM_UNINITMENUPOPUP()|afx_msg void [OnUnInitMenuPopup](../../mfc/reference/cwnd-class.md#onuninitmenupopup)( CMenu*, UINT );|
|ON_WM_USERCHANGED()|afx_msg void [OnUserChanged](../../mfc/reference/cwnd-class.md#onuserchanged)();|
|ON_WM_VKEYTOITEM()|afx_msg int [OnVKeyToItem](../../mfc/reference/cwnd-class.md#onvkeytoitem)( UINT, CWnd*, UINT );|
|ON_WM_VSCROLL()|afx_msg void [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)( UINT, UINT, CWnd* );|
|ON_WM_VSCROLLCLIPBOARD()|afx_msg void [OnVScrollClipboard](../../mfc/reference/cwnd-class.md#onvscrollclipboard)( CWnd*, UINT, UINT );|
|ON_WM_WINDOWPOSCHANGED()|afx_msg void [OnWindowPosChanged](../../mfc/reference/cwnd-class.md#onwindowposchanged)( WINDOWPOS*);|
|ON_WM_WINDOWPOSCHANGING()|afx_msg void [OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)( WINDOWPOS*);|
|ON_WM_WININICHANGE()|afx_msg void [OnWinIniChange](../../mfc/reference/cwnd-class.md#onwininichange)( LPSTR );|
|ON_WM_WTSSESSION_CHANGE()|afx_msg void [OnSessionChange](../../mfc/reference/cwnd-class.md#onsessionchange)( UINT, UINT );|
|ON_WM_XBUTTONDBLCLK()|afx_msg void [OnXButtonDblClk](../../mfc/reference/cwnd-class.md#onxbuttondblclk)( UINT, UINT, CPoint );|
|ON_WM_XBUTTONDOWN()|afx_msg void [OnXButtonDown](../../mfc/reference/cwnd-class.md#onxbuttondown)( UINT, UINT, CPoint );|
|ON_WM_XBUTTONUP()|afx_msg void [OnXButtonUp](../../mfc/reference/cwnd-class.md#onxbuttonup)( UINT, UINT, CPoint );|

## <a name="see-also"></a>请参阅

[消息映射](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ 消息的处理程序](../../mfc/reference/handlers-for-wm-messages.md)
