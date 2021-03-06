---
title: 如何：使用 LINQ 对查询结果进行排序
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: 020e4a3800515329b29e2941baf50d3d8add4605
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354170"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a>如何：使用 LINQ 排序查询结果 (Visual Basic)
使用语言集成查询（LINQ），可以轻松地访问数据库信息和执行查询。  
  
 下面的示例演示如何创建一个新的应用程序，该应用程序对 SQL Server 数据库执行查询，并通过使用 `Order By` 子句按多个字段对结果进行排序。 每个字段的排序顺序可以是升序或降序。 有关详细信息，请参阅[Order By 子句](../../../../visual-basic/language-reference/queries/order-by-clause.md)。  
  
 本主题中的示例使用 Northwind 示例数据库。 如果你的开发计算机上没有此数据库，可以从 Microsoft 下载中心进行下载。 有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>创建与数据库的连接  
  
1. 在 Visual Studio 中，通过单击 "**视图**"**菜单上的** **服务器资源管理器**/数据库资源管理器来打开**服务器资源管理器**/**数据库资源管理器**。  
  
2. 右键单击**服务器资源管理器**/**数据库资源管理器**中的 "**数据连接**"，然后单击 "**添加连接**"。  
  
3. 指定与 Northwind 示例数据库的有效连接。  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>添加包含 LINQ to SQL 文件的项目  
  
1. 在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。 选择 Visual Basic **Windows 窗体应用程序**作为项目类型。  
  
2. 在 **“项目”** 菜单上，单击 **“添加新项”** 。 选择 " **LINQ to SQL 类**" 项模板。  
  
3. 为 `northwind.dbml` 文件命名。 单击 **“添加”** 。 为 northwind 文件打开对象关系设计器（O/R 设计器）。  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>添加要查询到 O/R 设计器的表  
  
1. 在**服务器资源管理器**/**数据库资源管理器**中，展开与 Northwind 数据库的连接。 展开 "**表**" 文件夹。  
  
     如果关闭了 O/R 设计器，则可以通过双击先前添加的 northwind 文件来重新打开它。  
  
2. 单击 "Customers" 表，并将其拖到设计器的左窗格中。 单击 "Orders" 表，并将其拖到设计器的左窗格中。  
  
     设计器将为您的项目创建新的 `Customer` 和 `Order` 对象。 请注意，设计器将自动检测表之间的关系，并创建相关对象的子属性。 例如，IntelliSense 将显示 `Customer` 对象具有与该客户相关的所有订单的 `Orders` 属性。  
  
3. 保存更改并关闭设计器。  
  
4. 保存你的项目。  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>添加代码以查询数据库并显示结果  
  
1. 从 "**工具箱**" 中，将 "<xref:System.Windows.Forms.DataGridView>" 控件拖动到项目的默认 Windows 窗体 "Form1"。  
  
2. 双击 "Form1"，将代码添加到窗体的 `Load` 事件。  
  
3. 将表添加到 O/R 设计器后，设计器会将 <xref:System.Data.Linq.DataContext> 对象添加到项目。 此对象包含访问这些表所需的代码，以及访问每个表的单个对象和集合的代码。 项目的 <xref:System.Data.Linq.DataContext> 对象根据 .dbml 文件的名称进行命名。 对于此项目，<xref:System.Data.Linq.DataContext> 对象名为 `northwindDataContext`。  
  
     您可以在代码中创建 <xref:System.Data.Linq.DataContext> 的实例，并查询由 O/R 设计器指定的表。  
  
     将以下代码添加到 `Load` 事件，以查询作为数据上下文的属性公开的表并对结果进行排序。 查询按客户订单数对结果进行排序，并按降序排列。 具有相同订单数的客户按公司名称升序排序（默认值）。  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. 按 F5 运行项目并查看结果。  
  
## <a name="see-also"></a>另请参阅

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [查询](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext 方法（O/R 设计器）](/visualstudio/data-tools/datacontext-methods-o-r-designer)
