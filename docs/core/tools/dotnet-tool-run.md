---
title: dotnet tool run 命令
description: dotnet tool run 命令调用本地工具。
ms.date: 02/14/2020
ms.openlocfilehash: 05b21c0f5ea86f4b99b220f556c61bf83f464114
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543826"
---
# <a name="dotnet-tool-run"></a>dotnet tool run

 本文适用于： ✔️ .NET Core 3.0 SDK 及更高版本

## <a name="name"></a>“属性”

`dotnet tool run` -调用本地工具。

## <a name="synopsis"></a>摘要

```dotnetcli
dotnet tool run <COMMAND NAME> 
dotnet tool run <-h|--help>
```

## <a name="description"></a>描述

`dotnet tool run` 命令将搜索当前目录范围内的工具清单文件。 当找到对指定工具的引用时，它会运行该工具。 有关详细信息，请参阅 [调用本地工具](global-tools.md#invoke-a-local-tool)。

## <a name="arguments"></a>自变量

- **`COMMAND_NAME`**

  要运行的工具的命令名称。

## <a name="options"></a>选项

- **`-h|--help`**

  打印出有关命令的简短帮助。

## <a name="example"></a>示例

- **`dotnet tool run dotnetsay`**

  运行 `dotnetsay` 本地工具。

## <a name="see-also"></a>请参阅

- [.NET Core 工具](global-tools.md)
