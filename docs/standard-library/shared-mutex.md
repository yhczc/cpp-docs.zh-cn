---
title: '&lt;shared_mutex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <shared_mutex>
- shared_mutex/std::swap
- shared_mutex/std::shared_lock
- shared_mutex/std::shared_lock::shared_lock
- shared_mutex/std::shared_lock::operator=
- shared_mutex/std::shared_lock::operator =
- shared_mutex/std::shared_lock::lock
- shared_mutex/std::shared_lock::try_lock
- shared_mutex/std::shared_lock::try_lock_for
- shared_mutex/std::shared_lock::try_lock_until
- shared_mutex/std::shared_lock::unlock
- shared_mutex/std::shared_lock::swap
- shared_mutex/std::shared_lock::release
- shared_mutex/std::shared_lock::owns_lock
- shared_mutex/std::shared_lock::operator bool
- shared_mutex/std::shared_lock::mutex
- shared_mutex/std::shared_mutex
- shared_mutex/std::shared_mutex::native_handle_type
- shared_mutex/std::shared_mutex::shared_mutex
- shared_mutex/std::shared_mutex::operator=
- shared_mutex/std::shared_mutex::operator =
- shared_mutex/std::shared_mutex::lock
- shared_mutex/std::shared_mutex::try_lock
- shared_mutex/std::shared_mutex::unlock
- shared_mutex/std::shared_mutex::lock_shared
- shared_mutex/std::shared_mutex::try_lock_shared
- shared_mutex/std::shared_mutex::unlock_shared
- shared_mutex/std::shared_mutex::native_handle
- shared_mutex/std::shared_timed_mutex
- shared_mutex/std::shared_timed_mutex::shared_timed_mutex
- shared_mutex/std::shared_timed_mutex::operator=
- shared_mutex/std::shared_timed_mutex::operator =
- shared_mutex/std::shared_timed_mutex::lock
- shared_mutex/std::shared_timed_mutex::try_lock
- shared_mutex/std::shared_timed_mutex::try_lock_for
- shared_mutex/std::shared_timed_mutex::try_lock_until
- shared_mutex/std::shared_timed_mutex::unlock
- shared_mutex/std::shared_timed_mutex::lock_shared
- shared_mutex/std::shared_timed_mutex::try_lock_shared
- shared_mutex/std::shared_timed_mutex::try_lock_shared_for
- shared_mutex/std::shared_timed_mutex::try_lock_shared_until
- shared_mutex/std::shared_timed_mutex::unlock_shared
ms.assetid: 0b37a97d-ee5d-4050-b29f-09db9f76beb3
ms.openlocfilehash: 9823b01048eece557a4d29904f223841b626bc9a
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751812"
---
# <a name="ltsharedmutex"></a>&lt;shared_mutex>

&lt;Shared_mutex > 标头提供同步基元，多个线程可以访问的共享数据的保护。 除由 mutex 类提供的独占访问控制之外，共享 mutex 类还允许共享多个线程的非独占访问所有权。 共享 mutex 可用于控制可通过多个线程读取的资源且不会引发争用条件问题，但必须以独占方式通过单个线程写入。

标头&lt;shared_mutex > 定义类`shared_mutex`并`shared_timed_mutex`，此模板类`shared_lock`，和模板函数`swap`共享互斥体的支持。

