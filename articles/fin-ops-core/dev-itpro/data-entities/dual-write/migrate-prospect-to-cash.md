---
title: Data Integrator에서 이중 쓰기로 현금 데이터로 Prospect 마이그레이션
description: 이 토픽에서는 Data Integrator에서 이중 쓰기로 현금 데이터로 Prospect 마이그레이션하는 방법을 설명합니다.
author: RamaKrishnamoorthy
ms.date: 02/01/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-26
ms.openlocfilehash: 82bfb768b0ecac04184f4b806527346d39584d64
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2022
ms.locfileid: "8461008"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Data Integrator에서 이중 쓰기로 현금 데이터로 Prospect 마이그레이션

[!include [banner](../../includes/banner.md)]

Data Integrator에 사용할 수 있는 Prospect to Cash 솔루션은 이중 쓰기와 호환되지 않습니다. 그 이유는 Prospect to cash 솔루션의 일부로 제공된 계정 테이블의 msdynce_AccountNumber 인덱스 때문입니다. 이 색인이 있는 경우 두 개의 다른 법인에서 동일한 고객 계정 번호를 생성할 수 없습니다. Prospect to 현금 데이터를 Data Integrator에서 이중 쓰기로 마이그레이션하여 이중 쓰기로 새로 시작하도록 선택하거나 Prospect의 마지막 "dorman" 버전을 현금 솔루션으로 설치할 수 있습니다. 이 항목에서는 이러한 접근 방식을 모두 다룹니다.

## <a name="install-the-last-dorman-version-of-the-data-integrator-prospect-to-cash-solution"></a>현금 솔루션에 Data Integrator Prospect의 마지막 "dorman" 버전 설치

**P2C Version 15.0.0.2** 가 현금 솔루션에 데이터 통합자 Prospect의 마지막 "dorman" 버전으로 고려됩니다. [FastTrack for Dynamics 365](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/P2C)에서 다운로드할 수 있습니다.

수동으로 설치해야 합니다. 설치 후 msdynce_AccountNumber 인덱스가 제거된 것을 제외하고는 모든 것이 정확히 동일하게 유지됩니다.

## <a name="steps-to-migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Data Integrator에서 이중 쓰기로 현금 데이터로 Prospect 마이그레이션 단계

Data Integrator에서 이중 쓰기로 현금 데이터로 Prospect 마이그레이션하려면 다음 단계를 따르세요.

