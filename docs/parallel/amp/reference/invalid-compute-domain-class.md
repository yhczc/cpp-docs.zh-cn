---
title: invalid_compute_domain 类
ms.date: 11/04/2016
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
ms.openlocfilehash: 51fcd9e42bc4497131da5adb3dff72efb46537b3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296873"
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain 类

当运行时不能通过使用在指定的计算域启动内核时引发的异常[parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)调用站点。

## <a name="syntax"></a>语法

```
class invalid_compute_domain : public runtime_exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[invalid_compute_domain 构造函数](#ctor)|初始化 `invalid_compute_domain` 类的新实例。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`runtime_exception`

`invalid_compute_domain`

## <a name="requirements"></a>要求

**标头：** amprt.h

**命名空间：** 并发

## <a name="ctor"></a> invalid_compute_domain

初始化类的新实例。

## <a name="syntax"></a>语法

```
explicit invalid_compute_domain(
    const char * _Message ) throw();

invalid_compute_domain() throw();
```

### <a name="parameters"></a>参数

*_Message*<br/>
错误说明。

### <a name="return-value"></a>返回值

实例`invalid_compute_domain`类

## <a name="see-also"></a>请参阅

[并发命名空间 (C++ AMP)](concurrency-namespace-cpp-amp.md)
