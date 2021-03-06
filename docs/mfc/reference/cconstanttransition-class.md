---
title: CConstantTransition 类
ms.date: 11/04/2016
f1_keywords:
- CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::Create
- AFXANIMATIONCONTROLLER/CConstantTransition::m_duration
helpviewer_keywords:
- CConstantTransition [MFC], CConstantTransition
- CConstantTransition [MFC], Create
- CConstantTransition [MFC], m_duration
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
ms.openlocfilehash: 9641af2f184d2edaa82922363dff75783e79f87e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326330"
---
# <a name="cconstanttransition-class"></a>CConstantTransition 类

封装常量转换。

## <a name="syntax"></a>语法

```
class CConstantTransition : public CBaseTransition;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[CConstantTransition::CConstantTransition](#cconstanttransition)|构造转换对象并初始化其持续时间。|

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[CConstantTransition::Create](#create)|调用要创建封装的转换 COM 对象的转换库。 (重写[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create)。)|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CConstantTransition::m_duration](#m_duration)|过渡的持续时间。|

## <a name="remarks"></a>备注

常量在转换期间，动画变量的值保持为初始值过渡的持续时间内。 因为会自动清除所有转换，我们建议分配它们使用新运算符。 封装 IUIAnimationTransition 创建 COM 对象通过 CAnimationController::AnimateGroup，直到它为 NULL。 创建此 COM 对象不起作用之后更改成员变量。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CConstantTransition`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

##  <a name="cconstanttransition"></a>  CConstantTransition::CConstantTransition

构造转换对象并初始化其持续时间。

```
CConstantTransition (UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>参数

*duration*<br/>
过渡的持续时间。

##  <a name="create"></a>  CConstantTransition::Create

调用要创建封装的转换 COM 对象的转换库。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>参数

*pLibrary*<br/>
一个指向[IUIAnimationTransitionLibrary 接口](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)，用于定义的标准转换库。

### <a name="return-value"></a>返回值

如果成功，则创建转换，则返回 TRUE否则为 FALSE。

##  <a name="m_duration"></a>  CConstantTransition::m_duration

过渡的持续时间。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
