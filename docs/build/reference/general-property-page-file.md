---
title: “常规”属性页（文件）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCFileConfiguration.ExcludedFromBuild
- VC.Project.VCFileConfiguration.Tool
ms.assetid: 26e3711e-9e7d-4e8d-bc4c-2474538efdad
ms.openlocfilehash: 66e26cabf5af85091000e6cda144898789c581df
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824464"
---
# <a name="general-property-page-file"></a>“常规”属性页（文件）

在“解决方案资源管理器”中选定文件时，“配置属性”节点下的“常规”属性页包含以下属性：

- **从生成中排除**

   指定文件是否应位于当前配置的生成中。

   若要以编程方式访问此属性，请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.ExcludedFromBuild%2A>。

- **工具**

   该工具将用于生成此文件。 请参阅[指定自定义生成工具](../specifying-custom-build-tools.md)，获取详细信息。

   若要以编程方式访问此属性，请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.Tool%2A>。

有关如何访问的信息**常规**下的属性页**配置属性**节点，请参阅[Visual Studio 中的设置 c + + 编译器和生成属性](../working-with-project-properties.md)。

对于非 Windows 项目，请参阅[Linux c + + 属性页引用](../../linux/prop-pages-linux.md)。

## <a name="see-also"></a>请参阅

[C + + 项目属性页引用](property-pages-visual-cpp.md)