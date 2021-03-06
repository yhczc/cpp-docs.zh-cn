---
title: 泛型函数 (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- functions [C++], generic
- generic methods
- generics [C++], functions
- methods [C++], generic
- generic functions
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
ms.openlocfilehash: 74e8cfe2b5b49a672b276400be75031626fd61c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432391"
---
# <a name="generic-functions-ccli"></a>泛型函数 (C++/CLI)

泛型函数是使用类型参数声明的函数。 调用时，使用实际类型而不是类型参数。

## <a name="all-platforms"></a>所有平台

### <a name="remarks"></a>备注

此功能不适用于所有平台。

## <a name="windows-runtime"></a>Windows 运行时

### <a name="remarks"></a>备注

在 Windows 运行时中不支持此功能。

### <a name="requirements"></a>要求

编译器选项：`/ZW`

## <a name="common-language-runtime"></a>公共语言运行时

泛型函数是使用类型参数声明的函数。 调用时，使用实际类型而不是类型参数。

### <a name="syntax"></a>语法

```cpp
[attributes] [modifiers]
return-type identifier<type-parameter identifier(s)>
[type-parameter-constraints clauses]

([formal-parameters])
{function-body}
```

### <a name="parameters"></a>参数

*特性*<br/>
（可选）声明性的其他信息。 有关属性和属性类的详细信息，请参阅属性。

*修饰符*<br/>
（可选）对于函数，如静态修饰符。  **虚拟**不允许，因为虚方法不是泛型。

*返回类型*<br/>
由方法返回的类型。 如果返回类型为 void，则需要没有返回值。

*identifier*<br/>
函数名称。

*类型参数标识符*<br/>
以逗号分隔的标识符列表。

*形参*<br/>
（可选）参数列表。

*类型形参约束子句*<br/>
这可能会用作类型参数的类型上指定的限制，接受窗体中指定[泛型类型参数的约束 (C + + CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)。

*函数体*<br/>
可能引用的类型参数标识符的方法的正文。

### <a name="remarks"></a>备注

泛型函数是使用泛型类型参数声明的函数。 它们可能是类或结构或独立函数中的方法。 单个泛型声明隐式声明一的系列区别只体现在不同的实际类型为泛型类型参数替换的函数。

不能使用泛型类型参数声明的类或结构的构造函数。

调用时，泛型类型参数替换为实际类型。 可以使用类似于模板函数调用语法的尖括号中显式指定的实际类型。 如果调用不带类型参数，编译器将尝试推导从函数调用中提供的参数的实际类型。 如果无法从使用的参数推导预期的类型参数，编译器将报告错误。

### <a name="requirements"></a>要求

编译器选项：`/clr`

### <a name="examples"></a>示例

下面的代码示例演示了泛型函数。

```cpp
// generics_generic_function_1.cpp
// compile with: /clr
generic <typename ItemType>
void G(int i) {}

ref struct A {
   generic <typename ItemType>
   void G(ItemType) {}

   generic <typename ItemType>
   static void H(int i) {}
};

int main() {
   A myObject;

   // generic function call
   myObject.G<int>(10);

   // generic function call with type parameters deduced
   myObject.G(10);

   // static generic function call
   A::H<int>(10);

   // global generic function call
   G<int>(10);
}
```

可以根据签名或实参数量、 上一个函数的类型参数的数目进行重载泛型函数。 此外，泛型函数可以具有相同名称的非泛型函数重载，只要函数在某些类型参数中的差异。 例如，以下函数可以进行重载：

```cpp
// generics_generic_function_2.cpp
// compile with: /clr /c
ref struct MyClass {
   void MyMythod(int i) {}

   generic <class T>
   void MyMythod(int i) {}

   generic <class T, class V>
   void MyMythod(int i) {}
};
```

以下示例使用泛型函数在数组中查找的第一个元素。 它声明`MyClass`，后者又继承的基类`MyBaseClass`。 `MyClass` 包含泛型函数`MyFunction`，它调用另一个泛型函数`MyBaseClassFunction`，在基类中。 在中`main`，泛型函数， `MyFunction`，使用不同的类型参数调用。

```cpp
// generics_generic_function_3.cpp
// compile with: /clr
using namespace System;

ref class MyBaseClass {
protected:
   generic <class ItemType>
   ItemType MyBaseClassFunction(ItemType item) {
      return item;
   }
};

ref class MyClass: public MyBaseClass {
public:
   generic <class ItemType>
   ItemType MyFunction(ItemType item) {
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);
   }
};

int main() {
   MyClass^ myObj = gcnew MyClass();

   // Call MyFunction using an int.
   Console::WriteLine("My function returned an int: {0}",
                           myObj->MyFunction<int>(2003));

   // Call MyFunction using a string.
   Console::WriteLine("My function returned a string: {0}",
   myObj->MyFunction<String^>("Hello generic functions!"));
}
```

```Output
My function returned an int: 2003
My function returned a string: Hello generic functions!
```

## <a name="see-also"></a>请参阅

[ .NET 和 UWP 的组件扩展](../windows/component-extensions-for-runtime-platforms.md)<br/>
[泛型](../windows/generics-cpp-component-extensions.md)
