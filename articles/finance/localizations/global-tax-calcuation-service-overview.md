---
title: 세금 계산 개요
description: 이 항목에서는 세금 계산 기능의 전체 범위와 기능에 관해 설명합니다.
author: wangchen
ms.date: 03/02/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a02767e4a90fa6b7414c796d66e758afe0501cf5
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8451738"
---
# <a name="tax-calculation-overview"></a>세금 계산 개요

[!include [banner](../includes/banner.md)]

세금 계산은 Global Tax Engine이 세금 결정 및 계산 프로세스를 자동화하고 단순화할 수 있도록 하는 확장 가능한 다중 테넌트 서비스입니다. 세금 엔진은 완전히 구성할 수 있습니다. 구성할 수 있는 요소에는 과세 데이터 모델, 세금 코드, 세금 적용 가능성 매트릭스 및 세금 계산 공식이 포함되며 이에 제한되지 않습니다. 세금 엔진은 Microsoft Azure 핵심 서비스 플랫폼에서 실행되며 최신 기술과 기하급수적인 확장성을 제공합니다.

세금 계산은 Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management와 통합됩니다. 최종적으로 Dynamics 365 Project Operations, Dynamics 365 Commerce 및 기타 자사 및 타사 애플리케이션과도 통합됩니다.

> [!IMPORTANT]
> 세금 계산을 활성화하면 관련 데이터에 대한 일부 작업이 서비스 데이터를 유지 관리하는 데이터 센터가 아닌 다른 데이터 센터에서 수행될 수 있습니다. 세금 계산을 활성화하기 전에 [이용약관](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md)을 검토하세요. 귀하의 개인 정보는 Microsoft에 중요합니다. 자세히 알아보려면 [개인정보처리방침](https://go.microsoft.com/fwlink/?LinkId=521839)을 읽어보세요.

세금 계산은 기하급수적인 확장성을 제공하고 다음 작업을 수행하도록 지원하는 마이크로 서비스 기반 세금 엔진입니다.

- 향상된 결정 메커니즘을 통해 올바른 판매세 그룹, 품목 판매세 그룹 및 세금 코드를 자동으로 결정합니다.
- 한 법인의 여러 납세자 등록 번호를 지원하고 과세 거래에 대한 올바른 납세자 등록 번호를 자동으로 결정합니다.
- 이전 주문에 대한 세금 결정, 계산, 게시 및 정산을 지원합니다.
- 특정 비즈니스 요구 사항에 대해 구성 가능한 세금 계산 공식 및 조건을 정의합니다.
- 법인 간에 세금 결정 및 계산 솔루션을 공유하여 유지 관리 노력을 줄이고 오류를 방지합니다.
- 고객 및 공급업체 납세자 등록 번호 결정을 지원합니다.
- 목록 코드 결정을 지원합니다.
- 세금 관할 구역 수준에서 세금 계산 매개 변수를 지원합니다.

세금 계산을 사용하려면 Microsoft Dynamics Lifecycle Services의 프로젝트에서 세금 계산 추가 기능을 설치하세요. 그런 다음 [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/)에서 설정을 완료하고 Finance 및 Supply Chain Management에서 세금 계산을 활성화합니다. 자세한 내용은 [세금 서비스 시작](global-get-started-with-tax-calculation-service.md)을 참조하세요.

## <a name="availability"></a>가용성

세금 계산은 일반적으로 버전 10.0.21부터 모든 고객이 프로덕션 환경에서 사용할 수 있습니다.

새로운 기능이 계속 제공될 것입니다. 지원되는 기능의 적용 범위에 대해 알아보려면 최신 릴리스 계획을 자주 확인하세요.

세금 계산은 다음 Azure 지리에 배포됩니다. 고객 요구 사항에 따라 더 많은 Azure 지리가 추가됩니다.

- 아시아 태평양
- 오스트레일리아
- 캐나다
- 유럽
- 일본
- 스위스
- 영국
- 미국

> [!NOTE]
> 세금 계산은 Dynamics AX 2012와 같은 이전 버전의 Dynamics 365 또는 Dynamics 365의 온-프레미스 배포를 지원하지 않습니다.

## <a name="versions"></a>버전
Finance 또는 Supply Chain Management와 일치하는 버전으로 세금 계산 구성을 가져오고 설정하는 것이 좋습니다.

| Finance 또는 Supply Chain Management 버전 | 세금 구성 버전               |
| --------------- | --------------------------------------- |
| 10.0.18         | 세금 구성 - 유럽 30.12.82     |
| 10.0.19         | 세금 계산 구성 36.38.193 |
| 10.0.20         | 세금 계산 구성 40.43.208 |
| 10.0.21         | 세금 계산 구성 40.48.215 |
| 10.0.22         | 세금 계산 구성 40.48.215 |
| 10.0.23         | 세금 계산 구성 40.50.221 |
| 10.0.24         | 세금 계산 구성 40.50.225 |
| 10.0.25         | 세금 계산 구성 40.50.225 |
| 10.0.26         | 세금 계산 구성 40.54.234 |


## <a name="data-flow"></a>데이터 흐름

다음은 세금 계산을 위한 데이터 흐름 프로세스의 개요입니다. 

1. RCS에서 과세 문서 모델 구성 및 모델 매핑 구성을 보고 가져옵니다. 고급 시나리오를 위한 구성을 확장해야 하는 경우 [세금 구성에 데이터 필드 추가](tax-service-add-data-fields-tax-configurations.md)를 참조하세요.
2. RCS에서 세금 기능을 생성하거나 유지 관리합니다. 세금 기능을 사용하여 세율 및 세금 적용 규칙을 유지할 수 있습니다.
3. 세금 기능 설정이 완료되면 RCS에서 글로벌 리포지토리로 세금 구성 및 세금 기능을 게시합니다.
4. Finance에서 특정 법인에 사용할 세금 기능 설정 버전을 선택합니다.
5. Finance 및 Supply Chain Management에서 평소와 같이 거래를 운영합니다. 세금 계산이 필요한 경우 클라이언트는 판매 주문 또는 구매 주문과 같은 거래 정보를 수집하고 정보를 페이로드로 패키징합니다. 그러면 세금 계산 요청이 전송됩니다.
6. 클라이언트로부터 세금 계산 요청이 수신되고 계산이 완료됩니다. 세금 결과가 클라이언트에 반환됩니다.
7. Dynamics 365 클라이언트는 세금 결과를 수신하고 판매세 페이지에 세금 계산 결과를 표시합니다.

## <a name="supported-transactions"></a>지원되는 거래

세금 계산은 거래별로 활성화할 수 있습니다. 

다음 거래는 버전 10.0.21에서 지원됩니다. 

- 영업

    - 판매 견적
    - 판매 주문
    - 확인
    - 불출 목록
    - 포장 전표
    - 판매 송장
    - 신용 전표
    - 반품 주문
    - 헤더 잡비
    - 라인 잡비

- 구매

    - 구매 주문
    - 확인
    - 영수증 목록
    - 제품 영수증
    - 구매 청구서
    - 헤더 잡비
    - 라인 잡비
    - 신용 전표
    - 반품 주문
    - 구매 요청
    - 구매 요청 라인 잡비
    - 견적 요청
    - 견적 요청 헤더 잡비
    - 견적 요청 라인 잡비

- 인벤토리

    - 이전 주문 – 발송
    - 이전 주문 – 수신

다음 거래는 버전 10.0.23에서 지원됩니다. 

- 자유 텍스트 송장

다음 거래는 버전 10.0.26에서 지원됩니다. 

- 일반 분개장
- 공급업체 송장 분개장

## <a name="supported-countriesregions"></a>지원되는 국가/지역

세금 계산은 법인별로 활성화할 수 있습니다. 

버전 10.0.21에서 법인의 기본 주소로 다음 국가/지역이 지원됩니다.

- 오스트리아
- 벨기에
- 덴마크
- 에스토니아
- 핀란드
- 프랑스
- 독일
- 헝가리
- 아이슬란드
- 이탈리아
- 라트비아
- 리투아니아
- 네덜란드
- 노르웨이
- 폴란드
- 스웨덴
- 스위스
- 영국
- 미국

버전 10.0.22에서 법인의 기본 주소로 다음 국가/지역이 지원됩니다.

- 오스트레일리아
- 바레인
- 캐나다
- 이집트
- 홍콩 특별 행정구
- 쿠웨이트
- 뉴질랜드
- 오만
- 카타르
- 사우디아라비아
- 남아프리카 공화국
- 아랍에미리트

버전 10.0.23에서 법인의 기본 주소로 다음 국가/지역이 지원됩니다.

- 태국
- 일본
- 말레이시아
- 싱가포르

버전 10.0.24에서 법인의 기본 주소로 다음 국가/지역이 지원됩니다.

- 멕시코

버전 10.0.26에서 법인의 기본 주소로 다음 국가/지역이 지원됩니다.

- 중국
- 체코
- 스페인

## <a name="related-resources"></a>관련 리소스

[세금 서비스 시작](./global-get-started-with-tax-calculation-service.md)

[여러 VAT 등록 번호](./emea-multiple-vat-registration-numbers.md)

[이전 주문에 대한 세금 기능 지원](./tasks/tax-feature-support-for-transfer-order.md)

[세금 서비스에서 확장을 구축하는 방법](./tax-service-add-data-fields-tax-integration-by-extension.md)
