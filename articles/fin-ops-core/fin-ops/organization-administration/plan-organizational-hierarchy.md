---
title: 조직 계층 구조 계획
description: 조직 및 조직 계층을 설정하기 전에 비즈니스를 가장 잘 모델링하는 방법을 알아야 합니다.
author: sericks007
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMLegalEntity, OMOperatingUnit
audience: Application User
ms.reviewer: sericks
ms.custom: 17404
ms.assetid: babde0c6-bb5d-45ae-95ca-2af75a0ea292
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef906c0d60639da763f2a9c1e1adf508b0849b8978dff17cd0e7b3936fc4779e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460993"
---
# <a name="plan-your-organizational-hierarchy"></a>조직 계층 구조 계획

[!include [banner](../includes/banner.md)]

조직 및 조직 계층을 설정하기 전에 비즈니스 모델링 방법을 계획해야 합니다. 조직 모델은 구현 및 비즈니스 프로세스에 상당한 영향을 미칩니다.

조직 계층은 비즈니스를 구성하는 조직 간의 관계를 나타냅니다. 따라서 조직을 모델링할 때 가장 중요한 고려 사항은 비즈니스 구조입니다. 재무 및 회계, 인사, 운영, 구매, 판매 및 마케팅과 같은 기능 영역의 임원 및 고위 관리자의 피드백을 기반으로 조직 구조를 정의하는 것이 좋습니다.

계층 구조를 계획할 때 조직 계층 구조와 재무 차원 간의 관계를 고려하는 것도 중요합니다. 여러 조직 계층을 설정하여 비즈니스의 다양한 보기를 나타낼 수 있습니다. 재무 차원을 사용하여 이러한 보기를 기반으로 보고서를 만들 수 있습니다. 파트너와 협력하여 조직 및 법적 보고 요구 사항을 모두 해결하는 계층 구조를 만드세요.

> [!NOTE]
> 재무 차원을 사용하여 법인을 만들지 않고도 법인을 나타낼 수 있지만 재무 차원은 법인의 운영 또는 비즈니스 요구 사항을 해결하도록 설계되지 않았습니다. 단위 간 회계 기능은 각 거래로 생성된 회계 항목만 처리하도록 설계되었습니다.

> [!IMPORTANT]
> 이 기사의 정보만을 기반으로 조직을 모델링하는 방법을 결정해서는 안 됩니다. 이 문서는 가이드입니다. 추가 지침을 위해 파트너와 협력할 수 있습니다. 귀하의 파트너는 다양한 산업 및 고객 기반에서 경험을 쌓았습니다.

## <a name="decide-whether-to-model-internal-organizations-as-legal-entities-or-operating-units"></a>내부 조직을 법인 또는 운영 단위로 모델링할지 결정

비즈니스를 대표할 법인이 하나 이상 있어야 합니다. 법인은 법적 계약을 체결할 수 있으며 성과에 대해 보고하는 재무제표를 준비해야 합니다.

법인은 거래 비즈니스 또는 통합에 사용할 수 있습니다. 이는 재무 및 운영의 법인이 반드시 귀하의 비즈니스에서 실제 법인을 대표하는 것은 아님을 의미합니다. 예를 들어, 거래에 참여하는 회사는 자회사 법인을 소유할 수 있습니다. 이 시나리오에서는 거래에 법인이 필요하고 자회사 법인의 결과와 잔액을 통합하기 위해 가상 법인이 필요합니다.

지역 사무소와 같은 비즈니스의 내부 조직은 추가 법인 또는 주요 법인의 운영 단위로 나타낼 수 있습니다. 운영 단위는 법적으로 정의된 조직일 필요가 없습니다. 운영 단위는 비즈니스의 경제적 자원과 운영 프로세스를 제어하는 데 사용됩니다. 예를 들어 부서와 비용 센터는 운영 단위입니다.

일부 기능은 조직이 법인인지 운영 단위인지에 따라 다르게 작동합니다. 결정을 내릴 때 아래에 설명된 기능을 신중하게 고려하세요.

### <a name="master-data"></a>마스터 데이터

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

고객, 지불 조건, 세무 당국 및 사이트별 주식 주문과 같은 일부 마스터 데이터는 각 법인에 대해 설정되어야 합니다. 사용자, 제품 및 대부분의 인적 자원 데이터와 같은 일부 마스터 데이터는 모든 법인 간에 공유됩니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

마스터 데이터는 운영 단위 간에 공유됩니다.

### <a name="module-parameters"></a>모듈 매개 변수

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

