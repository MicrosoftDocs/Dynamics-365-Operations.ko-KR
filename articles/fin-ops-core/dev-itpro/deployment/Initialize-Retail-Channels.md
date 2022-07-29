---
title: Commerce Scale Unit(클라우드) 초기화
description: 이 항목에서는 Microsoft Dynamics 365 Commerce에서 Commerce Scale Unit(클라우드)을 초기화하는 방법에 대해 설명합니다.
author: AamirAllaq
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2018-4-30
ms.openlocfilehash: 84e70515accde161e7efa36755edec68d26be952
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2022
ms.locfileid: "8460960"
---
# <a name="initialize-commerce-scale-unit-cloud"></a>Commerce Scale Unit(클라우드) 초기화

[!include[banner](../includes/banner.md)]

이 항목에서는 Microsoft Dynamics 365 Commerce에서 Commerce Scale Unit(클라우드)을 초기화하는 방법에 대해 설명합니다.

애플리케이션 버전 8.1.2.x 이상이 있는 Tier-2 샌드박스 또는 프로덕션 환경을 사용하는 경우 또는 클라우드에서 Retail Server를 사용하는 전자 상거래 작업의 경우 POS(Point of Sale) 작업에 소매 채널 기능을 사용하려면 먼저 Commerce Scale Unit(클라우드)을 초기화해야 합니다. 초기화는 Commerce Scale Unit(클라우드)를 배포합니다.

> [!IMPORTANT]
> 클라우드에서 소매 채널 기능을 사용하는 기존 고객의 경우 비즈니스를 지속적으로 중단 없이 지원하려면 Commerce Scale Unit을 사용하도록 소매 채널을 업데이트해야 합니다. Commerce Scale Unit 없이 배포된 새로운 환경은 더 이상 클라우드 호스팅 소매 채널 구성 요소에 대한 품질 및 서비스 업데이트를 수신하지 않습니다. Commerce Scale Unit(자체 호스팅)을 독점적으로 사용하는 고객에게는 필요한 조치가 없습니다. 확장이 필요한 경우 Microsoft FastTrack Solution Architect에 문의하세요.

## <a name="prerequisites"></a>전제 조건

1. 버전 8.1.2.x 이상이 있는 Tier-2 샌드박스 또는 프로덕션 환경을 배포합니다.
2. 환경당 최대 2개의 Commerce Scale Unit을 자체 배포할 수 있습니다. 환경당 2개 이상의 Commerce Scale Unit이 필요한 경우 Microsoft Dynamics LCS(Lifecycle Services)에서 지원 요청 생성 및 **추가 Commerce Scale Unit 요청** 을 입력하고 환경 ID, Commerce Scale Unit 수 및 원하는 데이터 센터 지역을 나타냅니다. 요청은 영업일 기준 5일 이내에 완료됩니다. 환경당 2개 이상의 Commerce Scale Units가 필요하지 않은 경우 지원 요청을 생성할 필요가 없습니다. 
3. Commerce Scale Unit을 초기화하려면 먼저 Lifecycle Services에서 프로젝트 소유자 권한이 있어야 합니다.
4. 사용자 환경에서 정품 라이선스 구성 키가 활성화되어 있는지 확인합니다. 자세한 내용은 [라이센스 코드 및 구성 키 보고서](../sysadmin/license-codes-configuration-keys-report.md)를 참조하세요. Commerce Scale Unit을 사용하려면 다음 키가 켜져 있어야 합니다.

    - RetailBasic
    - RetaileCommerce - Dynamics 365 Commerce용 전자 상거래를 사용할 계획인 경우.
    - RetailGiftCard - 기프트 카드를 사용하려는 경우.
    - RetailInvent - 인벤토리를 사용하려는 경우.
    - RetailModernPos - 판매 시점(POS)을 사용하려는 경우.
    - RetailReplenishment - 보충을 사용하려는 경우.
    - RetailScheduler
    - RetailStores - POS를 사용할 계획인 경우.


## <a name="region-availability"></a>지역 가용성
Commerce Scale Unit은 다음 지역에서 배포할 수 있습니다.

