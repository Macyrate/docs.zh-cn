---
title: DataGrid 控件的键盘快捷键
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard shortcuts [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], navigation keys
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
ms.openlocfilehash: 6693531b8d0e820a68d75bf5da40f4169fd244f2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745040"
---
# <a name="keyboard-shortcuts-for-the-windows-forms-datagrid-control"></a>Windows 窗体 DataGrid 控件的键盘快捷键
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 下表列出了可在 Windows 窗体 <xref:System.Windows.Forms.DataGrid> 控件内用于导航的键盘快捷方式：  
  
|操作|快捷方式|  
|------------|--------------|  
|完成单元格输入并向下移动到下一个单元格。<br /><br /> 如果焦点位于子表链接上，则导航到该表。|Enter|  
|如果处于单元编辑模式，则取消单元格编辑。<br /><br /> 如果在选择框中，取消对行进行编辑。|ESC|  
|编辑单元格时，删除插入点前面的字符。|Backspace|  
|编辑单元格时，删除插入点后的字符。|删除|  
|移动到当前行中的第一个单元格。|主页|  
|移动到当前行中的最后一个单元格。|End|  
|突出显示当前单元格中的字符并将插入点放置在行的末尾。 与双击单元格的行为相同。|F2|  
|如果焦点位于某个单元格上，则移动到该行中的下一个单元格。<br /><br /> 如果焦点位于行中的最后一个单元格，则移动到该行的第一个子表链接，然后将其展开。<br /><br /> 如果焦点位于某个子链接上，则移动到下一个子链接。<br /><br /> 如果焦点位于最后一个子链接上，则移动到下一行的第一个单元格。|Tab|  
|如果焦点位于某个单元格上，则移动到该行中的上一个单元格。<br /><br /> 如果焦点位于行中的第一个单元格，则移动到上一行的最后一个展开的子表链接，或移到上一行的最后一个单元格。<br /><br /> 如果焦点位于某个子链接上，则移动到上一个子链接。<br /><br /> 如果焦点位于第一个子链接上，则移动到上一行的最后一个单元格。|Shift + Tab|  
|按 tab 键顺序移到下一个控件。|Ctrl + Tab|  
|按 tab 键顺序移到上一个控件。|Ctrl+Shift+Tab|  
|如果在子表中，则向上移动到父表。 与单击 "后退" 按钮的行为相同。|Alt+向左键|  
|展开 "子表链接"。 ALT + 向下键将展开所有链接，而不仅仅是所选的链接。|ALT + 向下键或 CTRL + 加号|  
|折叠子表链接。 ALT + 向上键折叠所有链接，而不仅仅是所选的链接。|ALT + 向上键或 CTRL + 减号|  
|在箭头方向移动到最远非空白单元格。|CTRL + 箭头|  
|将所选内容扩展到箭头的方向（不包括子表链接）。|SHIFT + 向上键/向下键|  
|将所选内容扩展到箭头方向最远的非空行（不包括子表链接）。|CTRL + SHIFT + 向上/向下键|  
|移动到左上角的单元格。|Ctrl+Home|  
|移动到右下角的单元格。|Ctrl+End|  
|将所选内容扩展到顶部行。|Ctrl+Shift+Home|  
|将所选内容扩展到底部行。|Ctrl+Shift+End|  
|选择当前行（不包括子表链接）。|SHIFT + 空格键|  
|选择整个网格（不包括子表链接）。|CTRL+A|  
|在子表中时显示父行。|Ctrl+PAGE DOWN|  
|当位于子表中时，隐藏父行。|Ctrl+PAGE UP|  
|将选择范围向下扩展一屏（不包括子表链接）。|Shift+Page Down|  
|将选择范围向上扩展一屏（不包括子表链接）。|Shift+Page Up|  
|为当前行调用 <xref:System.Windows.Forms.DataGrid.EndEdit%2A> 方法。|Ctrl+Enter|  
|处于编辑模式时，在单元格中输入 <xref:System.DBNull.Value?displayProperty=nameWithType> 值。|Ctrl+0|  
  
## <a name="see-also"></a>另请参阅

- [DataGrid 控件概述](datagrid-control-overview-windows-forms.md)
- [DataGrid 控件](datagrid-control-windows-forms.md)