미수금 매개변수, 미지급금 매개변수, 현금 및 은행 관리 매개변수와 같은 모듈 매개변수는 법인별로 설정해야 합니다. 법인에 대한 모듈 설정이 별개이기 때문에 각 자회사는 현지 법적 요구 사항 및 비즈니스 관행을 준수할 수 있습니다. 예를 들어, 전문 서비스 법인과 제조 법인은 동일한 모회사에 보고하더라도 서로 다른 모듈 매개변수를 가질 수 있습니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

모듈 매개변수는 운영 단위 간에 공유됩니다.

### <a name="data-security"></a>데이터 보안

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

대부분의 데이터는 회사 ID에 의해 자동으로 보호됩니다. 회사 ID는 법인과 연결된 데이터의 고유 식별자입니다. 회사는 하나의 법인에만 연결할 수 있고 법인은 하나의 회사에만 연결할 수 있습니다. 사용자는 액세스 권한이 있는 회사의 데이터에만 액세스할 수 있습니다. 회사 ID별로 데이터를 보호하기 위해 사용자 정의할 필요가 없습니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

맞춤형 데이터 보안 정책을 생성하여 운영 단위별로 데이터를 보호할 수 있습니다. 데이터 보안 정책은 데이터에 대한 액세스를 제한하는 데 사용됩니다. 예를 들어, 사용자가 특정 운영 단위에서만 구매 주문을 생성할 수 있다고 가정합니다. 사용자가 다른 운영 단위의 구매 주문 데이터에 액세스하지 못하도록 데이터 보안 정책을 생성할 수 있습니다. 트랜잭션의 양과 보안 정책의 수는 성능에 영향을 줄 수 있습니다. 보안 정책을 설계할 때 성능을 염두에 두세요.

### <a name="ledgers"></a>원장

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

각 법인에는 계정과목표, 회계 통화, 보고 통화 및 회계 달력을 제공하는 원장이 필요합니다. 대차 대조표는 법인에 대해서만 생성할 수 있습니다. 기본 계정, 차원, 계정 구조, 계정 코드집 및 계정 규칙은 둘 이상의 법인에서 사용할 수 있습니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

운영 단위는 자체 원장 정보를 가질 수 없습니다. 내부 조직에 고유한 원장이 필요하지 않은 경우 운영 단위로 모델링할 수 있습니다. 원장 정보는 계층의 상위 법인에 대해 설정됩니다. 손익계산서는 법인 내의 운영 단위 또는 모회사에 대해 생성할 수 있습니다.

### <a name="fiscal-calendars"></a>회계 캘린더

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

각 법인에는 자체 회계 달력이 있습니다. 내부 조직에서 다른 회계 연도와 회계 달력을 사용하는 경우 조직을 법인으로 모델링해야 합니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

운영 단위는 회계 달력을 공유해야 합니다. 내부 조직에서 동일한 회계 연도와 회계 달력을 사용하는 경우 조직을 운영 단위로 모델링해야 합니다.

### <a name="consolidation"></a>연결

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

재무제표를 작성하려면 지역 사무소의 재무 결과를 하나의 통합 회사로 통합해야 합니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

데이터가 이미 운영 단위 간에 공유되기 때문에 통합이 필요하지 않습니다.

### <a name="centralized-payments"></a>중앙 집중형 지불

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

모든 하위 법인에 대한 인보이스가 단일 상위 법인과 주고받을 수 있도록 중앙 집중식 결제를 설정해야 합니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

모든 송장이 단일 법인에 기록되기 때문에 중앙 집중식 지불이 필요하지 않습니다.

### <a name="intercompany-transactions"></a>회사간 거래

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

내부 거래 판매 주문, 구매 주문, 지불 또는 영수증을 서로 적용할 수 있습니다. 저널 바우처를 사용할 필요는 없습니다. 보조원장 수준(미수금, 미지급금)에서 본지사 거래를 조회할 수 있습니다. 다음 예는 내부 거래 트랜잭션이 처리되는 방법을 보여줍니다.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>예 1: 본사는 지역 사무소에 서비스를 제공하고 해당 서비스 비용을 지역 사무소에 청구해야 합니다.

지역 사무소를 법인으로 모델링하는 경우 다음과 같은 옵션이 있습니다.

- 본사는 비용에 대해 지역 사무소를 상호 청구하기 위해 분개 항목을 생성합니다. 거래를 에이징할 수 없습니다.
- 본사는 서비스에 대한 구매 주문서를 지역 사무소로 보냅니다. 회사 간 보조 원장 거래와 함께 지역 사무소의 법인에서 판매 주문이 자동으로 생성됩니다.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>예 2: 본사가 지역 사무소에 제공되는 서비스를 조달하고 비용을 지불합니다.

지역 사무소를 법인으로 모델링하는 경우 다음과 같은 옵션이 있습니다.

