---
title: /FI（命名强制包含文件）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
- /fi
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
ms.openlocfilehash: 2e85706a0266696b83fe1a1a6cdc45ba3399fc21
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809218"
---
# <a name="fi-name-forced-include-file"></a>/FI（命名强制包含文件）

促使预处理器来处理指定的标头文件。

## <a name="syntax"></a>语法

```
/FI[ ]pathname
```

## <a name="remarks"></a>备注

此选项具有相同的效果与指定文件中的双引号`#include`指令在 CL 环境变量，或在命令文件在命令行上指定的每个源代码文件的第一行上。 如果使用了多个 **/FI**选项，文件包含 CL 处理它们的顺序。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[Visual Studio 中的设置 c + + 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 单击**高级**属性页。

1. 修改**强制包含**属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>。

## <a name="see-also"></a>请参阅

[输出文件 (/F) 选项](output-file-f-options.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器命令行语法](compiler-command-line-syntax.md)<br/>
[指定路径名](specifying-the-pathname.md)
