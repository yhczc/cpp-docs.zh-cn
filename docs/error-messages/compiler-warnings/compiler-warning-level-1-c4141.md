---
title: 编译器警告（等级 1）C4141
ms.date: 11/04/2016
f1_keywords:
- C4141
helpviewer_keywords:
- C4141
ms.assetid: 6ce8c058-7f4c-41cf-93e7-90a466744656
ms.openlocfilehash: bbc2aea86c367c4977c8899e7aa9b8418e7fedcf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657959"
---
# <a name="compiler-warning-level-1-c4141"></a>编译器警告（等级 1）C4141

“modifier”: 使用了多次

## <a name="example"></a>示例

```
// C4141.cpp
// compile with: /W1 /LD
inline inline void func ();   // C4141
```