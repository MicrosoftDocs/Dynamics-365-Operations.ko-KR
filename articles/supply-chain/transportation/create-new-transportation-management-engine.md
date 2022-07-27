---
title: 새로운 운송 관리 엔진 생성
description: 이 항목에서는 Dynamics 365 Supply Chain Management에서 새 운송 관리 엔진을 만드는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSGenericEngine, TMSRateEngine, TMSMileageEngine, TMSEngineParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 51661
ms.assetid: 0473acef-755e-4b42-acf5-5e5aa902dc0e
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88661b6a974e2bd60f78e38d49a08d3290008b8b
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "8449392"
---
# <a name="create-a-new-transportation-management-engine"></a>새로운 운송 관리 엔진 생성

[!include [banner](../includes/banner.md)]

이 항목에서는 Dynamics 365 Supply Chain Management에서 새 운송 관리 엔진을 만드는 방법에 대해 설명합니다. 

운송 관리(TMS) 엔진은 운송 관리에서 운송 요금을 생성하고 처리하는 데 사용되는 논리를 정의합니다. Supply Chain Management는 요금, 운송 시간, 운송 중 통과할 구역 수와 같은 다양한 매개변수를 계산하는 여러 엔진 유형을 제공합니다. 이 문서에서는 Microsoft Visual Studio 개발 환경과 함께 Supply Chain Management 개발 도구를 사용하여 새 TMS 엔진을 만들고 배포하는 방법 및 운영에서 엔진을 설정하는 방법을 설명합니다. 엔진에 대한 자세한 내용은 [운송 관리 엔진](transportation-management-engines.md)을 참조하세요.

## <a name="create-a-new-tms-engine"></a>새 TMS 엔진 만들기

이 섹션에서는 TMS 엔진 구현이 있는 클래스 라이브러리를 만드는 방법과 Supply Chain Management 모델에서 이를 참조하는 방법을 설명합니다.

1. 새 엔진을 배포하려면 엔진을 포함할 모델이 있어야 합니다. **Dynamics 365** &gt; **모델 관리** 메뉴에서 **모델 생성** 을 클릭하여 새로운 모델을 만듭니다. **모델 생성** 마법사의 첫 페이지에서 모델 이름을 **TMSEngines** 로 지정합니다. 

   [![모델 만들기.](./media/012.png)](./media/012.png)

2. 다음 페이지에서 **새 패키지 만들기** 를 선택합니다. 

   [![새 패키지 만들기.](./media/021.png)](./media/021.png)

3. 다음 페이지에서 참조할 **ApplicationSuite** 를 선택합니다. (**ApplicationPlatform** 모델이 미리 선택되어 있습니다.) 

   [![참조할 모델 선택.](./media/032.png)](./media/032.png)

4. 다음 페이지에서 **완료** 를 클릭하여 새 모델의 생성을 확인합니다. 

   [![모델 생성 완료.](./media/042.png)](./media/042.png)

5. 새 솔루션에서 새 Supply Chain Management 프로젝트를 만들고 이름을 **TMSThirdParty** 로 지정합니다. 프로젝트 속성에서 프로젝트의 모델을 **TMSEngines** 로 설정합니다.
6. 새 C\# 클래스 라이브러리를 솔루션에 추가하고 이름을 **ThirdPartyTMSEngines** 로 지정합니다.
7. ThirdPartyTMSEngines 프로젝트에서 Supply Chain Management 관련 어셈블리에 대한 참조를 추가합니다.
   -   X++ 형식을 참조할 수 있도록 하는 응용 프로그램 어셈블리입니다. 이러한 어셈블리는 다음 위치에서 찾을 수 있습니다. \[패키지 루트\]는 C:\\Packages와 같이 배포된 모든 어셈블리가 배치되는 위치의 경로입니다.

        ```xpp
        [Packages root]\ApplicationPlatform\bin\Dynamics.AX.ApplicationPlatform.dll
        [Packages root]\ApplicationFoundation\bin\Dynamics.AX.ApplicationFoundation.dll
        [Packages root]\ApplicationSuite\bin\Dynamics.AX.ApplicationSuite.dll
        ```
        
   -   데이터, LINQ 및 보조 기능에 대한 액세스를 가능하게 하는 프레임워크 어셈블리. 이 모든 어셈블리는 \[패키지 루트\]\\빈에서 찾을 수 있습니다.

        ```xpp 
        Microsoft.Dynamics.ApplicationPlatform.Environment.dll
        Microsoft.Dynamics.AX.Data.Core.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.AdoNet.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Interface.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Msil.dll
        Microsoft.Dynamics.AX.Server.Core.dll
        Microsoft.Dynamics.AX.Xpp.AxShared.dll
        Microsoft.Dynamics.AX.Xpp.Support.dll
        ```

   -   핵심 TMS 어셈블리(엔진 포함) 및 TMS 기본 어셈블리(헬퍼, 상수, 데이터 전송 클래스 정의 등 포함). 이러한 어셈블리는 다음 위치에서 찾을 수 있습니다.

        ```xpp
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.dll
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.Base.dll
        ```
