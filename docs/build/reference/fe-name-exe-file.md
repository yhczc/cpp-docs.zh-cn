---
title: /Fe（命名 EXE 文件）
ms.date: 11/04/2016
f1_keywords:
- /fe
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
ms.openlocfilehash: 5901ef1997cfea84c97b6d91b30335ff7dbc1d9f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818045"
---
# <a name="fe-name-exe-file"></a>/Fe（命名 EXE 文件）

指定的名称和.exe 文件或由编译器创建的 DLL 的目录。

## <a name="syntax"></a>语法

> **/Fe**[_pathname_] **/Fe:** _路径名_

### <a name="arguments"></a>自变量

*pathname*<br/>
相对或绝对路径和基文件名或相对或绝对路径的目录中或要用于生成可执行文件的基本文件名称。

## <a name="remarks"></a>备注

**/Fe**选项可以指定输出目录、 输出可执行文件名称，或两者，为生成的可执行文件。 如果*pathname*以路径分隔符结束 (**&#92;**)，则假定它指定仅输出目录。 否则为最后一个组成部分*pathname*用作输出文件基名称和其余*路径名*指定的输出目录。 如果*pathname*不具有任何路径分隔符，则假定当前目录中指定输出文件的名称。 *Pathname*必须括在双引号 (**"**) 如果它包含任何字符，不能在短路径，如空格字符或扩展路径组件超过八个字符长时间。

当 **/Fe**未指定选项，或基本的文件时在未指定名称*路径名*，编译器为输出文件赋予其默认名称，使用指定的第一个源或对象文件的基名称在命令行和扩展名为.exe 或.dll。

如果指定[/c （编译而无需链接）](c-compile-without-linking.md)选项， **/Fe**不起作用。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[Visual Studio 中的设置 c + + 编译器和生成属性](../working-with-project-properties.md)。

1. 打开**配置属性** > **链接器** > **常规**属性页。

1. 修改**输出文件**属性。 选择“确定”以保存更改。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>。

## <a name="example"></a>示例

下面的命令行编译并链接当前目录中的所有 C 源代码文件。 生成可执行文件名为 PROCESS.exe 和目录"C:\Users\User Name\repos\My Project\bin"中创建。

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>示例

下面的命令行创建可执行文件在`C:\BIN`具有相同基名称为当前目录中的第一个源文件：

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>请参阅

[输出文件 (/F) 选项](output-file-f-options.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器命令行语法](compiler-command-line-syntax.md)<br/>
[指定路径名](specifying-the-pathname.md)<br/>
