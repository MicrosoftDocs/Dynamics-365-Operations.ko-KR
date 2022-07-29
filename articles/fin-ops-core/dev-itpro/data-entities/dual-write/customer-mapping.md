---
title: 통합 고객 마스터
description: 이번에는 재무 및 운영 Dataverse 간의 고객 데이터 통합 및 에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 41e4b6c192b6125a144e4d5ef952ba0975821d44
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460816"
---
# <a name="integrated-customer-master"></a>통합 고객 마스터

[!include [banner](../../includes/banner.md)]



고객 데이터는 둘 이상의 Dynamics 365 애플리케이션에서 마스터할 수 있습니다. 예를 들어 고객 행은 Dynamics 365 Sales(고객 참여 앱)의 판매 활동을 통해 시작될 수 있고 행은 Dynamics 365 Commerce(재무 및 운영 앱) 소매 활동을 통해 시작될 수 있습니다. 고객 데이터의 출처가 어디이든 상관없이 배후에서 통합됩니다. 통합 고객 마스터는 모든 Dynamics 365 애플리케이션에서 고객 데이터를 마스터할 수 있는 유연성을 제공하고 Dynamics 365 애플리케이션 제품군 전반에 걸쳐 고객에 대한 포괄적인 보기를 제공합니다.

## <a name="customer-data-flow"></a>고객 데이터 흐름

*고객* 은 애플리케이션에서 잘 정의된 개념입니다. 따라서 고객 데이터의 통합에는 두 애플리케이션 간의 고객 개념을 조화시키는 것만 포함됩니다. 다음 그림은 고객 데이터 흐름을 보여줍니다.

![고객 데이터 흐름.](media/dual-write-customer-data-flow.png)

고객은 크게 상업/조직 고객과 소비자/최종 사용자의 두 가지 유형으로 분류할 수 있습니다. 이 두 가지 유형의 고객은 재무 및 운영 및 Dataverse에서 다르게 저장되고 처리됩니다.

재무 및 운영에서 상업/조직 고객과 소비자/최종 사용자는 모두 **CustTable**(CustCustomerV3Entity)이라는 단일 테이블에서 마스터되며 **유형** 속성을 기반으로 분류됩니다. (**유형** 이 **조직** 으로 설정되면 고객은 상업/조직 고객이고 **유형** 이 **개인** 으로 설정되면 고객은 소비자/최종 사용자입니다.) 기본 담당자 정보는 SMMContactPersonEntity 테이블을 통해 처리됩니다.

Dataverse에서 상업/조직 고객은 계정 테이블에서 마스터되며 **관계 유형** 속성이 **고객** 으로 설정될 때 고객으로 식별됩니다. 소비자/최종 사용자 및 담당자는 모두 Contact 테이블로 표시됩니다. 소비자/최종 사용자와 담당자를 명확하게 구분하기 위해 **Contact** 테이블에는 **Sellable** 이라는 부울 플래그가 있습니다. **Sellable** 이 **True** 인 경우 연락처는 소비자/최종 사용자이며 해당 연락처에 대한 견적 및 주문을 생성할 수 있습니다. **Sellable** 이 **False** 인 경우 연락처는 고객의 기본 연락처입니다.

판매 불가 연락처가 견적 또는 주문 프로세스에 참여하면 **Sellable** 이 **True** 로 설정되어 연락처를 판매 가능 연락처로 플래그 지정합니다. 판매 가능 연락처가 된 연락처는 판매 가능 연락처로 남아 있습니다.

## <a name="templates"></a>템플릿

고객 데이터에는 고객 그룹, 주소, 연락처 정보, 지급 프로필, 송장 프로필 및 충성도 상태와 같은 고객에 대한 모든 정보가 포함됩니다. 테이블 맵 컬렉션은 다음 테이블과 같이 고객 데이터 상호 작용 중에 함께 작동합니다.

금융 및 운영 앱 | 고객 참여 앱         | 설명
----------------------------|---------------------------------|------------
[CDS 연락처 V2](mapping-reference.md#115) | 다음 담당자에게 연락해 주십시오. | 이 템플릿은 고객과 공급 업체 모두에 대한 모든 기본, 보조 및 삼차 연락처 정보를 동기화합니다.
[고객 그룹](mapping-reference.md#126) | msdyn_customergroups | 이 템플릿은 고객 그룹 정보를 동기화합니다.
[고객 결제 수단](mapping-reference.md#127) | msdyn_customerpaymentmethods | 이 템플릿은 고객 지급 방법 정보를 동기화합니다.
[고객 V3](mapping-reference.md#101) | 계정 | 이 템플릿은 상업 및 조직 고객에 대한 고객 마스터 정보를 동기화합니다.
[고객 V3](mapping-reference.md#116) | 다음 담당자에게 연락해 주십시오. | 이 템플릿은 소비자와 최종 사용자에 대한 고객 마스터 데이터를 동기화합니다.
[이름 접미사](mapping-reference.md#155) | msdyn_name접두사 | 이 템플릿은 고객과 공급 업체 모두에 대해 이름 접미사 참조 데이터를 동기화합니다.
[지급 일자 라인 CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | 이 템플릿은 고객과 공급 업체 모두에 대한 지급 일자 라인 참조 데이터를 동기화합니다.
[결제일 CDS](mapping-reference.md#158) | msdyn_paymentdays | 이 템플릿은 고객과 공급 업체 모두에 대한 지급 날짜 참조 데이터를 동기화합니다.
[지급 일정 라인](mapping-reference.md#159) | msdyn_payments스케줄라인 | 고객과 공급 업체 모두에 대한 지급 일정 라인 참조 데이터를 동기화합니다.
[지급 일정 :](mapping-reference.md#160) | msdyn_payments스케줄 | 이 템플릿은 고객과 공급 업체 모두에 대한 지급 일정 참조 데이터를 동기화합니다.
[지급 조건](mapping-reference.md#161) | msdyn_paymentterms | 이 템플릿은 고객과 공급 업체 모두에 대한 지급 조건(지급 조건) 참조 데이터를 동기화합니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
