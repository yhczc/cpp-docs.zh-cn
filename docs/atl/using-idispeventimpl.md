---
title: 使用 IDispEventImpl (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
ms.openlocfilehash: 59f8e7d095f3d514ab41b28dc37f5d3c707bbd08
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820294"
---
# <a name="using-idispeventimpl"></a>使用 IDispEventImpl

当使用`IDispEventImpl`来处理事件，你将需要：

- 从类派生[IDispEventImpl](../atl/reference/idispeventimpl-class.md)。

- 将事件接收器映射添加到您的类。

- 将条目添加到使用事件接收器映射[SINK_ENTRY](reference/composite-control-macros.md#sink_entry)或[SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)宏。

- 实现你感兴趣处理的方法。

- 通知和取消通知事件源。

## <a name="example"></a>示例

下面的示例演示如何处理`DocumentChange`由 Word 的事件触发**应用程序**对象。 此事件指一种方法上`ApplicationEvents`调度接口。

该示例摘自[ATLEventHandling 示例](../visual-cpp-samples.md)。

```cpp
[ uuid(000209F7-0000-0000-C000-000000000046), hidden ]
dispinterface ApplicationEvents {
properties:
methods:
    [id(0x00000001), restricted, hidden]
    void Startup();

    [id(0x00000002)]
    void Quit();

    [id(0x00000003)]
    void DocumentChange();
};
```

该示例使用`#import`从 Word 的类型库生成必需的标头文件。 如果你想要使用此示例与其他版本的 Word，则必须指定正确 mso dll 文件。 例如，Office 2000 提供 mso9.dll 并 OfficeXP 提供 mso.dll 有关的问题。 此代码从 stdafx.h 简化：

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

下面的代码所示 NotSoSimple.h。 通过注释记录了相关代码：

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>请参阅

[事件处理](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling 示例](../visual-cpp-samples.md)