- 청구서 및 지불은 본사의 규정 요구 사항을 따릅니다. 본사는 비용에 대해 지역 사무소를 상호 청구하기 위해 분개 항목을 생성할 수 있습니다. 거래를 에이징할 수 없습니다.
- 청구서 및 지불은 본사의 규정 요구 사항을 따릅니다. 본사는 본지사 보조원장 거래를 생성할 수 있습니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

운영 단위 간의 본지사 거래는 분개장을 통해서만 지원됩니다. 운영 단위는 동일한 법인의 다른 운영 단위에서 구매 주문, 판매 주문 또는 송장을 발행하거나 받을 수 없습니다. 보조원장 수준(미수금, 미지급금)에서 본지사 거래를 조회할 수 없습니다. 다음 예는 내부 거래 트랜잭션이 처리되는 방법을 보여줍니다.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>예 1: 본사는 지역 사무소에 서비스를 제공하고 해당 서비스 비용을 지역 사무소에 청구해야 합니다.

지역 사무소를 운영 단위로 모델링하면 본사에서 비용 거래를 입력하고 이를 지역 사무소에 코드화합니다.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>예 2: 본사가 지역 사무소에 제공되는 서비스를 조달하고 비용을 지불합니다.

지역 사무소를 운영 단위로 모델링하는 경우 송장 및 지불은 본사의 규정 요구 사항을 따릅니다. 청구서는 지역 사무소로 코딩할 수 있습니다. 손익 계산서에서 균형 재정 차원을 사용하여 지역 사무소의 비용을 보고합니다.

### <a name="local-tax-requirements"></a>지방세 요건

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

법인은 법인이 등록된 국가/지역의 세무당국 세법의 적용을 받습니다. 예를 들어, 덴마크에 등록된 법인은 덴마크 세법 및 규정의 적용을 받습니다. 법인은 하나의 국가/지역에만 속할 수 있습니다. 법인의 기본 주소로 선택한 국가/지역은 해당 법인에서 사용할 수 있는 국가/지역별 기능을 제어합니다. 예를 들어 법인의 기본 주소가 덴마크인 경우 덴마크 세법 및 규정과 관련된 기능을 사용할 수 있습니다. 따라서 조직이 다른 국가/지역에 있고 다른 지방세 옵션이 필요한 경우 조직을 별도의 법인으로 설정해야 합니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

운영 단위는 모법인의 국가 컨텍스트를 사용합니다. 동일한 법인의 운영 단위는 다른 국가/지역별 요구 사항을 가질 수 없습니다. 조직이 동일한 국가/지역에 있고 동일한 세금 옵션을 사용하는 경우 운영 단위로 설정할 수 있습니다.

### <a name="statutory-reporting-for-a-countryregion"></a>국가/지역에 대한 법적 보고

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

지원되는 국가/지역의 경우 대부분의 법정 보고서를 생성할 수 있습니다. 

> [!NOTE]
> 총계정 원장의 전기 레이어를 사용하면 하위 회사와 다른 회계 표준을 사용하는 모회사에 조정 항목을 만들 수 있습니다. 예를 들어 영국(UK GAAP)에서 일반적으로 인정되는 회계 관행을 사용하는 회사의 경우 전기 레이어에서 조정 항목을 만들 수 있습니다. 이러한 항목은 미국에서 일반적으로 인정되는 회계 원칙(GAAP)을 사용하는 모회사로 통합될 수 있습니다. 조정 항목은 UK GAAP 보고에 영향을 미치지 않습니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

법정 보고서는 다른 애플리케이션을 사용하여 생성해야 합니다. 각 운영 단위의 요구 사항을 지원하기 위해 재무 및 운영 앱에서 데이터가 캡처되는지 확인해야 합니다. 이러한 요구 사항은 본사 요구 사항과 다릅니다.

### <a name="currency"></a>통화

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

내부 조직에서 다른 기능 통화를 사용해야 하는 경우 조직을 법인으로 모델링해야 합니다. 기능 통화는 법인별로 설정됩니다. 그러나 여러 통화로 거래를 입력할 수 있습니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

조직에서 단일 기준 통화를 사용할 수 있는 경우 조직을 운영 단위로 모델링할 수 있습니다. 운영 단위는 기능 통화를 공유해야 합니다. 그러나 여러 통화로 거래를 입력하고 보고서를 만들 수 있습니다.

### <a name="year-end-closing"></a>연말 마감

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

조직이 위치한 국가/지역마다 법률 및 회계 관행이 다른 경우 조직마다 다른 연말정산 절차가 필요할 수 있습니다. 이는 조직을 법인으로 모델링해야 함을 의미합니다. 각 법인에는 자체 연말 절차가 있습니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

