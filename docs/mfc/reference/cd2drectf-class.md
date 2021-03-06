---
title: CD2DRectF 类
ms.date: 11/04/2016
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
ms.openlocfilehash: 8e5c22fe15ce0d930f81dd16673927d5299bf630
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290828"
---
# <a name="cd2drectf-class"></a>CD2DRectF 类

`D2D1_RECT_F`的包装器。

## <a name="syntax"></a>语法

```
class CD2DRectF : public D2D1_RECT_F;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[CD2DRectF::CD2DRectF](#cd2drectf)|已重载。 构造`CD2DRectF`对象从`D2D1_RECT_F`对象。|

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[CD2DRectF::IsNull](#isnull)|返回**布尔**值，该值指示表达式是否包含任何有效的数据 (NULL)。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DRectF::operator CRect](#operator_crect)|将转换`CD2DRectF`到`CRect`对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`D2D1_RECT_F`

`CD2DRectF`

## <a name="requirements"></a>要求

**标头：** afxrendertarget.h

##  <a name="cd2drectf"></a>  CD2DRectF::CD2DRectF

构造 CRect 对象从一个 CD2DRectF 对象。

```
CD2DRectF(const CRect& rect);
CD2DRectF(const D2D1_RECT_F& rect);
  CD2DRectF(const D2D1_RECT_F* rect);

CD2DRectF(
    FLOAT fLeft = 0.,
    FLOAT fTop = 0.,
    FLOAT fRight = 0.,
    FLOAT fBottom = 0.);
```

### <a name="parameters"></a>参数

*rect*<br/>
源矩形

*fLeft*<br/>
源左边缘坐标

*fTop*<br/>
源上边缘坐标

*fRight*<br/>
源角坐标

*fBottom*<br/>
源下边缘坐标

##  <a name="isnull"></a>  CD2DRectF::IsNull

返回一个布尔值，该值指示表达式是否包含任何有效的数据 (Null)。

```
BOOL IsNull() const;
```

### <a name="return-value"></a>返回值

矩形的上、 左、 下、 和正确的值均相等，则为 0; 如果为 TRUE否则为 FALSE。

##  <a name="operator_crect"></a>  CD2DRectF::operator CRect

将 CD2DRectF 转换为 CRect 对象。

```
operator CRect();
```

### <a name="return-value"></a>返回值

D2D 矩形的当前值。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
