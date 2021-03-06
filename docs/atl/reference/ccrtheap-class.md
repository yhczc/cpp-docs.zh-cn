---
title: CCRTHeap 类
ms.date: 11/04/2016
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
ms.openlocfilehash: 3c5030b9cfbfd636a783d27bcc8f9469f8348acb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276268"
---
# <a name="ccrtheap-class"></a>CCRTHeap 类

此类实现[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)使用 CRT 堆函数。

## <a name="syntax"></a>语法

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[CCRTHeap::Allocate](#allocate)|调用此方法来分配内存块。|
|[CCRTHeap::Free](#free)|调用此方法来释放此内存管理器分配的内存块。|
|[CCRTHeap::GetSize](#getsize)|调用此方法以获取此内存管理器分配的内存块的分配的大小。|
|[CCRTHeap::Reallocate](#reallocate)|调用此方法以重新分配由该内存管理器分配的内存。|

## <a name="remarks"></a>备注

`CCRTHeap` 实现内存分配函数使用 CRT 堆函数，包括[malloc](../../c-runtime-library/reference/malloc.md)，[免费](../../c-runtime-library/reference/free.md)， [realloc](../../c-runtime-library/reference/realloc.md)，以及[_msize](../../c-runtime-library/reference/msize.md)。

## <a name="example"></a>示例

有关示例，请参阅[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>要求

**标头：** atlmem.h

##  <a name="allocate"></a>  Ccrtheap:: Allocate

调用此方法来分配内存块。

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>参数

*nBytes*<br/>
新内存块中请求的字节数。

### <a name="return-value"></a>返回值

将指针返回到新分配内存块的起始位置。

### <a name="remarks"></a>备注

调用[ccrtheap:: Free](#free)或[ccrtheap:: Reallocate](#reallocate)来释放由此方法分配的内存。

使用实现[malloc](../../c-runtime-library/reference/malloc.md)。

##  <a name="free"></a>  Ccrtheap:: Free

调用此方法来释放此内存管理器分配的内存块。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>参数

*p*<br/>
指向此内存管理器以前分配的内存的指针。 NULL 是一个有效的值，不执行任何操作。

### <a name="remarks"></a>备注

使用实现[免费](../../c-runtime-library/reference/free.md)。

##  <a name="getsize"></a>  CCRTHeap::GetSize

调用此方法以获取此内存管理器分配的内存块的分配的大小。

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>参数

*p*<br/>
指向此内存管理器以前分配的内存的指针。

### <a name="return-value"></a>返回值

以字节为单位返回已分配的内存块的大小。

### <a name="remarks"></a>备注

使用实现[_msize](../../c-runtime-library/reference/msize.md)。

##  <a name="reallocate"></a>  Ccrtheap:: Allocate

调用此方法以重新分配由该内存管理器分配的内存。

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>参数

*p*<br/>
指向此内存管理器以前分配的内存的指针。

*nBytes*<br/>
新内存块中请求的字节数。

### <a name="return-value"></a>返回值

将指针返回到新分配内存块的起始位置。

### <a name="remarks"></a>备注

调用[ccrtheap:: Free](#free)来释放由此方法分配的内存。 使用实现[realloc](../../c-runtime-library/reference/realloc.md)。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)<br/>
[CComHeap 类](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap 类](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap 类](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap 类](../../atl/reference/cglobalheap-class.md)<br/>
[IAtlMemMgr 类](../../atl/reference/iatlmemmgr-class.md)
