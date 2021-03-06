---
title: 使用 ML.NET 自动化机器学习
description: 自动模型选择和训练的概述
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: c6c369dc0b0375f180d33d85ef320ddb24102f3e
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740094"
---
# <a name="automated-machine-learning-with-mlnet"></a>使用 ML.NET 自动化机器学习

自动化机器学习是 ML.NET 的一项功能，可执行自动模型选择和训练。 指定机器学习任务并提供数据集，自动化 ML 会选择具有最佳指标的模型。 它输出：

- 可以加载到预测应用程序中的模型文件
- 用于进行预测的应用程序代码
- 用于特征选择和模型训练的源代码（用于了解模型）

> [!NOTE]
> 此功能目前处于预览状态，且材料可能会有所变化。

自动化 ML 目前仅限于二元分类、多类分类和回归这三个机器学习[任务](resources/tasks.md)。 未来的版本将支持其他机器学习任务。

有三种方法可以使用自动化 ML：

1. 通过图形用户界面，使用 [ML.NET 模型生成器](automate-training-with-model-builder.md)
1. 在命令行中，使用 [ML.NET CLI](automate-training-with-cli.md)
1. 通过应用程序，使用[自动化 ML API](how-to-guides/how-to-use-the-automl-api.md)
