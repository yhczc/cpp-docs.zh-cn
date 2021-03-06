---
title: COM 接口入口点
ms.date: 11/04/2016
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
ms.openlocfilehash: 3c7b0067e66dfa8bc6f52bcd67637370f8c9a758
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288060"
---
# <a name="com-interface-entry-points"></a>COM 接口入口点

对于 COM 接口的成员函数，使用[METHOD_PROLOGUE](com-interface-entry-points.md#method_prologue)宏维护适当的全局状态时调用导出接口的方法。

通常，由 `CCmdTarget` 派生的对象实现的接口的成员函数已使用此宏提供 `pThis` 指针的自动初始化。 例如：

[!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]

有关其他信息，请参阅[技术说明 38](../mfc/tn038-mfc-ole-iunknown-implementation.md)有关 MFC/OLE`IUnknown`实现。

按如下方式定义 `METHOD_PROLOGUE` 宏：

```cpp
#define METHOD_PROLOGUE(theClass, localClass) \
    theClass* pThis = \
    ((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \
    AFX_MANAGE_STATE(pThis->m_pModuleState) \
```

与管理全局状态相关的宏的部分是：

`AFX_MANAGE_STATE( pThis->m_pModuleState )`

在此表达式中， *m_pModuleState*被假定为包含对象的成员变量。 它由 `CCmdTarget` 基类实现，并在实例化对象时由 `COleObjectFactory` 初始化为适当的值。

## <a name="see-also"></a>请参阅

[管理 MFC 模块的状态数据](../mfc/managing-the-state-data-of-mfc-modules.md)
