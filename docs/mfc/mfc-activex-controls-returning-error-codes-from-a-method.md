---
title: MFC ActiveX 控件：从方法返回错误代码
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
ms.openlocfilehash: 0800c1827c636dd81e2928e33c0ee2afde4c94ac
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259134"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX 控件：从方法返回错误代码

本文介绍如何通过 ActiveX 控件方法返回错误代码。

若要指示方法中出现错误，应使用[colecontrol:: Throwerror](../mfc/reference/colecontrol-class.md#throwerror)成员函数采用 SCODE （状态代码） 作为参数。 可以使用预定义的 SCODE 或你自己的一个定义。

> [!NOTE]
>  `ThrowError` 意味着仅用作通过属性的 Get 或 Set 函数或自动化方法返回错误的一种方式。 这是适当异常处理程序将出现在堆栈上的唯一时间。

最常见的预定义 SCODEs，例如，存在帮助器函数[colecontrol:: Setnotsupported](../mfc/reference/colecontrol-class.md#setnotsupported)， [colecontrol:: Getnotsupported](../mfc/reference/colecontrol-class.md#getnotsupported)，和[COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

预定义 SCODEs 和定义自定义 SCODEs 的说明的列表，请参阅的部分[ActiveX 控件中处理错误](../mfc/mfc-activex-controls-advanced-topics.md)ActiveX 控件中：高级的主题。

有关报告代码的其他几个方面的异常的详细信息，请参阅[COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror)和部分[ActiveX 控件中处理错误](../mfc/mfc-activex-controls-advanced-topics.md)ActiveX 控件中：高级的主题。

## <a name="see-also"></a>请参阅

[MFC ActiveX 控件](../mfc/mfc-activex-controls.md)
