---
title: BSCMAKE 参考
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, reference
- Microsoft Browse Information Maintenance Utility
- browse windows
- browse information files (.bsc), building
- .bsc files, building
- bsc files, building
- BSCMAKE
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
ms.openlocfilehash: 4303e48e3d02f0f69b177e8a888157a6f90aaa89
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822348"
---
# <a name="bscmake-reference"></a>BSCMAKE 参考

> [!WARNING]
> 虽然安装 Visual Studio 时仍会安装 BSCMAKE，但 IDE 将不再使用它。 从 Visual Studio 2008 起，浏览信息和符号信息自动存储在解决方案文件夹的 SQL Server .sdf 文件中。

Microsoft 浏览信息维护实用工具 (BSCMAKE.EXE) 从编译期间创建的 .sbr 文件生成浏览信息文件 (.bsc)。 某些第三方工具进行代码分析使用.bsc 文件。

生成程序时，可以使用 BSCMAKE 生成浏览信息文件，以自动为你的程序创建浏览信息文件。 如果在 Visual C++ 开发环境中创建浏览信息文件，则不需要知道如何运行 BSCMAKE。 但是，你可能需要阅读本主题以了解可用的选项。

如果在开发环境外部生成程序，则仍可以创建一个可在该环境中检查的自定义 .bsc。 对编译期间创建 .sbr 文件运行 BSCMAKE。

> [!NOTE]
>  可以仅从 Visual Studio 开发人员命令提示符启动此工具。 无法从系统命令提示符或文件资源管理器中启动它。

本节包括下列主题：

- [生成浏览信息文件：概述](building-browse-information-files-overview.md)

- [生成.bsc 文件](building-a-dot-bsc-file.md)

- [BSCMAKE 命令行](bscmake-command-line.md)

- [BSCMAKE 命令文件](bscmake-command-file-response-file.md)

- [BSCMAKE 选项](bscmake-options.md)

- [BSCMAKE 退出代码](bscmake-exit-codes.md)

## <a name="see-also"></a>请参阅

[其他 MSVC 生成工具](c-cpp-build-tools.md)
