---
title: 核心通信：TCP 传输通道
ms.date: 03/30/2017
ms.assetid: d5cd057f-faec-4e21-ae0e-18bbc22bcfb1
ms.openlocfilehash: 0dfbf939b39d53f104d749e0c0d24e04a05185e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929917"
---
# <a name="core-communications-tcp-transport-channels"></a>核心通信：TCP 传输通道
本主题列出由 TCP 传输通道生成的所有异常。  
  
## <a name="exception-list"></a>异常列表  
  
|资源代码|资源字符串|  
|-------------------|---------------------|  
|SocketCloseReadTimeout|指定套接字的远程终结点未在指定和分配的超时内响应关闭请求。 可能远程终结点在从 Receive 操作接收 EOF 信号 (Null) 后未调用 Close。 分配给此操作的时间可能是更长超时的一部分。|
