---
title: ___lc_collate_cp_func
ms.date: 11/04/2016
apiname:
- ___lc_collate_cp_func
apilocation:
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- ___lc_collate_cp_func
helpviewer_keywords:
- ___lc_collate_cp_func
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
ms.openlocfilehash: fac8b7ba2e9568dd53509e5cccbb96a6b2f1df8d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738878"
---
# <a name="lccollatecpfunc"></a>___lc_collate_cp_func

内部 CRT 函数。 检索线程的当前排序规则代码页。

## <a name="syntax"></a>语法

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>返回值

线程的当前排序规则代码页。

## <a name="remarks"></a>备注

`___lc_collate_cp_func` 是一个内部 CRT 函数，其他 CRT 函数可将其用于从 CRT 数据的线程本地存储中获取当前排序规则代码页。 也可通过使用 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) 函数提供此信息。

内部 CRT 函数特定于实现且会根据每个发行版本发生更改。 不建议在代码中使用它们。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|`___lc_collate_cp_func`|crt\src\setlocal.h|

## <a name="see-also"></a>请参阅

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
