---
title: 函数调用 (C)
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
ms.openlocfilehash: d22bdebc8fa832afb14a2cc09e6a441b7b9e8a5a
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147407"
---
# <a name="function-call-c"></a>函数调用 (C)

函数调用是包含被调用函数的名称或函数指针的值以及（可选）传递给函数的自变量的表达式。

## <a name="syntax"></a>语法

*postfix-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **(**  *argument-expression-list*<sub>opt</sub> **)**

*argument-expression-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*assignment-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*argument-expression-list* **,** *assignment-expression*

postfix-expression 的计算结果必须为函数地址（例如，函数标识符或函数指针值），argument-expression-list 是其值（“参数”）传递到函数的表达式的列表（用逗号分隔）。 argument-expression-list 参数可以为空。

function-call 表达式具有函数的返回值的值和类型。 函数不能返回数组类型的对象。 如果函数的返回类型是 `void`（即该函数已被声明为从不返回值），则 function-call 表达式也具有 `void` 类型。 （有关详细信息，请参阅[函数调用](../c-language/function-calls.md)。）

## <a name="see-also"></a>请参阅

[函数调用运算符：()](../cpp/function-call-operator-parens.md)