1. Prospect to cash Data Integrator 작업을 실행하여 최종 전체 동기화를 수행합니다. 이러한 방식으로 두 시스템(재무 및 운영 앱과 고객 참여 앱)에 모든 데이터가 있는지 확인합니다.
2. 잠재적인 데이터 손실을 방지하려면 Microsoft Dynamics 365 Sales에서 Excel 파일 또는 CSV(쉼표로 구분된 값) 파일로 현금 데이터에 대한 Prospect를 내보냅니다. 다음 엔터티에서 데이터를 내보냅니다.

    - [거래처](#account-table)
    - [연락처](#contact-table)
    - [인보이스](#invoice-table)
    - 송장 제품
    - [주문](#order-table)
    - [주문 제품](#order-products-table)
    - [제품](#products-table)
    - [견적](#quote-and-quote-product-tables)
    - [제품 견적](#quote-and-quote-product-tables)

3. Sales 환경에서 Prospect to Cash 솔루션을 제거합니다. 이 단계에서는 Prospect to Cash 솔루션이 도입한 열과 해당 데이터를 제거합니다.
4. 이중 쓰기 솔루션을 설치합니다.
5. 하나 이상의 법인에 대해 재무 및 운영 앱과 Customer Engagement 앱 간에 이중 쓰기 연결을 만듭니다.
6. 이중 쓰기 테이블 맵을 활성화하고 필요한 참조 데이터에 대한 초기 동기화를 실행합니다. (자세한 내용은 [초기 동기화 고려 사항](initial-sync-guidance.md)을 참조하세요.) 필수 데이터의 예에는 고객 그룹, 지불 조건 및 지불 일정이 포함됩니다. 계정, 견적, 견적 라인, 주문 및 주문 라인 테이블과 같이 초기화가 필요한 테이블에 대해 이중 쓰기 맵을 활성화하지 마세요.
7. Customer Engagement 앱에서 **고급 설정 \> 환경 설정 \> 자료 관리 \> 중복 탐지 규칙** 으로 이동하고 모든 규칙을 비활성화합니다.
8. 2단계에 나열된 테이블을 초기화합니다. 지침은 이 항목의 나머지 섹션을 참조하세요.
9. 재무 및 운영 앱을 열고 계정, 견적, 견적 라인, 주문 및 주문 라인 테이블 맵과 같은 테이블 맵을 활성화합니다. 그런 다음 초기 동기화를 실행합니다. (자세한 내용은 [초기 동기화 고려 사항](initial-sync-guidance.md)을 참조하세요.) 이 프로세스는 처리 상태, 배송 및 청구 주소, 사이트 및 창고와 같은 재무 및 운영 앱의 추가 정보를 동기화합니다.

## <a name="account-table"></a>계정 테이블

1. **회사** 열에 **USMF** 와과 같은 회사 이름을 입력합니다.
2. **관계 유형** 열에 **고객** 을 정적 값으로 입력합니다. 비즈니스 논리에서 모든 계정 레코드를 고객으로 분류하고 싶지 않을 수 있습니다.
3. **고객 그룹 ID** 열에 재무 및 운영 앱의 고객 그룹 번호를 입력합니다. Prospect to cash 솔루션의 기본값은 **10** 입니다.
4. **계정 번호** 사용자 정의 없이 Prospect to 현금 솔루션을 사용하는 경우 **계좌 번호** 값을 **파티 번호** 열에 입력합니다. 사용자 지정이 있고 당사자 번호를 모르는 경우 재무 및 운영 앱에서 이 정보를 가져옵니다.

## <a name="contact-table"></a>연락처 테이블

1. **회사** 열에 **USMF** 와과 같은 회사 이름을 입력합니다.
2. CSV 파일의 **IsActiveCustomer** 값에 따라 다음 열을 설정합니다.

    - CSV 파일에서 **IsActiveCustomer** 가 **네** 로 설저오디어 있으면 **판매 가능** 열을 **네** 로 설정합니다. **고객 그룹 ID** 열에 재무 및 운영 앱의 고객 그룹 번호를 입력합니다. Prospect to cash 솔루션의 기본값은 **10** 입니다.
    - CSV 파일에서 **IsActiveCustomer** 가 **아니요** 로 설정되어 있으면 **판매 가능** 열을 **아니요** 로 설정하고 **문의** 열을 **고객** 으로 설정합니다.

3. **연락처 번호** 사용자 정의 없이 Prospect to 현금 솔루션을 사용하는 경우 다음 열을 설정합니다.

    - CSV 파일의 연락처(**msdynce\_contactnumber**)를 **연락차** 테이블의 연락처 번호(**msdyn\_contactnumber**)로 마이그레이션합니다.
    - **파티 번호** 열에 있는 **연락처 번호** 테이블의 값을 사용합니다.
    - **계정 번호/연락처 사람 ID** 열에 있는 **연락처 번호** 테이블의 값을 사용합니다.

## <a name="invoice-table"></a>인보이스 테이블

**송장** 테이블의 데이터는 재무 및 운영 앱에서 Customer Engagement 앱으로 한 방향으로 흐르도록 설계되었으므로 초기화가 필요하지 않습니다. 초기 동기화를 실행하여 필요한 모든 데이터를 재무 및 운영 앱에서 Customer Engagement 앱으로 마이그레이션합니다. 자세한 내용은 [초기 동기화에 대한 고려 사항](initial-sync-guidance.md)을 참조하세요.

## <a name="order-table"></a>주문 테이블

1. **회사** 열에 **USMF** 와과 같은 회사 이름을 입력합니다.
2. CSV 파일의 **주문 ID** 열의 값을 **판매 주문 번호** 열로 복사합니다.
3. CSV 파일의 **고객** 열의 값을 **청구서 고객 번호** 열로 복사합니다.
4. CSV 파일에서 **국가/지역으로 배송** 열의 값을 **국가/지역으로 배송** 열로 복사합니다. 이 값의 예는 **US** 및 **미국** 이 있습니다.
5. **요청 접수 일자** 열을 설정합니다. 영수증 날짜를 사용하지 않는 경우 CSV 파일의 **요청된 배송 날짜**, **완료 날짜** 및 **제출된 날짜** 열을 사용합니다. 이 값의 예는 **2020-03-27T00:00:00Z** 가 있습니다.
6. **언어** 열을 설정합니다. 이 값의 예는 **en-us** 가 있습니다.
7. **품목 기반** 열을 사용하여 **주문 유형** 열을 설정합니다.

## <a name="order-products-table"></a>주문 제품 테이블

- **회사** 열에 **USMF** 와과 같은 회사 이름을 입력합니다.

## <a name="products-table"></a>제품 테이블

**제품** 테이블의 데이터는 재무 및 운영 앱에서 Customer Engagement 앱으로 한 방향으로 흐르도록 설계되었으므로 초기화가 필요하지 않습니다. 초기 동기화를 실행하여 필요한 모든 데이터를 재무 및 운영 앱에서 Customer Engagement 앱으로 마이그레이션합니다. 자세한 내용은 [초기 동기화에 대한 고려 사항](initial-sync-guidance.md)을 참조하세요.

## <a name="quote-and-quote-product-tables"></a>견적 및 견적 제품 테이블

**견적** 테이블의 경우 이 토픽 앞부분의 [주문 테이블](#order-table) 섹션의 안내를 참조하세요. **제품 견적** 테이블의 경우 [제품 주문 테이블](#order-products-table) 섹션의 안내를 참조하세요.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
