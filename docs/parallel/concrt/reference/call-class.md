---
title: call 类
ms.date: 11/04/2016
f1_keywords:
- call
- AGENTS/concurrency::call
- AGENTS/concurrency::call::call
- AGENTS/concurrency::call::process_input_messages
- AGENTS/concurrency::call::process_message
- AGENTS/concurrency::call::propagate_message
- AGENTS/concurrency::call::send_message
- AGENTS/concurrency::call::supports_anonymous_source
helpviewer_keywords:
- call class
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
ms.openlocfilehash: 9651a74fdb07ad96d6f01edb6818ea48d697c37c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271952"
---
# <a name="call-class"></a>call 类


  `call` 消息块是多源、有序的 `target_block`，可以在接收消息时调用指定函数。

## <a name="syntax"></a>语法

```
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>参数

*T*<br/>
传播到此块的消息的负载类型。

*_FunctorType*<br/>
该块可以接受的函数的签名。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[call](#ctor)|已重载。 构造 `call` 消息块。|
|[~ call 析构函数](#dtor)|销毁`call`消息块。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[process_input_messages](#process_input_messages)|输入消息执行调用的函数。|
|[process_message](#process_message)|处理已接受此消息`call`消息块。|
|[propagate_message](#propagate_message)|以异步方式从将消息传递`ISource`到此块`call`消息块。 由调用`propagate`方法，调用由源块时。|
|[send_message](#send_message)|以同步方式从将消息传递`ISource`到此块`call`消息块。 由调用`send`方法，调用由源块时。|
|[supports_anonymous_source](#supports_anonymous_source)|重写 `supports_anonymous_source` 方法，以指示该块可以接受由未链接的源为其提供的消息。 (重写[itarget:: Supports_anonymous_source](itarget-class.md#supports_anonymous_source)。)|

## <a name="remarks"></a>备注

有关详细信息，请参阅[异步消息块](../../../parallel/concrt/asynchronous-message-blocks.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[ITarget](itarget-class.md)

[target_block](target-block-class.md)

`call`

## <a name="requirements"></a>要求

**标头：** agents.h

**命名空间：** 并发

##  <a name="ctor"></a> 调用

构造 `call` 消息块。

```
call(
    _Call_method const& _Func);

call(
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func,
    filter_method const& _Filter);
```

### <a name="parameters"></a>参数

*_Func*<br/>
将为每个接受的消息调用一个函数。

*_Filter*<br/>
确定是否应接受提供的消息的筛选器函数。

*_PScheduler*<br/>
在其中计划了 `Scheduler` 消息块的传播任务的 `call` 对象。

*_PScheduleGroup*<br/>
在其中计划了 `ScheduleGroup` 消息块的传播任务的 `call` 对象。 所用 `Scheduler` 对象由该计划组提示。

### <a name="remarks"></a>备注

如果未指定 `_PScheduler` 或 `_PScheduleGroup` 函数，运行时将使用默认的计划程序。

类型`_Call_method`是具有签名的伪函数`void (T const &)`调用此`call`消息块来处理消息。

类型`filter_method`是具有签名的伪函数`bool (T const &)`调用此`call`消息块，以确定它是否应接受提供的消息。

##  <a name="dtor"></a> ~call

销毁`call`消息块。

```
~call();
```

##  <a name="process_input_messages"></a> process_input_messages

输入消息执行调用的函数。

```
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>参数

*_PMessage*<br/>
指向要处理的消息的指针。

##  <a name="process_message"></a> process_message

处理已接受此消息`call`消息块。

```
virtual void process_message(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>参数

*_PMessage*<br/>
指向要处理的消息的指针。

##  <a name="propagate_message"></a> propagate_message

以异步方式从将消息传递`ISource`到此块`call`消息块。 由调用`propagate`方法，调用由源块时。

```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>参数

*_PMessage*<br/>
指向 `message` 对象的指针。

*_PSource*<br/>
指向源块提供消息的指针。

### <a name="return-value"></a>返回值

一个[message_status](concurrency-namespace-enums.md)的目标决定如何处理该消息指示。

##  <a name="send_message"></a> send_message

以同步方式从将消息传递`ISource`到此块`call`消息块。 由调用`send`方法，调用由源块时。

```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>参数

*_PMessage*<br/>
指向 `message` 对象的指针。

*_PSource*<br/>
指向源块提供消息的指针。

### <a name="return-value"></a>返回值

一个[message_status](concurrency-namespace-enums.md)的目标决定如何处理该消息指示。

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

重写 `supports_anonymous_source` 方法，以指示该块可以接受由未链接的源为其提供的消息。

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>返回值

**true**因为该块没有推迟提供的消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[transformer 类](transformer-class.md)
