---
title: /ERRORREPORT（报告内部链接器错误）
ms.date: 12/28/2017
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
ms.openlocfilehash: 26cc157cb7247a3a2ea7c10b415df1160540c9ad
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818019"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT（报告内部链接器错误）

> **/errorreport:**[**无** | **提示符** | **队列** | **发送**]

## <a name="arguments"></a>自变量

**none**<br/>
不收集有关内部编译器错误的报告，或不向 Microsoft 发送报告。

**提示**<br/>
当您收到内部编译器错误时，提示您发送报告。 **提示符**时在开发环境中编译应用程序是默认值。

**queue**<br/>
将错误报告排入队列。 当使用管理员权限登录时，将显示一个窗口，以便可以报告自上次登录以来的任何失败 （将不会提示您发送一次每隔三天的故障报告）。 **队列**时在命令提示符下编译应用程序是默认值。

**发送**<br/>
如果报告启用的 Windows 错误报告服务设置自动向 Microsoft 发送内部编译器错误报告。

## <a name="remarks"></a>备注

**/ERRORREPORT**选项允许你直接向 Microsoft 提供内部编译器错误 (ICE) 信息。

选项 **/errorreport: send**自动将错误信息发送给 Microsoft，如果启用通过 Windows 错误报告服务设置。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目“属性页”  对话框。 有关详细信息，请参阅[Visual Studio 中的设置 c + + 编译器和生成属性](../working-with-project-properties.md)。

1. 打开**配置属性** > **链接器** > **高级**属性页。

1. 修改**错误报告**属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>。

## <a name="see-also"></a>请参阅

[/errorReport（报告内部编译器错误）](errorreport-report-internal-compiler-errors.md)<br/>
[MSVC 链接器引用](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
