---
ms.openlocfilehash: 975edd1bda507b46da353db788d9730560f9b573
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632121"
---
> [!NOTE]
> 从 .NET Core 2.0 SDK 开始，无需运行 [`dotnet restore`](~/docs/core/tools/dotnet-restore.md)，因为它由所有需要还原的命令隐式运行，如 `dotnet new`、`dotnet build` 和 `dotnet run`。
> 在执行显式还原有意义的某些情况下，例如 [Azure DevOps Services 中的持续集成生成](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core)中，或在需要显式控制还原发生时间的生成系统中，它仍然是有效的命令。