8.  ThirdPartyTMSEngines 프로젝트에서 자동으로 생성되는 C\# 클래스의 이름을 **SampleRatingEngine** 으로 바꿉니다.
9. 엔진을 구현합니다. 이 예제에서는 속도 엔진을 생성하기 때문에 속도 엔진의 기본 클래스에서 상속합니다. 기본 클래스는 대부분의 속도 엔진 인터페이스(**TMSFwkIRateEngine**). 레이트 메서드를 구현하기만 하면 됩니다. 이 예제를 단순하게 유지하기 위해 이 메서드가 100의 하드 코딩된 속도를 등록하도록 만들 것입니다. **TMSFwkIAccessorialEngine** 과 같은 엔진 인터페이스를 구현하는 엔진을 생성할 수 있습니다. 모든 엔진 인터페이스는 X++로 정의됩니다.

    ```xpp
    namespace ThirdPartyTMSEngines
    {
        using Dynamics.AX.Application;
        using Microsoft.Dynamics.Ax.Tms.Base.Data;
        using Microsoft.Dynamics.Ax.Tms.Base.Utility;
        using Microsoft.Dynamics.Ax.Tms.Bll;
        using System.Xml.Linq;
        public class SampleRatingEngine : BaseRateEngine
        {
            public override RatingDto rate(TmsTransactionFacade transactionFacade, XElement shipment, TMSRateMasterCode rateMasterCode)
            {
               XElement re = shipment.RetrieveOrCreateRatingEntity(this.RatingDto);
               re.AddRate(TmsRateType.Rate, 100);
               return this.RatingDto;
            }
        }
    }
    ```

10. 솔루션을 구축합니다.
11. TMSThirdParty 프로젝트에 대한 새 참조를 추가합니다. 참조는 ThirdPartyTMSEngines 프로젝트를 가리켜야 합니다. 완료되면 솔루션이 다음과 같아야 합니다. 

    [![TMSThirdParty 프로젝트에 대한 참조를 포함하는 솔루션.](./media/052.png)](./media/052.png)

12. 솔루션을 구축합니다. 새 라이브러리가 애플리케이션 탐색기의 **참조** 노드에 표시되는지 확인합니다. 

    [![애플리케이션 탐색기의 참조 노드에 있는 새 라이브러리.](./media/061.png)](./media/061.png)

## <a name="deploy-the-tms-engine-as-a-package"></a>TMS 엔진을 패키지로 배포

타사 TMS 엔진을 배포하는 한 가지 방법은 배포 패키지를 사용하는 것입니다. 이 접근 방식은 프로덕션 환경에서 권장됩니다. 다음 섹션 "Supply Chain Management에서 TMS 엔진 설정"에 설명된 대로 개발 환경에서 어셈블리를 수동으로 복사할 수 있습니다. 엔진을 패키지로 배포하려면 다음 단계를 따르세요.

1. **Dynamics 365** &gt; **배포** 메뉴에서 <strong>배포 패키지 만들기</strong>를 클릭합니다.
2. **배포 패키지 만들기** 대화 상자에서 TMSEngines 모델을 선택하고 패키지 파일을 저장할 경로를 입력합니다. 

   [![TMSEngines 모델 선택 .](./media/071.png)](./media/071.png)

