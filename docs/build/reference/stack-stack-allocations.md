---
title: /STACK（堆栈分配）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
ms.openlocfilehash: 27de554e1933b2753f641be358461c8d7ff4fffa
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813794"
---
# <a name="stack-stack-allocations"></a>/STACK（堆栈分配）

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>备注

/STACK 选项以字节为单位设置堆栈大小。 仅当生成的.exe 文件时，请使用此选项。

`reserve`值指定虚拟内存中的总堆栈分配。 对于 ARM，x86 和 x64 计算机，默认堆栈大小为 1 MB。

`commit` 取决于操作系统的解释。 在 Windows RT 中，它指定一次性分配的物理内存量。 提交的虚拟内存后，在分页文件为保留的空间。 当应用程序需要更多堆栈空间时，增大 `commit` 值可以节省时间，但会增加内存需求并可能延长启动时间。 对于 ARM，x86 和 x64 计算机，默认提交值为 4 KB。

以十进制或 C 语言表示方式指定 `reserve` 和 `commit` 值。

若要设置堆栈大小的另一种方法是使用[STACKSIZE](stacksize.md)模块定义 (.def) 文件中的语句。 **STACKSIZE**重写堆栈分配 (/stack) 如果同时指定了选项。 使用生成的.exe 文件后，可以更改堆栈大小[EDITBIN](editbin-reference.md)工具。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[Visual Studio 中的设置 c + + 编译器和生成属性](../working-with-project-properties.md)。

1. 选择**链接器**文件夹。

1. 选择**系统**属性页。

1. 修改以下属性之一：

   - **堆栈提交大小**

   - **Stack Reserve Size**

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> 和 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> 属性。

## <a name="see-also"></a>请参阅

[MSVC 链接器引用](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
