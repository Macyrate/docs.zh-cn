---
ms.openlocfilehash: 494e792d63a611cdaedf3e40aa607cfbb0420ae4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901592"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a>身份验证：Newtonsoft.json 类型已替换

在 ASP.NET Core 3.0 中，身份验证 API 中使用的 `Newtonsoft.Json` 类型已替换为 `System.Text.Json` 类型。 除以下情况外，身份验证包的基本使用不受影响：

* 派生自 OAuth 提供程序的类，例如来自 [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers) 的类。
* 高级声明操作实现。

有关详细信息，请参阅 [dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105)。 有关讨论，请参阅 [dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289)。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="recommended-action"></a>建议操作

对于派生的 OAuth 实现，最常见的更改是将 `JObject.Parse` 替换为 `CreateTicketAsync` 重写中的 `JsonDocument.Parse`，如[本文](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40)所示。 `JsonDocument` 可实现 `IDisposable`。

以下列表概述了已知更改：

- <xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> 变为 `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`。 `ClaimAction` 的所有派生的实现都受到类似的影响。
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> 变为 `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> 变为 `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> 已移除一个旧构造函数，另一个将 `JObject` 替换为 `JsonElement`。 已更新 `User` 属性和 `RunClaimActions` 方法以使其匹配。
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> 现在接受类型为 `JsonDocument` 而非 `JObject` 的参数。 已更新 `Response` 属性以使其匹配。 `OAuthTokenResponse` 现在可处置，并将由 `OAuthHandler` 处置。 替代 `ExchangeCodeAsync` 的派生的 OAuth 实现无需处置 `JsonDocument` 或 `OAuthTokenResponse`。
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> 从 `JObject` 更改为 `JsonDocument`。
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> 从 `JObject` 更改为 `JsonElement`。
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> 从接受 `JObject` 更改为 `JsonElement`。

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

- <xref:Microsoft.AspNetCore.Authentication.Facebook?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.MicrosoftAccount?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OAuth?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Twitter?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Facebook`
- `N:Microsoft.AspNetCore.Authentication.Google`
- `N:Microsoft.AspNetCore.Authentication.MicrosoftAccount`
- `N:Microsoft.AspNetCore.Authentication.OAuth`
- `N:Microsoft.AspNetCore.Authentication.OpenIdConnect`
- `N:Microsoft.AspNetCore.Authentication.Twitter`

-->
