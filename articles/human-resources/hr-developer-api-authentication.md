---
title: 인증
description: 이 문서에서는 Microsoft Dynamics 365 Human Resources 데이터 API(애플리케이션 프로그래밍 인터페이스)로 인증하는 방법에 관한 개요 정보를 제공합니다.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3396f0ae6d089f43c39f318dc9d92a88a7db3d7c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452668"
---
# <a name="authentication"></a>인증


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 문서에서는 Microsoft Dynamics 365 Human Resources 데이터 API(애플리케이션 프로그래밍 인터페이스)로 인증하는 방법에 관한 개요 정보를 제공합니다.

## <a name="overview"></a>개요

Human Resources용 데이터 API는 OData 구현입니다. 자세한 내용은 [OData(Open Data Protocol)](../fin-ops-core/dev-itpro/data-entities/odata.md)를 참조하세요.

API가 애플리케이션의 요청을 처리하려면 애플리케이션이 승인된 호출자로 인증되어야 합니다.

## <a name="fundamentals"></a>기초

애플리케이션이 데이터 API를 호출하려면 Microsoft ID 플랫폼에서 액세스 토큰을 획득해야 합니다. 액세스 토큰에는 애플리케이션에 대한 정보와 Human Resources에서 리소스를 호출하는 데 필요한 권한이 포함되어 있습니다.

### <a name="access-token"></a>액세스 토큰

Microsoft ID 플랫폼에서 발급한 액세스 토큰은 Base64로 인코딩된 JSON(JavaScript Object Notation) 웹 토큰(JWT)입니다. 여기에는 데이터 API(및 Microsoft ID 플랫폼으로 보호되는 기타 웹 API)가 호출자의 유효성을 검사하고 호출자가 요청하는 작업을 수행하기 위한 올바른 권한이 있는지 확인하는 데 사용하는 정보(클레임)가 포함되어 있습니다. 호출 중에 액세스 토큰을 불투명하게 처리할 수 있습니다. 액세스 토큰은 항상 TLS(Transport Layer Security) 및 HTTPS(Hypertext Transfer Protocol Secure)와 같은 보안 채널을 통해 전송해야 합니다.

다음은 Microsoft ID 플랫폼에서 발급한 액세스 토큰의 예입니다.

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

데이터 API를 호출하려면 액세스 토큰을 HTTP 요청의 인증 헤더에 전달자 토큰으로 첨부합니다. 다음은 예입니다.

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a>Azure Portal을 사용하여 새 애플리케이션 등록

