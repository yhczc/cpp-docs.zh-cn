---
title: "数据库支持，MFC 应用程序向导 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.database
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 875df8f8205d132cf6bcafe536c221876a5e3e51
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="database-support-mfc-application-wizard"></a>MFC 应用程序向导的数据库支持
此页提供允许你指定的数据库级别的选项为你的项目支持 （加上数据源中，如有必要）。  
  
 **数据库支持**  
 设置为你的项目的数据库支持的级别。  
  
|选项|描述|  
|------------|-----------------|  
|**无**|未提供的数据库支持。 这是默认选项。|  
|**仅标头文件**|你的应用程序提供基本级别的数据库支持。 如果你选择下的 ODBC 支持**客户端类型**，MFC 应用程序向导包括你的项目中的标头文件 AFXDB。H。 它将添加链接库，但它不创建任何数据库特定类。 你可以稍后创建记录集并使用它们来检查和更新记录。 如果你选择在 OLE DB 支持**客户端类型**，将包含以下标头文件： ATLBASE。H AFXOLEDB。H ATLPLUS。H|  
|**不支持文件的数据库视图**|包括数据库标头文件、 链接库、 记录视图和记录集。 (仅适用于应用程序与**文档/视图体系结构支持**中选择选项[应用程序类型](../../mfc/reference/application-type-mfc-application-wizard.md)页。)此选项包含文档支持，但不是序列化支持。 如果你选择要包含的数据库视图，你必须指定数据源。|  
|**文件支持的数据库视图**|包括数据库标头文件、 链接库、 记录视图和记录集。 (仅适用于应用程序与**文档/视图体系结构支持**中选择选项**应用程序类型**页。)此选项支持文档序列化，你可以使用，例如，若要更新的用户配置文件。 数据库应用程序通常运行在每个记录基础上而不是对每个文件的基础，因此不需要序列化。 但是，你可能具有序列化的特殊的用途。 如果你选择要包含的数据库视图，你必须指定数据源。|  
  
> [!NOTE]
>  下**数据库支持**，如果你选择**数据库不支持文件的视图**或**数据库支持文件的视图**，视图类派生的不同，具体于在你**客户端类型**选择，如下所示：  
  
-   如果你选择**ODBC**下**客户端类型**，然后应用程序的视图类派生自[CRecordView](../../mfc/reference/crecordview-class.md)。 此类与[CRecordset](../../mfc/reference/crecordset-class.md)-派生类，该类还为你创建 MFC 应用程序向导。 此选项可基于窗体的应用程序，使用记录视图来查看和更新通过其记录集的记录。  
  
-   如果你选择**OLE DB**下**客户端类型**，然后查看类派生自[COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)，并与之关联[CTable](../../data/oledb/ctable-class.md)或[CCommand](../../data/oledb/ccommand-class.md)-派生类。  
  
 **客户端类型**  
 指示你的项目是使用 OLE DB 或 ODBC 的类。  
  
|选项|描述|  
|------------|-----------------|  
|**OLE DB**|选中此选项后，单击**数据源**按钮时，将调用**数据链接属性**向导可帮助你创建的 OLE DB 数据源的连接。|  
|**ODBC**|选中此选项后，单击**数据源**按钮时，将调用**选择数据源**向导可帮助您创建到 ODBC 数据源的连接。|  
  
 **数据源**  
 单击**数据源**按钮以设置使用指定的驱动程序或提供程序和数据库的数据源。 如果你选择 OLE DB 中**客户端类型**选项，此按钮将显示**数据链接属性**对话框。 如果你选择在 ODBC**客户端类型**选项，此按钮提供了**选择数据源**对话框。 此选项才可用，仅当你选择要包含在你的应用程序中的数据库视图。  
  
|选项|描述|  
|------------|-----------------|  
|**数据链接属性**(OLE DB)|建立指定的数据源使用指定的 OLE DB 提供程序。 必须指定 OLE DB 提供程序、 数据、 数据源、 登录 ID 和 （可选） 密码的位置。 有关此对话框中的详细信息，请参阅**数据源**中[ATL OLE DB 使用者向导](../../atl/reference/atl-ole-db-consumer-wizard.md)。|  
|**选择数据源**(ODBC)|建立指定的数据源使用指定的 ODBC 驱动程序。 必须选择要选择数据源的表的数据源名称。 向导将表的所有列都绑定到成员变量的`CRecordset`-派生类。 有关此对话框中的详细信息，请参阅**数据源**中[MFC ODBC 使用者向导](../../mfc/reference/mfc-odbc-consumer-wizard.md)。|  
  
> [!NOTE]
>  在以前版本中，Shift 单击**数据源**按钮打开文件打开对话框，从中可以选择数据链接 (.udl) 文件。 不再支持此功能。  
  
 **生成特性化的数据库类**  
 用于 OLE DB 客户端。 指定是否在生成的项目的数据库类使用属性。  
  
 **将所有列都绑定**  
 用于 ODBC 客户端。 指定是否绑定中所选表的所有列。 如果选中此框，则会绑定所有列;如果不选择此框，没有列被绑定，并在记录集类，必须手动绑定它们。  
  
 **类型**  
 用于 ODBC 客户端。 指定记录集是动态集或快照下, 表中所述。  
  
|选项|描述|  
|------------|-----------------|  
|**动态集**|指定的记录集是动态集。 动态集是查询的提供为查询的数据库的数据的索引的视图的结果。 动态集缓存仅的原始数据的整数索引并提供了一个性能因此获得比快照。 直接与每个记录的索引点找到作为查询结果，并指示是否删除一条记录。 查询记录中还有权访问更新信息。|  
|快照|指定记录集是快照。 快照是查询的结果，并且是时间点的数据库。 由于查询找到的所有记录会都缓存，因此你看不到对原始记录的任何更改。|  
  
## <a name="see-also"></a>另请参阅  
 [MFC 应用程序向导](../../mfc/reference/mfc-application-wizard.md)
