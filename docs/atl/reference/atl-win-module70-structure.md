---
title: _ATL_WIN_MODULE70 结构
ms.date: 11/04/2016
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
ms.openlocfilehash: 0b636d328852daf821269230aae443cef084578b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299707"
---
# <a name="atlwinmodule70-structure"></a>_ATL_WIN_MODULE70 结构

使用开窗中的代码 atl。

## <a name="syntax"></a>语法

```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize;
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```

## <a name="members"></a>成员

`cbSize`<br/>
用于版本控制的结构的大小。

`m_csWindowCreate`<br/>
用于序列化窗口注册代码的访问权限。 在内部由 atl。

`m_pCreateWndList`<br/>
用于将 windows 绑定到它们的对象。 在内部由 atl。

`m_rgWindowClassAtoms`<br/>
用于跟踪窗口类注册，以便它们可以成为在终止时未正确注册。 在内部由 atl。

## <a name="remarks"></a>备注

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)定义的 typedef 为`_ATL_WIN_MODULE70`。

## <a name="requirements"></a>要求

**标头：** atlbase.h

## <a name="see-also"></a>请参阅

[类和结构](../../atl/reference/atl-classes.md)