| 글로벌 위치 | 지역              | 가용성        |
|-----------------|---------------------|---------------------|
| 아메리카        | 미국 동부             | 정식 제공 |
| 아메리카        | 미국 동부 2           | 정식 제공 |
| 아메리카        | 미국 중북부    | 정식 제공 |
| 아메리카        | 미국 중남부    | 정식 제공 |
| 아메리카        | 미국 중부          | 정식 제공 |
| 아메리카        | 미국 서부             | 정식 제공 |
| 아메리카        | 미국 서부 2           | 정식 제공 |
| 아메리카        | 캐나다 중부      | 제한된 용량    |
| 아메리카        | 캐나다 동부         | 제한된 용량    |
| 아메리카        | 미국 중서부     | 제한된 용량    |
| APAC            | 오스트레일리아 동부      | 정식 제공 |
| APAC            | 동남 아시아      | 정식 제공 |
| APAC            | 일본 동부          | 정식 제공 |
| APAC            | 일본 서부          | 정식 제공 |
| APAC            | 오스트레일리아 남동부 | 제한된 용량    |
| APAC            | 동아시아           | 제한된 용량    |
| APAC            | 인도 남부         | 제한된 용량    |
| APAC            | 인도 중부       | 제한된 용량    |
| EMEA            | 서유럽         | 정식 제공 |
| EMEA            | 북유럽        | 정식 제공 |
| EMEA            | 영국 남부            | 제한된 용량    |
| EMEA            | 영국 서부             | 제한된 용량    |

제한된 용량 지역의 배포 용량은 매우 제한적입니다. 배포 요청은 사례별로 평가됩니다. 제한된 용량 지역에 배포해야 하는 강력한 비즈니스 요구 사항이 있는 경우 대기자 명단에 추가하도록 지원 요청을 제출할 수 있습니다.

![지역 가용성을 보여주는 지도.](media/Commerce-Scale-Unit-Region-Availability.png "지역 가용성을 보여주는 지도")

## <a name="initialize-commerce-scale-unit-as-part-of-a-new-environment-deployment"></a>새 환경 배포의 일부로 Commerce Scale Unit 초기화

본사가 가능한지 확인해주세요. 초기화 과정에서 스케일 유닛을 본사에 등록하기 위해 필요합니다. 본사가 서비스 중일 때 스케일 장치를 초기화하는 것은 서비스 프로세스 중에 사용할 수 없게 될 수 있으므로 권장하지 않습니다.

1. 본사 환경이 사용 가능하고 [유지 관리 모드](../sysadmin/maintenance-mode.md)에서 사용할 수 없어야 합니다.
2. LCS의 환경 세부 정보 페이지에서 **환경 기능 \> 상거래** 를 선택합니다.
3. Commerce 설정 배포 페이지에서 **초기화** 를 선택합니다.
4. 초기화할 Commerce Scale Unit의 버전을 선택합니다.
5. Commerce Scale Unit을 초기화할 지역을 선택합니다.

## <a name="configure-channels-to-use-commerce-scale-unit"></a>Commerce Scale Unit을 사용하도록 채널 구성

Commerce Scale Unit이 배포된 후에는 채널이 데이터베이스를 사용하도록 구성되었는지 확인해야 합니다. 

Commerce Scale Unit 데이터베이스를 사용하도록 채널을 구성하려면 다음 단계를 따르세요.

1. 상업 본부에서 **소매 및 상업 \> 본사 설정 \> 상거래 스케줄러 \> 채널 데이터베이스** 로 이동합니다.
1. 왼쪽 창에서 채널 데이터베이스를 선택합니다.
1. **소매 채널** 빠른 탭에서 **추가** 를 선택한 다음 드롭다운 목록에서 소매 채널을 선택합니다.
1. **추가** 를 선택한 다음 드롭다운 목록에서 온라인 채널을 선택합니다. 

완료되면 **소매 및 상업 \> 소매 및 상거래 IT \> 배포 일정** 으로 이동하고 작업 9999를 실행합니다.

> [!NOTE] 
> 작업 9999는 모든 신제품과 고객을 Commerce Scale Unit에 동기화합니다. 이 프로세스는 오래 걸릴 수 있습니다. 전자 상거래 사이트 빌더 구성에만 채널을 사용할 수 있어야 하는 경우 작업 9999 대신 작업 1070을 실행할 수 있습니다.

