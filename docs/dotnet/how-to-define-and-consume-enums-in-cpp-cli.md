---
title: 如何：定义和使用枚举在 C + + /cli CLI
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: 0252c4b64690f6a2fb0fd97b97841fe45fcce244
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751448"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>如何：定义和使用枚举在 C + + /cli CLI

本主题讨论了枚举在 C + + /cli CLI。

## <a name="specifying-the-underlying-type-of-an-enum"></a>指定枚举的基础类型

默认情况下，枚举的基础类型是`int`。  但是，可以指定为有符号或无符号形式的类型`int`， `short`， `long`， `__int32`，或`__int64`。  此外可以使用`char`。

```
// mcppv2_enum_3.cpp
// compile with: /clr
public enum class day_char : char {sun, mon, tue, wed, thu, fri, sat};

int main() {
   // fully qualified names, enumerator not injected into scope
   day_char d = day_char::sun, e = day_char::mon;
   System::Console::WriteLine(d);
   char f = (char)d;
   System::Console::WriteLine(f);
   f = (char)e;
   System::Console::WriteLine(f);
   e = day_char::tue;
   f = (char)e;
   System::Console::WriteLine(f);
}
```

**输出**

```Output
sun
0
1
2
```

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>如何托管和标准枚举之间进行转换

没有枚举和一种整型类型; 之间的标准转换强制转换是必需的。

```
// mcppv2_enum_4.cpp
// compile with: /clr
enum class day {sun, mon, tue, wed, thu, fri, sat};
enum {sun, mon, tue, wed, thu, fri, sat} day2; // unnamed std enum

int main() {
   day a = day::sun;
   day2 = sun;
   if ((int)a == day2)
   // or...
   // if (a == (day)day2)
      System::Console::WriteLine("a and day2 are the same");
   else
      System::Console::WriteLine("a and day2 are not the same");
}
```

**输出**

```Output
a and day2 are the same
```

## <a name="operators-and-enums"></a>运算符和枚举

以下运算符是有效枚举在 C + + /cli CLI:

|运算符|
|--------------|
|== != \< > \<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

运算符&#124;^ & ~ + +-仅为枚举定义与基础类型，不包括布尔值的整数。  两个操作数必须是枚举类型。

编译器会执行任何静态或动态检查结果的枚举操作;操作可能会导致不在范围枚举的有效枚举器值。

> [!NOTE]
>  C + + 11 引入了枚举类类型在非托管代码中的它们是明显不同于托管的枚举类在 C + + /cli CLI。 特别是，C + + 11 枚举类类型不支持相同的运算符作为托管的枚举类类型在 C + + /cli CLI 和 C + + /cli CLI 源代码必须提供托管枚举中的可访问性说明符类声明才能将它们区分开来从非托管 （c + +11） 枚举类声明。 有关枚举类在 C + + /cli CLI，C + + /CX 和 C + + 11，请参阅[枚举类](../windows/enum-class-cpp-component-extensions.md)。

```
// mcppv2_enum_5.cpp
// compile with: /clr
private enum class E { a, b } e, mask;
int main() {
   if ( e & mask )   // C2451 no E->bool conversion
      ;

   if ( ( e & mask ) != 0 )   // C3063 no operator!= (E, int)
      ;

   if ( ( e & mask ) != E() )   // OK
      ;
}
```

```
// mcppv2_enum_6.cpp
// compile with: /clr
private enum class day : int {sun, mon};
enum : bool {sun = true, mon = false} day2;

int main() {
   day a = day::sun, b = day::mon;
   day2 = sun;

   System::Console::WriteLine(sizeof(a));
   System::Console::WriteLine(sizeof(day2));
   a++;
   System::Console::WriteLine(a == b);
}
```

**输出**

```Output
4
1
True
```

## <a name="see-also"></a>请参阅

[枚举类](../windows/enum-class-cpp-component-extensions.md)
