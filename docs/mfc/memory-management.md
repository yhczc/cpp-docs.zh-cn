---
title: 内存管理
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
ms.openlocfilehash: 1c7f901009d5e1e7f0af20d493bb748b46b18480
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281286"
---
# <a name="memory-management"></a>内存管理

此系列文章介绍了如何利用与内存管理相关的 Microsoft 基础类库 (MFC) 的通用服务。 内存分配可分为两大类别：帧分配和堆分配。

这两种分配方法之间的一个主要区别是：使用帧分配，您通常可处理实际内存块；使用堆分配，您总是会获得一个指向内存块的指针。 这两个方案之间的另一个主要区别是：帧对象会被自动删除，而堆对象必须由程序员显式删除。

有关 Windows 内存管理程序中的非 MFC 信息，请参阅[内存管理](/windows/desktop/memory/memory-management)Windows SDK 中。

## <a name="what-do-you-want-to-know-more-about"></a>你想要了解更多信息

- [帧分配](../mfc/memory-management-frame-allocation.md)

- [堆分配](../mfc/memory-management-heap-allocation.md)

- [为数组分配内存](../mfc/memory-management-examples.md)

- [从堆释放的数组的内存](../mfc/memory-management-examples.md)

- [为数据结构分配内存](../mfc/memory-management-examples.md)

- [为对象分配内存](../mfc/memory-management-examples.md)

- [可调整大小的内存块](../mfc/memory-management-resizable-memory-blocks.md)

## <a name="see-also"></a>请参阅

[概念](../mfc/mfc-concepts.md)<br/>
[常规 MFC 主题](../mfc/general-mfc-topics.md)