### <a name="database-refresh-and-commerce-scale-units"></a>데이터베이스 새로 고침 및 Commerce Scale Unit

시작하기 전에 [Commerce 기능을 사용하는 환경에 대한 데이터베이스 새로 고침 후 완료 단계](../database/database-refresh.md)에 익숙해져야 합니다.

배율 단위 채널 데이터베이스 레코드(채널 데이터베이스 형식)는 데이터베이스 새로 고침의 일부로 환경 간에 이동할 수 없습니다. 레코드가 환경별 구성을 나타내기 때문입니다.

데이터베이스 새로 고침 후 LCS에서 스케일 단위 재배포를 실행하여 스케일 단위의 채널 데이터베이스 레코드를 다시 생성할 수 있습니다. 등록이 누락된 것으로 감지되는 경우 스케일 장치의 배포 또는 서비스 작업은 스케일 장치를 본사에 등록하려고 시도합니다.

확장 장치가 이미 있는 동일한 버전을 배포하도록 선택하여 구성 요소를 변경하지 않고 확장 장치를 다시 배포할 수 있습니다. 이것은 다음 단계에 따라 LCS에서 수행할 수 있습니다.

1. LCS의 환경 세부 정보 페이지에서 **환경 기능 \> 리테일** 을 선택합니다.
2. 설정 배포 페이지에서 재배포할 배율 단위를 선택합니다.
3. 저울의 작동 메뉴에서 **업데이트** 를 선택합니다.
4. 슬라이더의 **버전 선택** 드롭다운에서 옵션 **버전 지정** 을 선택합니다.
5. **버전 지정** 아래의 텍스트 상자에서 **현재 버전** 레이블 옆에 스케일 단위에 대해 표시된 버전을 입력하십시오.
6. **업데이트** 단추를 클릭합니다.

이전에 확장을 적용했더라도 스케일 단위를 업데이트할 때 스케일 단위에 적용된 마지막 확장 패키지가 자동으로 선택되므로 **확장 업데이트** 를 선택할 필요가 없습니다.

배율 단위가 여러 개인 경우 각 저울 단위에 대해 위의 작업을 수행해야 합니다. 원하는 경우 이러한 작업을 병렬로 수행할 수 있습니다.

## <a name="deploy-additional-commerce-scale-units-optional"></a>추가 Commerce Scale Unit 배포(선택 사항)

Commerce Scale Unit을 초기화한 후 라이선스에 권한이 있는 경우 두 번째 Scale Unit을 자체 배포할 수 있습니다. 3개 이상의 Scale Unit을 배포하려면 지원 요청을 생성해야 합니다. 지원 요청에 필요한 Commerce Scale Unit의 수, 환경 이름 및 원하는 지역을 명시합니다. 라이선스에 대한 자세한 내용은 [Dynamics 365 라이선스 가이드](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409)를 참조하세요. 

배포하는 각 추가 Commerce Scale Unit에 대해 다음 단계에 따라 별도의 채널 데이터베이스 그룹을 만드는 것이 좋습니다.

1. 상업 본사에서 **소매 및 상거래 > Retail Headquarters > 소매 스케줄러 설정 > 채널 데이터베이스 그룹** 으로 이동합니다.
2. 새 채널 데이터베이스 그룹을 만듭니다.
3. **소매 및 상업 > Retail Headquarters > 소매 스케줄러 설정 > 채널 데이터베이스** 로 이동하고 새로 생성된 Commerce Scale Unit에 해당하는 채널 데이터베이스를 선택합니다.
4. **편집** 을 선택하고 새 채널 데이터베이스 그룹을 선택합니다.
5. **저장** 을 선택합니다.
6. 선택한 채널 데이터베이스에 대해 **전체 데이터 동기화 실행** 을 선택합니다.

## <a name="additional-considerations-if-you-initialize-cloud-hosted-commerce-channel-components-in-an-existing-environment"></a>기존 환경에서 클라우드 호스팅 상거래 채널 구성 요소를 초기화하는 경우 추가 고려 사항

