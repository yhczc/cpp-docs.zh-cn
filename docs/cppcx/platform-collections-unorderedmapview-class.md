---
title: Platform::Collections::UnorderedMapView 类
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
ms.openlocfilehash: ebda6f179c365aaa009eb45425a36058105def10
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743444"
---
# <a name="platformcollectionsunorderedmapview-class"></a>Platform::Collections::UnorderedMapView 类

将一个只读视图表示为一个 映射，这是键值对的集合。

## <a name="syntax"></a>语法

```cpp
template <
   typename K,
   typename V,
   typename C = ::std::equal_to<K>>
ref class UnorderedMapView sealed;
```

#### <a name="parameters"></a>参数

*K*<br/>
键值对中键的类型。

*V*<br/>
键值对中值的类型。

*C*<br/>
提供可比较两个键值是否相等的函数对象的类型。 默认情况下[std:: equal_to\<K >](../standard-library/equal-to-struct.md)

### <a name="remarks"></a>备注

UnorderedMapView 是具体的 c + + 实现[Windows::Foundation::Collections::IMapView\<K，V >](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_)跨应用程序二进制接口 (ABI) 传递的接口。 有关更多信息，请参见 [集合 (C++/CX)](../cppcx/collections-c-cx.md)。

### <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[UnorderedMapView::UnorderedMapView](#ctor)|初始化 UnorderedMapView 类的新实例。|

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[UnorderedMapView::First](#first)|返回初始化为映射视图中第一个元素的迭代器。|
|[UnorderedMapView::HasKey](#haskey)|确定当前 UnorderedMapView 中是否包含指定键。|
|[UnorderedMapView::Lookup](#lookup)|检索当前 UnorderedMapView 对象中指定键处的元素。|
|[UnorderedMapView::Size](#size)|返回当前 UnorderedMapView 对象中的元素数目。|
|[UnorderedMapView::Split](#split)|将原始 UnorderedMapView 对象拆分成两个 UnorderedMapView 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`UnorderedMapView`

### <a name="requirements"></a>要求

**标头：** collection.h

**命名空间：** Platform::Collections

## <a name="first"></a>  UnorderedMapView::First 方法

返回一个迭代器，指定第一个[Windows::Foundation::Collections::IKeyValuePair\<K，V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_)无序映射中的元素。

### <a name="syntax"></a>语法

```cpp
virtual Windows::Foundation::Collections::IIterator<
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
    First();
```

### <a name="return-value"></a>返回值

指定映射视图中第一个元素的迭代器。

### <a name="remarks"></a>备注

保留 first （） 返回的迭代器的简便方法是将返回值分配为使用声明的变量**自动**类型推导关键字。 例如 `auto x = myMapView->First();`。

## <a name="haskey"></a>  UnorderedMapView::HasKey 方法

确定当前 UnorderedMap 中是否包含指定键。

### <a name="syntax"></a>语法

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>参数

*key*<br/>
用于定位元素的键。 类型`key`是 typename *K*。

### <a name="return-value"></a>返回值

**true**如果该键; 否则为**false**。

## <a name="lookup"></a>  UnorderedMapView::Lookup 方法

检索与类型 K 的指定键关联的类型 V 的值。

### <a name="syntax"></a>语法

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>参数

*key*<br/>
用于定位 UnorderedMapView 中的元素的键。 类型`key`是 typename *K*。

### <a name="return-value"></a>返回值

与 `key` 配对的值。 返回值的类型是 typename *V*。

## <a name="size"></a>  UnorderedMapView::Size 方法

返回的数[Windows::Foundation::Collections::IKeyValuePair\<K，V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) UnorderedMapView 中的元素。

### <a name="syntax"></a>语法

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>返回值

UnorderedMapView 中的元素数目。

## <a name="split"></a>  UnorderedMapView::Split 方法

将当前 UnorderedMapView 对象分成两个 UnorderedMapView 对象。 此方法为非操作性的。

### <a name="syntax"></a>语法

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * secondPartition);
```

### <a name="parameters"></a>参数

*firstPartition*<br/>
原始 UnorderedMapView 对象的第一部分。

*secondPartition*<br/>
原始 UnorderedMapView 对象的第二部分。

### <a name="remarks"></a>备注

此方法为非操作性的，它不执行任何操作。

## <a name="ctor"></a>  UnorderedMapView::UnorderedMapView 构造函数

初始化 UnorderedMapView 类的新实例。

### <a name="syntax"></a>语法

```cpp
UnorderedMapView();
explicit UnorderedMapView(size_t n);
UnorderedMapView(size_t n, const H& h);
UnorderedMapView(size_t n, const H& h, const P& p);

explicit UnorderedMapView(
    const std::unordered_map<K, V, H, P>& m);
explicit UnorderedMapView(
    std::unordered_map<K, V, H, P>&& m);

template <typename InIt> UnorderedMapView(InIt first, InIt last );
template <typename InIt> UnorderedMapView(InIt first, InIt last, size_t n );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p );

UnorderedMapView(std::initializer_list<std::pair<const K, V>);

UnorderedMapView(std::initializer_list< std::pair<const K, V>> il, size_t n

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h);

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p );
```

### <a name="parameters"></a>参数

*n*<br/>
要预分配空间的元素数目。

*InIt*<br/>
UnorderedMapView 的类型名称。

*H*<br/>
可以为键生成哈希值的函数对象。 默认情况下[std:: hash\<K >](../standard-library/hash-class.md)类型的`std::hash`支持。

*P*<br/>
提供可比较两个键以确定其相等性的函数对象的类型。 默认情况下[std:: equal_to\<K >](../standard-library/equal-to-struct.md)。

*m*<br/>
引用或[Lvalues 和 Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)到[std:: unordered_map](../standard-library/unordered-map-class.md)用于初始化 UnorderedMapView。

*first*<br/>
用于初始化 UnorderedMapView 的一系列元素中的第一个元素的输入迭代器。

*last*<br/>
用于初始化 UnorderedMapView 的一系列元素之后的第一个元素的输入迭代器。

## <a name="see-also"></a>请参阅

[Platform::Collections 命名空间](../cppcx/platform-collections-namespace.md)<br/>
[Windows::Foundation::IMapView](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_)
