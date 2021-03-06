---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 6ee842dbe65cbd9d147e77ec523a2b031d303738
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002387"
---
# <a name="-baseaddress"></a>-baseaddress
创建 DLL 时指定默认基址。  
  
## <a name="syntax"></a>语法  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`address`|必需。 DLL 的基址。 此地址必须指定为十六进制数。|  
  
## <a name="remarks"></a>备注  
 DLL 的默认基址由 .NET Framework 设置。  
  
 请注意，此地址中的低序位字被舍入。 例如，如果指定0x11110001，则它将舍入为0x11110000。  
  
 若要完成 DLL 的签名过程，请使用强名称工具（Sn.exe）的 `–R` 选项。  
  
 如果目标不是 DLL，则忽略此选项。  
  
|在 Visual Studio IDE 中设置-baseaddress|  
|---|  
|1.在 **“解决方案资源管理器”** 中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“编译”选项卡。<br />3.单击 **“高级”** 。<br />4.修改 " **DLL 基址：** " 框中的值。 **注意：**     **Dll 基址：** 框是只读的，除非目标是一个 DLL。|  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target （Visual Basic）](../../../visual-basic/reference/command-line-compiler/target.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)）