환경에서 클라우드 호스팅 Commerce 채널 구성 요소를 이미 사용하고 있는 경우 Commerce Scale Unit을 초기화하면 해당 구성 요소가 업데이트될 때 가동 중지 시간을 줄이는 데 도움이 됩니다. Commerce Scale Unit을 초기화하기 전에 추가 계획이 필요합니다.

클라우드 호스팅 상거래 채널 구성 요소를 사용하는 환경에서 첫 번째 Commerce Scale Unit를 초기화할 때 초기화 프로세스는 클라우드 호스팅 채널 구성 요소와 연결된 채널을 첫 번째 규모 단위로 마이그레이션합니다. Store Scale 단위와 연결된 채널은 영향을 받지 않습니다.

마이그레이션 프로세스는 채널에 투명합니다. 저울 단위 초기화가 시작된 후 다음 작업이 자동으로 수행됩니다.

1. 새로운 Commerce Scale Unit이 생성되어 환경과 연결됩니다.
2. Commerce Scale Unit은 본사에서 사용 가능한 채널 데이터베이스로 등록됩니다.
3. 본사의 **기본** 채널 데이터베이스에 매핑된 모든 채널은 새로운 Commerce Scale Unit에 매핑되도록 업데이트됩니다.
4. Commerce Data Exchange(CDX) 전체 데이터 동기화가 수행되어 채널 데이터를 새 스케일 단위로 가져옵니다.

**Commerce Scale Unit 초기화 계획 및 테스트** 일반적으로 Commerce Scale Unit을 초기화할 때 소매 서버 또는 클라우드 POS를 사용하는 전자 상거래 채널 운영은 물론 매장 운영에 대해 5시간의 가동 중지 시간을 계획해야 합니다.

1. 프로덕션 환경에서 샌드박스 UAT 환경으로 데이터베이스 새로 고침을 수행합니다. 
2. 샌드박스 UAT 환경에서 Commerce Scale Unit을 초기화합니다. 
3. Commerce Scale Unit에 대해 완료되는 초기화 시간에 유의하세요. 이는 매장 운영 및 전자 상거래 운영을 사용할 수 없는 프로덕션 환경에서 이 작업에 걸리는 시간과 비슷합니다.

Commerce Scale Unit을 초기화하기 전에 다음 추가 단계를 수행해야 합니다.

- **모든 POS 근무조 닫기** - 마이그레이션 후 POS 사용자는 마이그레이션 프로세스 중에 활성화된 교대조를 닫을 수 없습니다.
- **모든 P-작업이 성공적으로 완료되었는지 확인** - 보류 중인 트랜잭션을 동기화하기 위한 P-작업은 CSU가 초기화되기 전에 완료되는 것이 좋습니다.
- **모든 POS 장치의 로그아웃** - 마이그레이션 중에는 POS 작업이 지원되지 않습니다.
- **POS에서 일시 중단된 모든 거래 회수 및 무효화** - 일시 중단된 트랜잭션은 초기화의 일부로 보존되지 않습니다.

> [!IMPORTANT]
> Commerce Scale Unit 초기화의 일부로 이전에 일시 중단된 트랜잭션이 손실되고 회수할 수 없습니다. 

다음은 초기화 기간 동안 발생하는 일입니다.

- POS 오프라인 기능을 켜지 않으면 클라우드 호스팅 상거래 채널이 작동하지 않습니다.
- 오프라인 기능이 켜진 POS 장치는 기능이 저하됩니다.
- Retail Server에 의존하는 모든 전자 상거래 클라이언트는 중단됩니다.
- Commerce Scale Units(자체 호스팅)에서 호스팅되는 채널은 영향을 받지 않습니다.
- 본사 기능은 영향을 받지 않습니다.

초기화가 완료된 후 발생하는 사항은 다음과 같습니다.

- 활성화된 모든 POS 장치의 장치 활성화 상태가 유지되므로 장치를 다시 활성화할 필요가 없습니다.
- 독립형 하드웨어 스테이션 인스턴스는 계속 작동합니다.
- POS 채널 측 보고서가 재설정되고 초기화 이전의 데이터가 표시되지 않습니다.
- 저널 표시 작업도 재설정되고 초기화 이전의 데이터를 표시하지 않습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
