---
title: /SAFESEH（图像具有安全异常处理程序）
ms.date: 11/04/2016
f1_keywords:
- /SAFESEH
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
ms.openlocfilehash: 62784933cbecd4f312c52ae98cab7d232b893f35
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822335"
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH（图像具有安全异常处理程序）

```
/SAFESEH[:NO]
```

当 **/SAFESEH**指定，则链接器才将生成一个映像，是否它还可以生成映像的安全异常处理程序的表。 此表指定哪些异常处理程序是有效的映像的操作系统。

**/SAFESEH**链接为 x86 时才有效目标。 **/SAFESEH**已记下的异常处理程序的平台不支持。 例如，在 x64 和 ARM 上，所有异常处理程序是 PDATA 中都注明。 ML64.exe 对提供支持将发出 SEH 信息 （XDATA 和 PDATA） 的批注添加到映像中，您可以通过 ml64 函数展开。 请参阅[MASM 的 x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)有关详细信息。

如果 **/SAFESEH**未指定，则链接器将生成具有安全异常处理程序表的映像，如果所有模块都都与安全异常处理功能兼容。 如果任何模块不兼容与安全异常处理功能，生成的映像将不包含安全异常处理程序的表。 如果[/SUBSYSTEM](subsystem-specify-subsystem.md) WINDOWSCE 或 EFI_ * 选项之一，指定链接器不会尝试生成具有安全异常处理程序表映像既不的那些子系统才可以进行信息的使用。

如果 **/SAFESEH:NO**指定，则链接器将不会产生安全异常处理程序表的映像，即使所有模块都都兼容与安全异常处理功能。

链接器不能以产生一个图像的最常见原因是因为一个或多个输入文件 （模块） 链接器不与安全异常处理程序功能兼容。 要与安全异常处理程序不兼容的模块的常见原因是因为它创建使用从以前版本的 Visual c + + 编译器。

您还可以注册一个函数作为结构化的异常处理程序通过使用[。SAFESEH](../../assembler/masm/dot-safeseh.md)。

不能将标记的现有二进制数作为具有安全异常处理程序 （或没有异常处理程序）;必须在生成时添加安全异常处理的信息。

生成的安全异常处理程序表的链接器的能力取决于使用 C 运行时库的应用程序。 如果与链接[/NODEFAULTLIB](nodefaultlib-ignore-libraries.md)和所需的安全异常处理程序表，您需要提供加载配置结构 （如可 loadcfg.c CRT 源文件中找到），它包含 Visual c + + 定义的所有项。 例如：

```
#include <windows.h>
extern DWORD_PTR __security_cookie;  /* /GS security cookie */

/*
* The following two names are automatically created by the linker for any
* image that has the safe exception table present.
*/

extern PVOID __safe_se_handler_table[]; /* base of safe handler entry table */
extern BYTE  __safe_se_handler_count;  /* absolute symbol whose address is
                                           the count of table entries */
typedef struct {
    DWORD       Size;
    DWORD       TimeDateStamp;
    WORD        MajorVersion;
    WORD        MinorVersion;
    DWORD       GlobalFlagsClear;
    DWORD       GlobalFlagsSet;
    DWORD       CriticalSectionDefaultTimeout;
    DWORD       DeCommitFreeBlockThreshold;
    DWORD       DeCommitTotalFreeThreshold;
    DWORD       LockPrefixTable;            // VA
    DWORD       MaximumAllocationSize;
    DWORD       VirtualMemoryThreshold;
    DWORD       ProcessHeapFlags;
    DWORD       ProcessAffinityMask;
    WORD        CSDVersion;
    WORD        Reserved1;
    DWORD       EditList;                   // VA
    DWORD_PTR   *SecurityCookie;
    PVOID       *SEHandlerTable;
    DWORD       SEHandlerCount;
} IMAGE_LOAD_CONFIG_DIRECTORY32_2;

const IMAGE_LOAD_CONFIG_DIRECTORY32_2 _load_config_used = {
    sizeof(IMAGE_LOAD_CONFIG_DIRECTORY32_2),
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    &__security_cookie,
    __safe_se_handler_table,
    (DWORD)(DWORD_PTR) &__safe_se_handler_count
};
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[Visual Studio 中的设置 c + + 编译器和生成属性](../working-with-project-properties.md)。

1. 选择**链接器**文件夹。

1. 选择**命令行**属性页。

1. 该选项输入**其他选项**框。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器引用](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
