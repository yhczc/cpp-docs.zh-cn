---
title: short_vector_traits 结构
ms.date: 11/04/2016
f1_keywords:
- short_vector_traits
- AMP_SHORT_VECTORS/short_vector_traits
- AMP_SHORT_VECTORS/Concurrency::graphics::short_vector_traits::short_vector_traits
- AMP_SHORT_VECTORS/Concurrency::graphics::short_vector_traits::size Constant
ms.assetid: cd9492da-9e02-4a6e-9d50-b61252cdb460
ms.openlocfilehash: c407c42e5c6a7035e911218ecb41c2da62967787
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289606"
---
# <a name="shortvectortraits-structure"></a>short_vector_traits 结构

通过 short_vector_traits 可检索基础矢量长度和短的矢量类型或标量类型的标量类型

## <a name="syntax"></a>语法

```
template<
    typename T
>
struct short_vector_traits;
template<>
struct short_vector_traits<unsigned int>;
template<>
struct short_vector_traits<uint_2>;
template<>
struct short_vector_traits<uint_3>;
template<>
struct short_vector_traits<uint_4>;
template<>
struct short_vector_traits<int>;
template<>
struct short_vector_traits<int_2>;
template<>
struct short_vector_traits<int_3>;
template<>
struct short_vector_traits<int_4>;
template<>
struct short_vector_traits<float>;
template<>
struct short_vector_traits<float_2>;
template<>
struct short_vector_traits<float_3>;
template<>
struct short_vector_traits<float_4>;
template<>
struct short_vector_traits<unorm>;
template<>
struct short_vector_traits<unorm_2>;
template<>
struct short_vector_traits<unorm_3>;
template<>
struct short_vector_traits<unorm_4>;
template<>
struct short_vector_traits<norm>;
template<>
struct short_vector_traits<norm_2>;
template<>
struct short_vector_traits<norm_3>;
template<>
struct short_vector_traits<norm_4>;
template<>
struct short_vector_traits<double>;
template<>
struct short_vector_traits<double_2>;
template<>
struct short_vector_traits<double_3>;
template<>
struct short_vector_traits<double_4>;
```

#### <a name="parameters"></a>参数

`T`

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[short_vector_traits:: short_vector_traits 构造函数](#ctor)||

### <a name="public-constants"></a>公共常量

|name|描述|
|----------|-----------------|
|[short_vector_traits:: size 常量](#size)||

## <a name="inheritance-hierarchy"></a>继承层次结构

`short_vector_traits`

## <a name="requirements"></a>要求

**标头：** amp_short_vectors.h

**命名空间：** Concurrency:: graphics

##  <a name="ctor"></a>  short_vector_traits:: short_vector_traits 构造函数

```
short_vector_traits();
```

##  <a name="size"></a>  short_vector_traits:: size 常量

```
static int const size = 1;
```

## <a name="see-also"></a>请参阅

[Concurrency::graphics 命名空间](concurrency-graphics-namespace.md)
