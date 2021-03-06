---
title: 如何：将自定义工具集成到项目属性
ms.date: 04/27/2016
f1_keywords:
- msbuild.cpp.howto.integratecustomtools
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
ms.openlocfilehash: a959eddb36a2de90ebd5b5b1b9eb5e2f4e67c03a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810154"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>如何：将自定义工具集成到项目属性

可以将自定义工具选项添加到 Visual Studio**属性页**通过创建基础的 XML 架构文件的窗口。

**配置属性**一部分**属性页**窗口将显示名为设置组*规则*。 每个规则包含一个工具或一组功能的设置。 例如，**链接器**规则包含链接器工具的设置。 在规则中的设置可以分为*类别*。

本文档介绍如何在包含自定义工具的属性，以便 Visual Studio 启动时加载属性集目录中创建一个文件。 有关如何修改该文件的信息，请参阅[平台可扩展性第 2](https://blogs.msdn.microsoft.com/vsproject/2009/06/18/platform-extensibility-part-2/) Visual Studio 项目团队博客上。

### <a name="to-add-or-change-project-properties"></a>若要添加或更改项目属性

1. 在 XML 编辑器中，创建一个 XML 文件。

1. 将文件保存在 Visual Studio 2017 中`VCTargets\1033`文件夹。 必须为每个版本的 Visual Studio 2017 安装和每种语言的不同路径。 例如，在英语中的 Visual Studio Enterprise 版的文件夹路径是`%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`。 调整您的语言和 Visual Studio 版本的路径。 在每个规则**属性页**窗口表示通过此文件夹中的 XML 文件。 请确保该文件唯一命名的文件夹中。

1. 将内容复制`%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`，而不保存更改，关闭然后再在新的 XML 文件中粘贴内容。 可以使用任何 XML 架构文件-这是只需一个以便开始使用模板可以使用。

1. 在新的 XML 文件中，修改内容根据您的要求。 请确保更改**规则名称**并**Rule.DisplayName**文件的顶部。

1. 保存所做的更改并关闭该文件。

1. 中的 XML 文件`%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>`Visual Studio 启动时加载。 因此，若要测试新文件，请重新启动 Visual Studio。

1. 在中**解决方案资源管理器**，右键单击某个项目，然后单击**属性**。 在中**属性页**窗口中的，在左窗格中，验证是否具有规则的名称的新节点。

## <a name="see-also"></a>请参阅

[在命令行-c + + 的 MSBuild](msbuild-visual-cpp.md)
