---
title: 生成文件中的注释
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, comments
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
ms.openlocfilehash: c66819210d2112f9a68243ed4d3b34f491caae9d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825066"
---
# <a name="comments-in-a-makefile"></a>生成文件中的注释

前加上注释以数字符号 （#）。 NMAKE 忽略从数字符号到下一步的换行字符的文本。 示例：

```
# Comment on line by itself
OPTIONS = /MAP  # Comment on macro definition line

all.exe : one.obj two.obj  # Comment on dependency line
    link one.obj two.obj
# Comment in commands block
#   copy *.obj \objects  # Command turned into comment
    copy one.exe \release

.obj.exe:  # Comment on inference rule line
    link $<

my.exe : my.obj ; link my.obj  # Err: cannot comment this
# Error: # must be the first character
.obj.exe: ; link $<  # Error: cannot comment this
```

若要指定文本的数字符号，请在它前面加一个插入符号 (**^**)，按如下所示：

```
DEF = ^#define  #Macro for a C preprocessing directive
```

## <a name="see-also"></a>请参阅

[生成文件的内容](contents-of-a-makefile.md)
