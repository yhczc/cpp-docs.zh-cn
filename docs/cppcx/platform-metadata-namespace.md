---
title: Platform::Metadata 命名空间
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata
helpviewer_keywords:
- Platform::Metadata Namespace
ms.assetid: e3e114d8-a4b0-47f0-865a-9ce9d7212e86
ms.openlocfilehash: 9626b3a9d28d28fd52a0d2295af8fda8855cd90c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739454"
---
# <a name="platformmetadata-namespace"></a>Platform::Metadata 命名空间

此命名空间包含修改类型声明的特性。

## <a name="syntax"></a>语法

```cpp
namespace Platform {
   namespace Metadata {
}}
```

### <a name="members"></a>成员

虽然此命名空间供内部使用，但是浏览器可以显示此命名空间的以下成员。

|name|备注|
|----------|------------|
|特性|特性的基类。|
|[Platform::Metadata::DefaultMemberAttribute 特性](../cppcx/platform-metadata-defaultmemberattribute-attribute.md)|指示首选函数以在几个可能的重载函数中调用。|
|[Platform::Metadata::FlagsAttribute 特性](../cppcx/platform-metadata-flagsattribute-attribute.md)标记|声明枚举为位域的枚举。<br /><br /> 下面的示例演示如何将枚举应用于 `Flags` 特性。<br /><br /> `[Flags] enum class MyEnumeration { enumA = 1, enumB = 2, enumC = 3}`|
|[Platform::Metadata::RuntimeClassNameAttribute](../cppcx/platform-metadata-runtimeclassname.md)|确保私有 ref 类具有一个有效的运行时类名称。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`Platform`

### <a name="requirements"></a>要求

**元数据：** platform.winmd

**命名空间：** Platform::Metadata

## <a name="see-also"></a>请参阅

[平台 Namespace](platform-namespace-c-cx.md)