1. 회사 또는 학교 계정이나 개인 Microsoft 계정으로 [Microsoft Azure Portal](https://portal.azure.com)에 로그인합니다.

2. 계정에 둘 이상의 테넌트에 대한 액세스 권한이 있는 경우 오른쪽 상단 모서리에서 계정을 선택하고 포털 세션을 원하는 Azure Active Directory(Azure AD) 테넌트로 설정합니다.

3. 왼쪽 창에서 **Azure Active Directory** 서비스를 선택한 다음 **앱 등록 \> 신규 등록** 을 선택합니다.

4. **애플리케이션 등록** 페이지가 열리면 애플리케이션의 등록 정보를 입력합니다.

    - **이름**: 앱 사용자에게 표시될 의미 있는 애플리케이션 이름을 입력합니다.
    - **지원되는 계정 유형**: 앱이 지원해야 하는 계정 유형을 선택합니다.

        | 지원되는 계정 유형 | 설명 |
        |-------------------------|-------------|
        | 이 조직 디렉터리의 계정만 | 기간 업무 앱을 구축하는 경우 이 옵션을 선택합니다. 디렉터리에 앱을 등록하지 않으면 이 옵션을 사용할 수 없습니다.<p>이 옵션은 **Azure AD 전용 단일 테넌트** 에 매핑됩니다.</p><p>이 옵션은 디렉터리 외부에 앱을 등록하지 않는 한 기본 옵션입니다. 이 경우 기본 옵션은 **Azure AD 다중 테넌트 및 개인 Microsoft 계정** 입니다.</p> |
        | 모든 조직 디렉터리의 계정 | 모든 비즈니스 및 교육 고객을 대상으로 하려면 이 옵션을 선택하세요.<p>이 옵션은 **Azure AD 전용 다중 테넌트** 에 매핑됩니다.</p><p>앱을 **Azure AD 전용 단일 테넌트** 로 등록한 경우 **인증** 블레이드를 사용하여 **Azure AD 전용 다중 테넌트** 로 업데이트한 다음 다시 **Azure AD 전용 단일 테넌트** 로 업데이트할 수 있습니다.</p> |
        | 모든 조직 디렉터리의 계정 및 개인 Microsoft 계정 | 가장 광범위한 고객을 대상으로 하려면 이 옵션을 선택하십시오.<p>이 옵션은 **Azure AD 다중 테넌트 및 개인 Microsoft 계정** 에 매핑됩니다.</p><p>앱을 **Azure AD 다중 테넌트 및 개인 Microsoft 계정** 으로 등록한 경우 사용자 인터페이스(UI)에서 이 설정을 변경할 수 없습니다. 대신 지원되는 계정 유형을 변경하려면 애플리케이션 매니페스트 편집기를 사용해야 합니다.</p> |

    - **리디렉션 URI(선택 사항)** – **웹** 또는 **공용 클라이언트(모바일 및 데스크톱)** 중에서 구축하는 앱 유형을 선택합니다. 그런 다음 앱의 리디렉션 URI(또는 응답 URL)를 입력합니다.

        - 웹 앱의 경우 앱의 기본 URL을 제공합니다. 예를 들어 `http://localhost:31544`는 로컬 컴퓨터에서 실행되는 웹 앱의 URL일 수 있습니다. 그런 다음 사용자는 이 URL을 사용하여 웹 클라이언트 앱에 로그인합니다.
        - 공용 클라이언트 앱의 경우 Azure AD가 토큰 응답을 반환하는 데 사용하는 URI를 제공합니다. `myapp://auth`와 같은 앱에 특정한 값을 입력합니다.

        웹 앱 또는 기본 앱의 특정 예제를 보려면 [Microsoft ID 플랫폼(이전의 개발자용 Azure Active Directory)](/azure/active-directory/develop/#quickstarts)을 참조하세요.

5. **API 사용 권한** 에서 **사용 권한 추가** 를 선택합니다. 그런 다음 **내 조직에서 사용하는 API** 탭에서 **Dynamics 365 Human Resources** 를 검색하고 앱에 **사용자\_가장** 권한을 추가합니다. Human Resources의 애플리케이션 ID는 f9be0c49-aa22-4ec6-911a-c5da515226ff입니다. 이 ID를 사용하여 올바른 애플리케이션을 선택하세요.

6. **등록** 을 선택합니다.

   [![Azure Portal에 새 앱 등록.](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)

Azure AD는 앱에 고유한 애플리케이션 ID(클라이언트 ID)를 할당하고 앱의 **개요** 페이지로 이동합니다. 앱에 더 많은 기능을 추가하기 위해 브랜딩, 인증서 및 비밀 옵션과 같은 다른 구성 옵션을 선택할 수 있습니다.

## <a name="retrieving-an-access-token"></a>액세스 토큰 검색

Human Resource 데이터 API를 호출하기 위해 액세스 토큰을 검색하는 세부적인 방법은 클라이언트 애플리케이션을 개발하는 데 사용하는 기술에 따라 다릅니다. 예를 들어 Postman과 같은 [타사 유틸리티로 테스트](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md)하고 C# 콘솔 애플리케이션 또는 웹 서비스를 개발하거나 JavaScript/TypeScript 클라이언트를 구축할 수 있습니다.

예제 C# 클라이언트 애플리케이션:
```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

// requires appropriate NuGet package references in the project
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace TalentODataPoC
{
    class Program
    {
        // prereq: This client app must be registered in Azure Active Directory. The app must be
        // registered as requiring permission to the Dynamics 365 for Talent API (with the Dynamics
        // HCM Workload delegated permission).
        static string clientId = "4fc703ef-672c-4e2c-813f-2f9d29d726db"; // This value should be obtained from AAD and must match your registered app
        static string talentNamespaceUri = "";

        public static async Task CallTalentODataService()
        {
            // authority URI
            UriBuilder uri = new UriBuilder("https://login.microsoftonline.com/common");
            AuthenticationContext authenticationContext = new AuthenticationContext(uri.ToString());

            // request token for the resource we want to access (Human Resources). This will authenticate
            // the user and return an access token containing claims for the authenticated user.
            var authResult = await authenticationContext.AcquireTokenAsync(
                "http://hr.talent.dynamics.com", /*Talent app id or resource URI*/
                clientId, /*registered client app id*/
                new Uri("https://localhost"), /*redirect URI, as registered in your AAD app*/
                new PlatformParameters(PromptBehavior.SelectAccount));

            // create the authorization header, which needs to be passed in the Header of the HTTP Requests to Talent
            string authHeader = authResult.CreateAuthorizationHeader();

            // HINT: paste the JWT into https://jwt.ms to decode and view it
            Console.Write("authHeader: ");
            Console.WriteLine(authHeader);
            Console.WriteLine();

            HttpClient client = new HttpClient();
            client.DefaultRequestHeaders.Add("Authorization", authHeader);

            string s;

            Console.Write("Talent Namespace URI: ");
            Console.WriteLine(talentNamespaceUri);
            Console.WriteLine();

            // call the OData service to get JobType data from Talent
            var resultOdata = await client.GetAsync(talentNamespaceUri + "data/JobTypes");
            s = await resultOdata.Content.ReadAsStringAsync();
            Console.WriteLine(s);
            Console.WriteLine();
        }

        static void Main(string[] args)
        {
            Console.WriteLine();

            // if the user passes in a single parameter, assume it is the namespaceUri for Talent
            if (args.Length == 1)
            {
                talentNamespaceUri = args[0];
            } else if (args.Length == 0)
            {
                Console.WriteLine("Enter Talent URL including namespace.");
                Console.WriteLine("Example: https://aos-rts-sf-21454f9d830-prod-westus2.hr.talent.dynamics.com/namespaces/2328af1a-2d45-4c6a-99e3-12a4c3867dcf/");
                Console.Write("> ");
                talentNamespaceUri = Console.ReadLine();
                if (!talentNamespaceUri.EndsWith("/"))
                {
                    talentNamespaceUri = talentNamespaceUri + "/";
                }
            } else
            {
                Console.WriteLine("Unexpected Arguments");
                System.Environment.Exit(1);
            }

            Task t = Program.CallTalentODataService();
            t.Wait();
        }
    }
}
```

액세스 토큰을 검색한 후에는 위에서 설명한 대로 데이터 API에 보내는 각 요청과 함께 인증 헤더의 토큰을 전달자 토큰으로 전달합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
