---
title: 错误 C1001
ms.date: 11/04/2016
f1_keywords:
- C1001
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
ms.openlocfilehash: a7130ed0568de387c99b8296dc4e10d92baec337
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821360"
---
# <a name="fatal-error-c1001"></a>错误 C1001

> 内部编译器 ERROR(compiler file *file*, line *number*)

编译器无法分析生成的构造，通常是由于某个特定表达式和优化选项或出现问题的组合的正确代码。 如果列出的编译器文件具有 utc 或 C2 路径段，它可能是优化错误。 如果文件具有 cxxfe 或 c1xx 路径段，或者是 msc1.cpp，它可能是分析器错误。 如果名为的文件，cl.exe 没有其他信息可用。

通常可以通过删除一个或多个优化选项修复一个优化问题。 若要确定哪个选项出现故障，请移除一个选项一个时间并重新编译之前的错误消息将消失。 选项通常负责[/Og （全局优化）](../../build/reference/og-global-optimizations.md)并[/Oi （生成内部函数）](../../build/reference/oi-generate-intrinsic-functions.md)。 一旦您确定哪些优化选项不负责任，则可以禁用它围绕使用发生错误的函数[优化](../../preprocessor/optimize.md)杂注，并继续使用该模块的其余部分的选项。 有关优化选项的详细信息，请参阅[优化最佳做法](../../build/optimization-best-practices.md)。

如果优化不负责该错误，请尝试重写其中报告错误，在行或几行代码周围的行。 若要查看的代码编译器在预处理后看到的方式，可以使用[/P （预处理到文件）](../../build/reference/p-preprocess-to-a-file.md)选项。

有关如何隔离错误的源以及如何向 Microsoft 报告内部编译器错误的详细信息，请参阅[如何使用 Visual c + + 工具集报告问题](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md)。