---
title: CAutoPtrElementTraits 类
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
ms.openlocfilehash: d217441048403b0ff5361f8049b76367174812f1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299456"
---
# <a name="cautoptrelementtraits-class"></a>CAutoPtrElementTraits 类

在创建集合的智能指针时，此类提供方法、 静态函数和有用的 typedef。

> [!IMPORTANT]
>  不能在 Windows 运行时中执行的应用程序中使用此类和其成员。

## <a name="syntax"></a>语法

```
template<typename T>
class CAutoPtrElementTraits
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```

#### <a name="parameters"></a>参数

*T*<br/>
指针类型。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|要用于将元素添加到集合类对象的数据类型。|
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|要用于从集合类对象中检索元素的数据类型。|

## <a name="remarks"></a>备注

此类提供帮助包含智能指针集合类对象的创建方法，静态函数和 typedef。 类[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)并[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)派生`CAutoPtrElementTraits`。 如果构建的智能指针集合需要新的向量和 delete 运算符，使用[CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md)相反。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoPtrElementTraits`

## <a name="requirements"></a>要求

**标头：** atlcoll.h

##  <a name="inargtype"></a>  CAutoPtrElementTraits::INARGTYPE

要用于将元素添加到集合类对象的数据类型。

```
typedef CAutoPtr<T>& INARGTYPE;
```

##  <a name="outargtype"></a>  CAutoPtrElementTraits::OUTARGTYPE

要用于从集合类对象中检索元素的数据类型。

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>请参阅

[CDefaultElementTraits 类](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
