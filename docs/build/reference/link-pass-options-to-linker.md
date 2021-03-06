---
title: /link（将选项传递到链接器）
ms.date: 11/04/2016
f1_keywords:
- /link
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
ms.openlocfilehash: 7f40841b82db9f46019ce2a96a61a1a0f622b6d5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813430"
---
# <a name="link-pass-options-to-linker"></a>/link（将选项传递到链接器）

将一个或多个链接器选项传递给链接器。

## <a name="syntax"></a>语法

```
/link linkeroptions
```

## <a name="arguments"></a>自变量

*linkeroptions*<br/>
链接器选项或要传递给链接器选项。

## <a name="remarks"></a>备注

**/Link**选项以及与之链接器选项必须出现在任何文件的名称和 CL 选项之后。 是之间需要空格 **/link**和`linkeroptions`。 有关详细信息，请参阅[MSVC 链接器引用](linking.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[Visual Studio 中的设置 c + + 编译器和生成属性](../working-with-project-properties.md)。

1. 单击**链接器**文件夹。

1. 单击链接器属性页。

1. 修改一个或多个属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 不能以编程方式更改此编译器选项。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器命令行语法](compiler-command-line-syntax.md)