|类|描述|
|-------------|-----------------|
|[shared_mutex 类](../standard-library/shared-mutex.md#class_shared_mutex)|一种共享 mutex 类型，可由单个代理以独占方式锁定，或由多个代理以非独占方式共享。|
|[shared_timed_mutex 类](../standard-library/shared-mutex.md#class_shared_timed_mutex)|一种共享的定时 mutex 类型，可由单个代理以独占方式锁定，或由多个代理以非独占方式共享。|
|[shared_lock 类](../standard-library/shared-mutex.md#class_shared_lock)|一种模板类，包装共享 mutex 以支持定时锁定操作，由多个代理以非独占方式共享。|

|函数|描述|
|---------------|-----------------|
|[swap](../standard-library/shared-mutex.md#function_swap)|交换由函数参数引用的共享 mutex 对象的内容。|

## <a name="syntax"></a>语法

```cpp
namespace std {
    class shared_mutex;
    class shared_timed_mutex;
    template <class Mutex>
class shared_lock;
    template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
}
```

## <a name="remarks"></a>备注

类 `shared_mutex` 的实例是一个共享 mutex 类型，该类型可控制作用域内 mutex 的共享所有权。 共享 mutex 类型满足作为 mutex 类型和成员的所有要求，以支持共享的非独占所有权。

共享 mutex 类型支持其他其他方法 `lock_shared`、`unlock_shared` 和 `try_lock_shared`：

- `lock_shared` 方法阻止调用线程，直到线程获取 mutex 共享所有权。

- `unlock_shared` 方法通过调用线程释放 mutex 共享所有权。

- `try_lock_shared` 方法尝试在不阻止的情况下获取 mutex 共享所有权。 转换为其返回类型是**bool**是**true**如果此方法获取所有权，否则**false**。

类 `shared_timed_mutex` 是 *共享定时 mutex 类型*，满足共享 mutex 类型的两个要求并且是定时 mutex 类型。

共享 mutex 类型支持其他方法 `try_lock_shared_for` 和 `try_lock_shared_until`：

- `try_lock_shared_for` 方法尝试获取 mutex 共享所有权，直到超过由参数指定的持续时间。 如果持续时间不为正，则该方法等效于 `try_lock_shared`。 除非已获得共享所有权，否则在指定持续时间内不会返回该方法。 它的返回值是 **，则返回 true**如果此方法获取所有权，否则**false**。

- `try_lock_shared_until` 方法尝试获取 mutex 共享所有权，直到超过指定的绝对持续时间。 如果指定的时间已过，该方法等效于 `try_lock_shared`。 除非已获得共享所有权，否则不会在指定时间之前返回该方法。 它的返回值是 **，则返回 true**如果此方法获取所有权，否则**false**。

`shared_lock` 模板类扩展对定时锁定和所有权转移给共享 mutex 的支持。 Mutex 所有权可以在构造之时或之后获得，也可转移到另一个 `shared_lock` 对象。 可移动 `shared_lock` 类型的对象，但不能复制。

> [!WARNING]
> 从 Visual Studio 2015 开始，c + + 标准库同步类型基于 Windows 同步基元和不再使用 ConcRT （除非目标平台是 Windows XP）。 中定义的类型&lt;shared_mutex > 不能与任何 ConcRT 类型或函数。

## <a name="classes"></a>类

###  <a name="class_shared_mutex"></a>shared_mutex 类

类 `shared_mutex` 实现非递归 mutex 和共享所有权语义。

```cpp
class shared_mutex {
public:
   shared_mutex();
   ~shared_mutex();
   shared_mutex(const shared_mutex&) = delete;
   shared_mutex& operator=(const shared_mutex&) = delete;
   // Exclusive ownership
   void lock();
   // blocking
   bool try_lock();
   void unlock();
   // Shared ownership
   void lock_shared();
   // blocking
   bool try_lock_shared();
   void unlock_shared();
   // Getters
   typedef void** native_handle_type; // implementation defined
   native_handle_type native_handle();
   };
```

###  <a name="class_shared_timed_mutex"></a>shared_timed_mutex 类

类 `shared_timed_mutex` 实现非递归 mutex 和满足定时 mutex 类型要求的共享所有权语义。

```cpp
class shared_timed_mutex {
public:
   shared_timed_mutex();
   ~shared_timed_mutex();
   shared_timed_mutex(const shared_timed_mutex&) = delete;
   shared_timed_mutex& operator=(const shared_timed_mutex&) = delete;
   // Exclusive ownership
   void lock();
   // blocking
   bool try_lock();
   template <class Rep, class Period>
   bool try_lock_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock();
   // Shared ownership
   void lock_shared();
   // blocking
   bool try_lock_shared();
   template <class Rep, class Period>
   bool try_lock_shared_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_shared_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock_shared();
   };
```

###  <a name="&lt;shared"></a>shared_lock 类

模板类 `shared_lock` 控制作用域中共享 mutex 对象的共享所有权。 模板参数必须是共享 mutex 类型。

```cpp
class shared_lock {
public:
   typedef Mutex mutex_type;
   shared_lock() noexcept;
   explicit shared_lock(mutex_type& m);
   // blocking
   shared_lock(mutex_type& m, defer_lock_t) noexcept;
   shared_lock(mutex_type& m, try_to_lock_t);
   shared_lock(mutex_type& m, adopt_lock_t);
   template <class Clock, class Duration>
   shared_lock(mutex_type& m,
   const chrono::time_point<Clock, Duration>& abs_time);
   template <class Rep, class Period>
   shared_lock(mutex_type& m,
   const chrono::duration<Rep, Period>& rel_time);
   ~shared_lock();
   shared_lock(shared_lock const&) = delete;
   shared_lock& operator=(shared_lock const&) = delete;
   shared_lock(shared_lock&& u) noexcept;
   shared_lock& operator=(shared_lock&& u) noexcept;
   void lock();
   // blocking
   bool try_lock();
   template <class Rep, class Period>
   bool try_lock_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock();
   // Setters
   void swap(shared_lock& u) noexcept;
   mutex_type* release() noexcept;
   // Getters
   bool owns_lock() const noexcept;
   explicit operator bool () const noexcept;
   mutex_type* mutex() const noexcept;
private:
   mutex_type* pm; // exposition only
   bool owns; // exposition only
   };
```

## <a name="functions"></a>函数

###  <a name="function_swap"></a> swap

交换 `shared_lock` 对象。

```cpp
template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
```

交换两个 `shared_lock` 对象的内容。 实际效果与 `x.swap(y)` 相同。

## <a name="requirements"></a>要求

**标头：**&lt;shared_mutex>

**命名空间：** std

## <a name="see-also"></a>请参阅

[头文件引用](../standard-library/cpp-standard-library-header-files.md)<br/>
[&lt;mutex>](../standard-library/mutex.md)
