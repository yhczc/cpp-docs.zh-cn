---
title: /V（版本号）
ms.date: 11/04/2016
f1_keywords:
- /v
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
ms.openlocfilehash: 7bebd3ab9677bb340203bbf857e4ee9f287e36e6
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817603"
---
# <a name="v-version-number"></a>/V（版本号）

已否决。 在.obj 文件中嵌入的文本字符串。

## <a name="syntax"></a>语法

```
/Vstring
```

## <a name="arguments"></a>自变量

*string*<br/>
一个字符串，指定要在.obj 文件中嵌入的版本号或版权声明。

## <a name="remarks"></a>备注

字符串标签具有版本号或版权声明的.obj 文件中。 如果它们是字符串的一部分，任何空格或制表符字符必须括在双引号 （"）。 反斜杠 (\\) 必须位于任何两个双引号之前如果它们是字符串的一部分。 之间有空格 **/V**和`string`是可选的。

此外可以使用[注释 （C/c + +）](../../preprocessor/comment-c-cpp.md)与编译器注释类型参数在.obj 文件中放置编译器的名称和版本数。

**/V**选项在 Visual Studio 2005 中; 从开始已弃用 **/V**主要是用于支持构建虚拟设备驱动程序 (VxDs) 和 Visual c + + 工具集不再支持生成 Vxd。 有关不推荐使用的编译器选项的列表，请参阅**已弃用并删除的编译器选项**中[按类别列出的编译器选项](compiler-options-listed-by-category.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[Visual Studio 中的设置 c + + 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 点击“命令行”  属性页。

1. 在 **“附加选项”** 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器命令行语法](compiler-command-line-syntax.md)
