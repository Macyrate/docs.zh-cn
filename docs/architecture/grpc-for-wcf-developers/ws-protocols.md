---
title: WS-* 协议-适用于 WCF 开发人员的 gRPC
description: 查看 WCF 支持的 WS-* 协议和 gRPC 提供的替代项
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: c8c06a5e23a4d7859165e1c562032055d63d76f7
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503298"
---
# <a name="ws--protocols"></a>WS\* 协议

使用 Windows Communication Foundation （WCF）的一个真正优点是它支持许多现有的_WS\*_ 标准协议。 本部分将简要介绍 gRPC 如何管理相同的 WS\* 协议，并讨论在没有替代方法时可用的选项。

## <a name="metadata-exchange-ws-policy-ws-discovery-and-so-on"></a>元数据交换： WS 策略、WS 发现等

SOAP 服务公开 Web 服务描述语言（WSDL）架构文档，其中包含数据格式、操作或通信选项等信息。 您可以使用此架构来生成客户端代码。

如果服务器和客户端是从同一个 `.proto` 文件生成的，则 gRPC 的效果最好，但服务器反射可选扩展提供了一种从正在运行的服务器中公开动态信息的方法。 有关详细信息，请参阅[Grpc](https://nuget.org/packages/Grpc.Reflection) NuGet 包和[Grpc C#服务器反射](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md)一文。

使用 WS 发现协议在本地网络上查找服务。 gRPC 服务通常位于 DNS 或服务注册表（如 Consul 或 ZooKeeper）中。

## <a name="security-ws-security-ws-federation-xml-encryption-and-so-on"></a>安全性： WS 安全性、WS 联合身份验证、XML 加密等

[第6章](security.md)中更详细地介绍了安全性、身份验证和授权。 但在此，值得注意的是，与 WCF 不同，gRPC 不支持 WS 安全性、WS 联合身份验证或 XML 加密。 尽管如此，gRPC 也能提供卓越的安全性。 所有 gRPC 网络流量在使用 HTTP/2 over TLS 时自动进行加密。 您可以使用 X509 证书进行相互的客户端/服务器身份验证。

## <a name="ws-reliablemessaging"></a>WS-ReliableMessaging

gRPC 未提供与 WS-RELIABLEMESSAGING 等效的。 应该在代码中处理重试语义，如[Polly](https://github.com/App-vNext/Polly)。 当你在 Kubernetes 或类似的业务流程环境中运行时，[服务网格](service-mesh.md)还有助于在服务之间提供可靠的消息传送。

## <a name="ws-transaction-ws-coordination"></a>WS 事务，WS 协调

WCF 对分布式事务的实现使用 Microsoft 分布式事务处理协调器（MSDTC）。 它适用于专门支持的资源管理器，例如 SQL Server、MSMQ 或 Windows 文件系统。 由于使用的技术范围更广，因此在现代微服务世界上没有任何等效项。 有关事务的讨论，请参阅[附录 a](appendix.md)。

>[!div class="step-by-step"]
>[上一页](error-handling.md)
>[下一页](migrate-wcf-to-grpc.md)
