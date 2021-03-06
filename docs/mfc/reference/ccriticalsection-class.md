---
title: CCriticalSection 类
ms.date: 11/04/2016
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
ms.openlocfilehash: 2c89647afc8a9a8c6564d25afe20d48818a643f2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291036"
---
# <a name="ccriticalsection-class"></a>CCriticalSection 类

表示一个"临界区"-每次访问资源或代码段的允许一个线程的同步对象。

## <a name="syntax"></a>语法

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[CCriticalSection::CCriticalSection](#ccriticalsection)|构造 `CCriticalSection` 对象。|

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[CCriticalSection::Lock](#lock)|使用可以访问到`CCriticalSection`对象。|
|[CCriticalSection::Unlock](#unlock)|释放 `CCriticalSection` 对象。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|检索指向内部 CRITICAL_SECTION 对象的指针。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CCriticalSection::m_sect](#m_sect)|CRITICAL_SECTION 对象。|

## <a name="remarks"></a>备注

可以允许一次只有一个线程来修改数据或某个其他受控的资源时，关键部分很有用。 例如，将节点添加到链接的列表是一个过程，应仅允许一个线程通过一次。 通过使用`CCriticalSection`对象以控制链接的列表中，仅一次一个线程可以访问列表。

> [!NOTE]
>  功能`CCriticalSection`类提供的实际 Win32 CRITICAL_SECTION 对象。

临界区使用而不是互斥体 (请参阅[CMutex](../../mfc/reference/cmutex-class.md)) 时速度很关键，该资源不会使用跨进程边界。

有两种方法来使用`CCriticalSection`对象： 独立和嵌入式类中。

- 要使用独立的独立方法`CCriticalSection`对象，构造`CCriticalSection`对象时需要它。 成功返回后从构造函数，显式锁定的对象通过调用[锁](#lock)。 调用[解锁](#unlock)完成后访问的关键部分。 此方法，更清晰的某个人可以读取源代码，同时是更容易出现错误必须记得要锁定和解锁之前和之后访问的关键部分。

   更好的方法是使用[CSingleLock](../../mfc/reference/csinglelock-class.md)类。 它还具有`Lock`和`Unlock`方法，但你无需担心如何取消锁定资源，如果发生异常。

- 嵌入方法还可以共享一个类，通过多个线程通过添加`CCriticalSection`-类型的类和锁定时所需的数据成员的数据成员。

有关使用的详细信息`CCriticalSection`对象，请参阅文章[多线程处理：如何使用同步类](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>要求

**标头：** afxmt.h

##  <a name="ccriticalsection"></a>  CCriticalSection::CCriticalSection

构造 `CCriticalSection` 对象。

```
CCriticalSection();
```

### <a name="remarks"></a>备注

访问或释放`CCriticalSection`对象，请创建[CSingleLock](../../mfc/reference/csinglelock-class.md)对象，并调用其[锁](../../mfc/reference/csinglelock-class.md#lock)并[解锁](../../mfc/reference/csinglelock-class.md#unlock)成员函数。 如果`CCriticalSection`正在独立使用对象，调用其[解锁](#unlock)成员函数以将其释放。

如果无法分配所需的系统内存，内存异常构造函数 (类型的[CMemoryException](../../mfc/reference/cmemoryexception-class.md)) 则会自动引发。

### <a name="example"></a>示例

  有关示例，请参阅[CCriticalSection::Lock](#lock)。

##  <a name="lock"></a>  CCriticalSection::Lock

调用此成员函数来访问关键部分对象。

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>参数

*dwTimeout*<br/>
`Lock` 将忽略此参数值。

### <a name="return-value"></a>返回值

如果函数成功，则非零值否则为 0。

### <a name="remarks"></a>备注

`Lock` 是关键部分对象处于终止状态之前不会返回一个阻塞调用 （可用时）。

如果超时的等待是必需的则可以使用[CMutex](../../mfc/reference/cmutex-class.md)对象而不是`CCriticalSection`对象。

如果`Lock`无法分配必要的系统内存，内存异常 (类型的[CMemoryException](../../mfc/reference/cmemoryexception-class.md)) 则会自动引发。

### <a name="example"></a>示例

此示例演示嵌套的关键节方法控制对共享资源的访问 (静态`_strShared`对象) 使用共享`CCriticalSection`对象。 `SomeMethod`函数演示了以安全方式更新共享的资源。

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

##  <a name="m_sect"></a>  CCriticalSection::m_sect

包含一个关键部分对象，由所有`CCriticalSection`方法。

```
CRITICAL_SECTION m_sect;
```

##  <a name="operator_critical_section_star"></a>  CCriticalSection::operator CRITICAL_SECTION *

检索 CRITICAL_SECTION 对象。

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>备注

调用此函数可检索指向内部 CRITICAL_SECTION 对象的指针。

##  <a name="unlock"></a>  CCriticalSection::Unlock

版本`CCriticalSection`对象以供另一个线程。

```
BOOL Unlock();
```

### <a name="return-value"></a>返回值

如果非零`CCriticalSection`对象已由线程拥有和发布已成功; 否则为 0。

### <a name="remarks"></a>备注

如果`CCriticalSection`正在使用独立的`Unlock`必须完成的关键部分由控制的资源的使用之后立即调用。 如果[CSingleLock](../../mfc/reference/csinglelock-class.md)使用对象，则`CCriticalSection::Unlock`锁对象将调用`Unlock`成员函数。

### <a name="example"></a>示例

  有关示例，请参阅[CCriticalSection::Lock](#lock)。

## <a name="see-also"></a>请参阅

[CSyncObject 类](../../mfc/reference/csyncobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CMutex 类](../../mfc/reference/cmutex-class.md)
