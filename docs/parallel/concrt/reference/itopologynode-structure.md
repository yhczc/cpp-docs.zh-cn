---
title: ITopologyNode 结构
ms.date: 11/04/2016
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
ms.openlocfilehash: 867e0543d1b9f2810a3fe761f038947c4d88da4d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268624"
---
# <a name="itopologynode-structure"></a>ITopologyNode 结构

资源管理器定义的拓扑节点的接口。 一个节点包含一个或多个执行资源。

## <a name="syntax"></a>语法

```
struct ITopologyNode;
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[ITopologyNode::GetExecutionResourceCount](#getexecutionresourcecount)|返回在此节点下组合在一起的执行资源的数量。|
|[ITopologyNode::GetFirstExecutionResource](#getfirstexecutionresource)|返回在此节点下以枚举顺序分组的第一个执行资源。|
|[ITopologyNode::GetId](#getid)|返回此节点的资源管理器的唯一标识符。|
|[ITopologyNode::GetNext](#getnext)|返回一个指向枚举顺序中下一拓扑节点的接口。|
|[ITopologyNode::GetNumaNode](#getnumanode)|返回 Windows 分配给此资源管理器节点所属的 NUMA 节点数。|

## <a name="remarks"></a>备注

此接口通常用于为通过资源管理器已观察到引导系统的拓扑。

## <a name="inheritance-hierarchy"></a>继承层次结构

`ITopologyNode`

## <a name="requirements"></a>要求

**标头：** concrtrm.h

**命名空间：** 并发

##  <a name="getexecutionresourcecount"></a>  Itopologynode:: Getexecutionresourcecount 方法

返回在此节点下组合在一起的执行资源的数量。

```
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>返回值

在此节点下组合在一起的执行资源的数量。

##  <a name="getfirstexecutionresource"></a>  Itopologynode:: Getfirstexecutionresource 方法

返回在此节点下以枚举顺序分组的第一个执行资源。

```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>返回值

在此节点下以枚举顺序分组的第一个执行资源。

##  <a name="getid"></a>  Itopologynode:: Getid 方法

返回此节点的资源管理器的唯一标识符。

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>返回值

此节点的资源管理器的唯一标识符。

### <a name="remarks"></a>备注

并发运行时表示硬件线程的处理器节点组中的系统上。 节点通常派生自系统的硬件拓扑。 例如，特定的套接字或特定 NUMA 节点上的所有处理器可能都属于同一处理器节点。 资源管理器将分配给从这些节点的唯一标识符`0`包括`nodeCount - 1`，其中`nodeCount`表示系统上的处理器节点的总数。

可以从函数获取的节点计数[GetProcessorNodeCount](concurrency-namespace-functions.md)。

##  <a name="getnext"></a>  Itopologynode:: Getnext 方法

返回一个指向枚举顺序中下一拓扑节点的接口。

```
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>返回值

一个指向枚举顺序中下一节点的接口。 如果系统拓扑的枚举顺序中没有更多的节点，则此方法将返回值 `NULL`。

##  <a name="getnumanode"></a>  Itopologynode:: Getnumanode 方法

返回 Windows 分配给此资源管理器节点所属的 NUMA 节点数。

```
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>返回值

Windows 分配给此资源管理器节点所属的 NUMA 节点数。

### <a name="remarks"></a>备注

属于此节点的虚拟处理器根上运行的线程代理将具有关联到至少是此方法返回的 NUMA 节点的 NUMA 节点级别。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
