---
title: location 类
ms.date: 11/04/2016
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
ms.openlocfilehash: 5e90dd3b23b33f6699f2df4ce0df9178f95816b8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273240"
---
# <a name="location-class"></a>location 类

硬件上物理位置的抽象。

## <a name="syntax"></a>语法

```
class location;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[location](#ctor)|已重载。 构造 `location` 对象。|
|[~ location 析构函数](#dtor)|销毁 `location` 对象。|

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[current](#current)|返回表示调用线程执行的最具体位置的 `location` 对象。|
|[from_numa_node](#from_numa_node)|返回表示给定的 NUMA 节点的 `location` 对象。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[operator!=](#operator_neq)|确定两个 `location` 对象是否表示不同的位置。|
|[operator=](#operator_eq)|将另一 `location` 对象的内容分配给此对象。|
|[operator==](#operator_eq_eq)|确定两个`location`对象表示相同的位置。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`location`

## <a name="requirements"></a>要求

**标头：** concrt.h

**命名空间：** 并发

##  <a name="dtor"></a> ~location

销毁 `location` 对象。

```
~location();
```

##  <a name="current"></a> 当前

返回表示调用线程执行的最具体位置的 `location` 对象。

```
static location __cdecl current();
```

### <a name="return-value"></a>返回值

表示调用线程执行的最具体位置的位置。

##  <a name="from_numa_node"></a> from_numa_node

返回表示给定的 NUMA 节点的 `location` 对象。

```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>参数

*_NumaNodeNumber*<br/>
要构造位置的 NUMA 节点号。

### <a name="return-value"></a>返回值

表示 `_NumaNodeNumber` 参数指定的 NUMA 节点的位置。

##  <a name="ctor"></a> 位置

构造 `location` 对象。

```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```

### <a name="parameters"></a>参数

*_Src*<br/>

*_LocationType*<br/>

*_Id*<br/>

*_BindingId*<br/>

*_PBinding*<br/>
（可选）绑定指针。

### <a name="remarks"></a>备注

默认构造的位置表示整个系统。

##  <a name="operator_neq"></a> 运算符 ！ =

确定两个 `location` 对象是否表示不同的位置。

```
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>参数

*_Rhs*<br/>
操作数`location`。

### <a name="return-value"></a>返回值

**true**如果两个位置不同， **false**否则为。

##  <a name="operator_eq"></a> 运算符 =

将另一 `location` 对象的内容分配给此对象。

```
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>参数

*_Rhs*<br/>
源 `location` 对象。

### <a name="return-value"></a>返回值

##  <a name="operator_eq_eq"></a> 运算符 = =

确定两个`location`对象表示相同的位置。

```
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>参数

*_Rhs*<br/>
操作数`location`。

### <a name="return-value"></a>返回值

**true**如果两个位置是相同的并**false**否则为。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
