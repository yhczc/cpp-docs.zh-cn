---
title: 按类别列出的关键 WRL API
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
ms.openlocfilehash: fd4bebf9c823079c3bdb4c4182bf3f30cdf105a7
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335751"
---
# <a name="key-wrl-apis-by-category"></a>按类别列出的关键 WRL API

下表列出主类、 结构、 函数和 Windows 运行时 c + + 模板库中的宏。 省略中帮助程序命名空间和类的构造。 这些列表提供了 API 文档，从而按命名空间排列。

## <a name="classes"></a>类

|标题|描述|
|-----------|-----------------|
|[ActivationFactory 类](activationfactory-class.md)|启用 Windows 运行时将激活的一个或多个类。|
|[AsyncBase 类](asyncbase-class.md)|实现 Windows 运行时异步状态机。|
|[ClassFactory 类](classfactory-class.md)|实现 `IClassFactory` 接口的基本功能。|
|[ComPtr 类](comptr-class.md)|创建表示模板参数指定的接口的 *智能指针* 类型。 ComPtr 会自动维护基础接口指针的引用计数，并在引用计数变为零时释放接口。|
|[Event 类（Windows 运行时 C++ 模板库）](event-class-wrl.md)|表示一个事件。|
|[EventSource 类](eventsource-class.md)|表示一个事件。 `EventSource` 成员函数将添加、删除和调用事件处理程序。|
|[FtmBase 类](ftmbase-class.md)|表示自由线程封送拆收器对象。|
|[HandleT 类](handlet-class.md)|表示对象的句柄。|
|[HString 类](hstring-class.md)|为处理 HSTRING 句柄提供支持。|
|[HStringReference 类](hstringreference-class.md)|表示从现有字符串创建的 HSTRING。|
|[Module 类](module-class.md)|表示相关对象的集合。|
|[Module::GenericReleaseNotifier 类](module-genericreleasenotifier-class.md)|在释放当前模块中的最后一个对象时调用事件处理程序。 事件处理程序由 lambda、functor 或 pointer-to-function 指定。|
|[Module::MethodReleaseNotifier 类](module-methodreleasenotifier-class.md)|在释放当前模块中的最后一个对象时调用事件处理程序。 对象并将其指针到方法成员由指定的事件处理程序。|
|[Module::ReleaseNotifier 类](module-releasenotifier-class.md)|在释放模块中的最后一个对象时调用事件处理程序。|
|[RoInitializeWrapper 类](roinitializewrapper-class.md)|初始化 Windows 运行时。|
|[RuntimeClass 类](runtimeclass-class.md)|表示继承指定数量的接口的实例化类，并提供指定 Windows 运行时、经典 COM 和弱引用支持。|
|[SimpleActivationFactory 类](simpleactivationfactory-class.md)|提供创建 Windows 运行时或经典 COM 基类的基础机制。|
|[SimpleClassFactory 类](simpleclassfactory-class.md)|提供创建基类的基本机制。|
|[WeakRef 类](weakref-class.md)|表示只能由 Windows 运行时而不是经典 COM 使用的 *弱引用* 。 弱引用表示可能可访问或可能不可访问的对象。|

## <a name="structures"></a>结构

|标题|描述|
|-----------|-----------------|
|[ChainInterfaces 结构](chaininterfaces-structure.md)|指定可应用于一组接口 ID 的验证和初始化函数。|
|[CloakedIid 结构](cloakediid-structure.md)|指示对`RuntimeClass`，`Implements`和`ChainInterfaces`： 指定的接口是无法访问 IID 列表中的模板。|
|[Implements 结构](implements-structure.md)|实现`QueryInterface`和`GetIid`指定接口。|
|[MixIn 结构](mixin-structure.md)|确保运行时类先后派生自 Windows 运行时接口（如果有）和经典 COM 接口。|

## <a name="functions"></a>函数

|标题|描述|
|-----------|-----------------|
|[ActivateInstance 函数](activateinstance-function.md)|注册并检索实例的指定类型定义中指定的类 id。|
|[AsWeak 函数](asweak-function.md)|检索对指定实例的弱引用。|
|[回调函数](callback-function-wrl.md)|创建一个对象，该对象的成员函数是一个回调方法。|
|[CreateActivationFactory 函数](createactivationfactory-function.md)|创建为可由 Windows 运行时激活的指定类生成实例的工厂。|
|[CreateClassFactory 函数](createclassfactory-function.md)|创建为指定类生成实例的工厂。|
|[GetActivationFactory 函数](getactivationfactory-function.md)|检索指定模板参数的类型的激活工厂。|
|[Make 函数](make-function.md)|初始化指定的 Windows 运行时类。|

## <a name="macros"></a>宏

|标题|描述|
|-----------|-----------------|
|[ActivatableClass 宏](activatableclass-macros.md)|填充内部缓存，其中包含一个工厂，它可以创建指定类的实例。|
|[InspectableClass 宏](inspectableclass-macro.md)|设置运行时类名称和信任级别。|

## <a name="see-also"></a>请参阅

[Windows 运行时 C++ 模板库 (WRL)](windows-runtime-cpp-template-library-wrl.md)