3. 이제 대상 환경에 패키지를 배포할 수 있습니다. 튜토리얼은 [배포 가능한 패키지 설치](../../fin-ops-core/dev-itpro/deployment/install-deployable-package.md)를 참조하세요.

## <a name="set-up-the-tms-engine-in-supply-chain-management"></a>Supply Chain Management에서 TMS 엔진 설정

이 섹션에서는 TMS 엔진을 사용하도록 Supply Chain Management를 설정하는 방법을 설명하고 우리가 만든 새 엔진이 요금 쇼핑에 사용되는 방법을 보여줍니다. 이 섹션에 예에서는 USMF 데모 데이터 회사를 사용합니다.

1. "새 TMS 엔진 작성" 섹션에 설명된 대로 새 엔진을 작성합니다.
2. 솔루션을 구축합니다.
3. 결과 어셈블리를 Supply Chain Management 서버 \[AOSWebRoot\]빈의 바이너리 위치에 복사합니다. **메모:** 이 단계는 개발 환경에서만 관련이 있습니다. 프로덕션 환경에서는 배포 패키지를 통해 배포해야 합니다. 지침은 이전 섹션 "TMS 엔진을 패키지로 배포"를 참조하세요.
4. Supply Chain Management의 **속도 엔진** 페이지에서 새 평가 엔진을 만듭니다. 엔진은 구현한 엔진 클래스와 엔진 클래스 라이브러리를 빌드하여 생성된 엔진 어셈블리를 가리켜야 합니다. 

   [![평가 엔진 페이지에서 새 평가 엔진 작성.](./media/081.png)](./media/081.png)

5. 샘플 비율 엔진을 사용하는 운송업체를 작성합니다. 우리 엔진은 데이터를 사용하지 않기 때문에 속도 마스터를 할당할 필요가 없습니다. 

   [![새 배송사 만들기.](./media/092.png)](./media/092.png)

6. **속도 경로 워크벤치** 페이지에서 **요금 가게** 를 클릭합니다. 다음 스크린샷과 같이 SampleCarrier에서 100.00의 비율이 표시되어야 합니다. 이 예에서는 창고 24에서 고객 US-004까지의 경로에 대한 쇼핑 요금을 계산합니다. 그러나 비율이 하드 코딩되어 있으므로 항상 100.00의 비율이 표시됩니다.

   [![평가 경로 워크벤치.](./media/101.png)](./media/101.png)

## <a name="tips-and-tricks"></a>팁과 요령

- Supply Chain Management용 개발 도구를 사용하는 경우 솔루션에 새 프로젝트를 추가하는 것이 유용합니다. 이 프로젝트를 시작 프로젝트로 설정하고 디버깅 세션을 시작하면 동일한 디버깅 세션에서 X++와 C\# 코드를 모두 디버깅할 수 있습니다.
- ThirdPartyTMSEngines 프로젝트를 변경하고 다시 컴파일할 때마다 결과 어셈블리를 바이너리 위치에 수동으로 복사하거나 배포 패키지를 통해 배포해야 합니다. 그렇지 않으면 오래된 어셈블리를 사용하여 실행할 수 있습니다.
- Supply Chain Management에서 TMS 관련 작업을 실행하면 IIS(인터넷 정보 서비스) 작업자 프로세스가 ThirdPartyTMSEngine 어셈블리를 잠글 수 있으므로 어셈블리를 업데이트할 수 없습니다. 이 경우 w3svc 프로세스를 다시 시작합니다.

### <a name="whitepaper"></a>백서

자세한 내용은 다음 백서를 다운로드하세요(AX2012를 지원하기 위해 작성되었지만 Dynamics 365 Supply Chain Management에 여전히 적용)

- [운송 관리 엔진 구현 및 배포](https://download.microsoft.com/download/b/5/f/b5ff8fef-3918-4c1d-92d5-b67eb0971684/ImplementingAndDeployingTransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]