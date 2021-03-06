---
title: 编译和链接多线程程序
ms.date: 11/04/2016
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
ms.openlocfilehash: bc56c71c4c3c1367d35dd5995054b1d7371ae9de
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283483"
---
# <a name="compiling-and-linking-multithread-programs"></a>编译和链接多线程程序

Bounce.c 程序在中引入[多线程 C 程序示例](sample-multithread-c-program.md)。

编译的程序默认情况下多线程。

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>若要编译和链接的开发环境中的多线程程序从 Bounce.c

1. 在 **“文件”** 菜单上，单击 **“新建”**，然后单击 **“项目”**。

1. 在中**项目类型**窗格中，单击**Win32**。

1. 在中**模板**窗格中，单击**Win32 控制台应用程序**，然后命名项目。

1. 添加包含项目的 C 源代码的文件。

1. 上**构建**菜单中，通过单击生成项目**生成**命令。

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>若要编译和链接多线程程序 Bounce.c 从命令行

1. 编译和链接程序：

    ```
    CL BOUNCE.C
    ```

## <a name="see-also"></a>请参阅

[使用 C 和 Win32 进行多线程编程](multithreading-with-c-and-win32.md)
