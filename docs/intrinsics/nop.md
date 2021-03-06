---
title: __nop
ms.date: 11/04/2016
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: b0033b0e3a62a16c2856b0e25daeebdb5df0c81f
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220382"
---
# <a name="nop"></a>__nop

**Microsoft 专用**

生成特定于平台的机器代码，会执行任何操作。

## <a name="syntax"></a>语法

```
void __nop();
```

## <a name="requirements"></a>要求

|内部函数|体系结构|
|---------------|------------------|
|`__nop`|x86、 ARM、 x64、 ARM64|

**标头文件** \<intrin.h >

**结束 Microsoft 专用**

## <a name="remarks"></a>备注

`__nop` 函数等同于 `NOP` 计算机指令。 X86 和 x64 的详细信息，搜索文档中，"Intel 体系结构软件开发人员手册，卷 2:指令设置参考，"在[Intel Corporation](https://software.intel.com/articles/intel-sdm)站点。

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)<br/>
[__noop](../intrinsics/noop.md)