조직이 위치한 국가/지역마다 법률 및 회계 관행이 같은 경우 단일 연말정산 절차를 사용할 수 있습니다. 이는 조직을 운영 단위로 모델링할 수 있음을 의미합니다. 모든 운영 단위는 동일한 연말 결산 절차를 사용해야 합니다.

### <a name="number-sequences"></a>번호 시퀀스

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

일부 참조의 번호 시퀀스는 법인별로 설정할 수 있습니다. 일부 숫자 시퀀스는 공유할 수 있습니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

일부 참조의 운영 단위 시퀀스는 법인별로 설정할 수 있습니다. 일부 숫자 시퀀스는 공유할 수 있습니다.

### <a name="products"></a>제품

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

제품 정의는 공유되며 거래에 포함되기 전에 개별 법인에 릴리스되어야 합니다. 각 법인에는 거래 문서에 포함될 수 있는 자체 출시 제품 세트가 있습니다. 내부 조직에서 다른 제품 세트를 사용해야 하는 경우 조직을 법인으로 모델링해야 합니다.

> [!NOTE]
> 제품 정의가 공유되더라도 제품이 출시된 각 법인에서 각 인벤토리 사이트의 항목에 대해 다른 판매, 구매 및 재고 매개변수를 지정할 수 있습니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

모든 운영 단위는 동일한 제품 세트를 공유합니다. 내부 조직에서 동일한 제품 세트를 공유하는 경우 조직을 운영 단위로 모델링해야 합니다.

### <a name="inquiry-and-reporting"></a>문의 및 보고

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>조직이 법인으로 모델링된 경우

여러 법인에서 거래를 입력하고 조회를 수행하려면 회사를 수동으로 변경해야 합니다. 데이터 보안 경계로 인해 통합 조회 및 보고는 리소스 집약적이고 시간이 많이 소요될 수 있습니다.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>조직을 운영 단위로 모델링한 경우

여러 운영 단위의 데이터에 액세스하기 위해 회사를 변경할 필요가 없습니다. 통합 조회 및 보고, 개별 지역 조회가 보다 쉽고 빠릅니다.

## <a name="best-practices-for-modeling-organizations-and-hierarchies"></a>조직 및 계층 모델링을 위한 모범 사례

조직 계층을 구현할 때 다음 모범 사례를 고려하세요.

- 법인과 사업부 간의 교차를 모델링할 부서를 만듭니다. 그런 다음 법정 보고를 위해 부서에서 법인으로 데이터를 롤업하고 내부 보고를 위해 부서에서 사업부로 데이터를 롤업할 수 있습니다. 부서는 수익 센터 역할을 할 수 있습니다. 부서를 사용하는 경우 계정 구조에서 법인 및 사업부를 차원으로 사용할 필요가 없습니다. 부서만 차원으로 사용할 수 있습니다. 그러나 비용 센터가 비용 누산기로만 사용되고 부서가 수익 인식에 사용되는 경우 비용 센터와 부서를 모두 계정 구조의 차원으로 사용해야 합니다.
- 손익 보고에 대한 복잡한 요구 사항이 있는 경우 운영 단위에 대한 다중 계층을 모델링합니다.
- 단일 법인에서 동일한 계층 목적을 위해 여러 계층을 모델링하지 마세요.
- 모든 목적을 위해 계층 구조를 만들지 마세요. 일반적으로 여러 목적으로 하나의 계층을 사용할 수 있습니다. 예를 들어, 하나의 운영 단위 계층이 모든 정책 관련 목적에 할당될 수 있습니다.
- 균형 잡힌 계층 구조를 만듭니다. 계층 구조에서 루트 노드에서 동일한 거리에 있는 모든 노드는 레벨로 정의됩니다. 균형 잡힌 계층 구조에서는 각 수준에서 한 가지 유형의 운영 단위만 발생할 수 있으며 루트 노드에서 각 수준까지의 거리는 일정합니다. 부서와 법인 또는 사업부 사이에 중간 수준이 있는 경우 자리 표시자 조직은 균형 잡힌 계층 구조를 만들어야 할 수 있습니다.
- 법인 구조가 운영 구조이기도 한 경우 별도의 운영 단위 계층을 모델링하지 마세요. 법인과 운영 단위의 혼합 계층 구조는 두 가지 목적을 모두 수행할 수 있습니다.
- 주요 구조 조정 시나리오를 모델링하기 전에 계층의 유효 날짜를 사용하여 영향 분석 및 검증 테스트를 수행하세요.
- 프로덕션 환경에서 새 버전을 게시하기 전에 드래프트 모드를 사용하여 계층 구조를 변경합니다.
- 프로덕션 환경의 계층 구조에서 조직을 추가하거나 제거할 수 있는 권한이 있는 사람의 수를 제한합니다. 숫자가 작을수록 값비싼 실수가 발생하고 수정해야 할 가능성이 줄어듭니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
