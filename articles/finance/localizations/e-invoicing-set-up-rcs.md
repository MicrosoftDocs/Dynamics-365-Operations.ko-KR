---
title: RCS(Regulatory Configuration Service) 설정
description: 이 항목에서는 RCS(Regulatory Configuration Service)를 설정하는 방법에 대해 설명합니다.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 33aab6f0a482ce3d90a7e9828015a8e7bebb7827
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451729"
---
# <a name="set-up-regulatory-configuration-service-rcs"></a>RCS(Regulatory Configuration Service) 설정

[!include [banner](../includes/banner.md)]

이 항목에서는 RCS(Regulatory Configuration Service)를 설정하는 방법에 대해 설명합니다.

## <a name="turn-on-globalization-features"></a>세계화 기능 켜기

1. RCS 계정에 로그인합니다.
2. **기능 관리** 타일을 선택합니다.
3. **기능 관리** 작업 영역에서 목록에서 **전역화 기능** 을 선택한 다음 **지금 사용** 을 선택합니다.

이제 기본 RCS 대시보드에 **글로벌 기능** 작업 공간의 타일이 나타납니다.

## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>전자 송장 처리와 RCS 통합을 위한 매개 변수 설정

1. **글로벌 기능** 작업 공간의 **관련 설정** 섹션에서 **전자 보고 매개 변수** 를 선택합니다.
2. **전자 송장** 탭의 **서비스 끝점** URI 필드에 다음 표와 같이 Microsoft Azure 지역에 적합한 서비스 끝점을 입력합니다.

    | 데이터 센터 Azure 지리 | 서비스 엔드포인트 URI |
    |----------------------------|----------------------|
    | 미국              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | 유럽                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | 영국             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | 아시아                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | 일본                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. **애플리케이션 ID** 필드가 **0cdb527f-a8d1-4bf8-9436-b352c68682b2** 로 설정되어 있는지 확인합니다. 이 값은 고정 값입니다. GUID(Globally Unique Identifier)만 입력하고 값에 공백, 쉼표, 마침표 또는 따옴표와 같은 다른 기호가 포함되지 않았는지 확인합니다.
4. **LCS 환경 ID** 필드에 LCS(Microsoft Dynamics Lifecycle Services) 환경의 ID를 입력합니다. 이 값은 전자 송장 서비스와 함께 사용할 Finance 또는 Supply Chain Management 환경에 대한 참조입니다. ID를 가져오려면 [LCS](https://lcs.dynamics.com/)에 로그인하여 프로젝트를 연 다음 **환경 관리** 탭의 **환경 세부 정보** 섹션에서 **환경 ID** 필드를 찾습니다.

    > [!IMPORTANT]
    > 전자 송장 추가 기능이 LCS의 여러 Finance 또는 Supply Chain Management 환경에 설치된 경우 항상 가장 최근에 설치된 환경의 환경 ID를 사용하십시오. 전자 송장 기능을 설정하고 작업한 후 새 환경에 추가 기능을 설치하기로 결정한 경우 RCS의 **LCS 환경 ID** 필드를 최신 값으로 업데이트합니다.

5. **저장** 을 선택한 다음 페이지를 닫습니다.

## <a name="configuration-providers"></a>구성 공급자

구성 제공자를 사용하여 전자 송장 발행 프로세스에 사용되는 전자 보고(ER) 구성의 소유자와 소유자의 세계화 기능을 구별할 수 있습니다. Microsoft에서 제공하고 Global 저장소에 게시되는 모든 Globalization 기능의 경우 구성 공급자는 **Microsoft**(`http://microsoft.com`)로 설정됩니다.

활성 구성 공급자에 속하는 ER 구성 및 세계화 기능만 조정할 수 있습니다. 이러한 구성 및 기능을 템플릿으로 사용하여 활성 구성 공급자에 속하는 구성 및 기능을 생성하여 조정할 수 있습니다.

먼저 구성 공급자를 만듭니다. 그런 다음 그 중 하나를 활성으로 설정합니다. **Microsoft** 구성 공급자를 활성으로 설정할 수 없습니다.

### <a name="create-a-configuration-provider"></a>구성 공급자 만들기

1. **전자 보고** 작업 영역의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
2. **새로 만들기** 를 선택합니다.
3. **이름** 필드에 구성 공급자의 고유한 이름을 입력합니다.
4. **인터넷 주소** 필드에 구성 공급자의 고유한 URL을 입력합니다.
5. **저장** 을 선택한 다음 페이지를 닫습니다.

### <a name="select-a-configuration-provider-as-active"></a>구성 공급자를 활성으로 선택합니다.

1. 구성 공급자 목록에서 활성으로 설정할 구성 공급자를 선택합니다.
2. **활성으로 설정** 을 선택합니다.

## <a name="import-er-configurations-from-the-global-repository"></a>글로벌 리포지토리에서 ER 구성 가져오기

1. **전자 보고** 작업 영역의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
2. 구성 공급자 목록에서 **Microsoft** 를 선택한 다음 **리포지토리** 를 선택하십시오.
3. **글로벌** 을 선택한 다음 작업 창에서 **열기** 를 선택합니다.
4. 다음 ER 모델을 가져옵니다.

    - **고객 송장 컨텍스트 모델**
    - **송장 모델**
    - **회계 문서**(브라질 시나리오의 경우, 필요한 경우)
    - **응답 메시지 모델**

5. **송장 모델 매핑** 을 자동으로 가져오지 않은 경우 가져오십시오.
6. 페이지를 닫습니다.
