---
title: '&lt;paramref > （c + + 文档注释）'
ms.date: 11/04/2016
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- paramref C++ XML tag
- <paramref> C++ XML tag
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
ms.openlocfilehash: cee35ddb5fd5cd811e45f0aa49e94dd9c4b8b180
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824814"
---
# <a name="ltparamrefgt"></a>&lt;paramref&gt;

\<paramref> 标记提供一种指示某字为参数的方法。 可处理 .xml 文件，以某种不同的方式设置此参数格式。

## <a name="syntax"></a>语法

```
<paramref name="name"/>
```

#### <a name="parameters"></a>参数

*name*<br/>
要引用的参数的名称。  将名称括在单引号或双引号中。  如果编译器没有找到 `name`，它会发出警告。

## <a name="remarks"></a>备注

使用 [/doc](doc-process-documentation-comments-c-cpp.md) 进行编译可以将文档注释处理到文件中。

## <a name="example"></a>示例

```
// xml_paramref_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_paramref_tag.dll
/// Text for class MyClass.
public ref class MyClass {
   /// <summary>MyMethod is a method in the MyClass class.
   /// The <paramref name="Int1"/> parameter takes a number.
   /// </summary>
   void MyMethod(int Int1) {}
};
```

## <a name="see-also"></a>请参阅

[XML 文档](xml-documentation-visual-cpp.md)
