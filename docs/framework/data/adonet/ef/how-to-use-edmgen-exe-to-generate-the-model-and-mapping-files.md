---
title: 如何：使用 EdmGen.exe 生成模型和映射文件
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: c74f9344891d43f21034a48ac51723fa7441744d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040306"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>如何：使用 EdmGen.exe 生成模型和映射文件
本主题描述如何使用 EDM 生成器 (EdmGen.exe) 工具生成以下文件（基于 School 数据库）：  
  
- 概念模型（.csdl 文件）。  
  
- 存储模型（.ssdl 文件）。  
  
- 概念模型与存储模型之间的映射（.msl 文件）。  
  
- 使用 Visual Basic 或 C# 的对象层代码。  
  
- 视图文件。  
  
 EdmGen.exe 工具使用 /mode:FullGeneration 生成上面列出的文件。 有关 Edmgen.exe 命令的详细信息，请参阅[EDM 生成器（edmgen.exe）](edm-generator-edmgen-exe.md)。  
  
 如果使用 Edmgen.exe 生成模型和映射文件，则仍需将 Visual Studio 项目配置为使用实体框架。 有关详细信息，请参阅[如何：手动配置实体框架项目](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))。  
  
> [!NOTE]
> 由 EdmGen.exe 生成的概念模型包含数据库中所有对象。 如果希望生成仅包含特定对象的概念模型，请使用实体数据模型向导。 有关详细信息，请参阅[如何：使用实体数据模型向导](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))。  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>使用 EdmGen.exe 为 Visual Basic 项目生成 School 模型  
  
1. 创建 School 数据库。 有关详细信息，请参阅[创建 School 示例数据库](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))。  
  
2. 在命令提示符下执行以下命令（无换行符）：  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>使用 EdmGen.exe 为 C# 项目生成 School 模型  
  
1. 创建 School 数据库。 有关详细信息，请参阅[创建 School 示例数据库](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))。  
  
2. 在命令提示符下执行以下命令（无换行符）：  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>请参阅

- [建模和映射](modeling-and-mapping.md)
- [如何：手动配置实体框架项目](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [如何：预生成视图以提高查询性能](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [ADO.NET 实体数据模型工具](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [如何：使用 EdmGen.exe 验证模型和映射文件](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
