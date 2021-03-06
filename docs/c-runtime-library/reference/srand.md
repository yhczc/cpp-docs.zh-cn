---
title: srand
ms.date: 1/02/2018
apiname:
- srand
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- srand
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.openlocfilehash: 6545d4eba6c17fd55bb2b8cf23fb0319d1c96bee
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57209816"
---
# <a name="srand"></a>srand

设置使用的伪随机数字生成器的起始种子值**rand**函数。

## <a name="syntax"></a>语法

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>参数

*seed*<br/>
伪随机数生成的种子

## <a name="remarks"></a>备注

**Srand**函数设置用于在当前线程中生成的伪随机整数序列的起始点。 若要重新初始化生成器来创建相同的结果序列，请调用**srand**函数，并使用同一个*种子*再次参数。 任何其他值*种子*将生成器设置为伪随机序列中的不同起始点。 **rand**检索生成的伪随机数。 调用**rand**对任何调用之前**srand**生成相同的序列与调用**srand**与*种子*作为 1 传递。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

请参阅 [rand](rand.md) 的示例。

## <a name="see-also"></a>请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
