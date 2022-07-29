---
title: 통합 공급업체 마스터
description: 이 항목에서는 금융 및 운영 앱과 Dataverse 간의 공급업체 데이터 통합에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 7794f33aed7364b76a7d5ffd08a068342887e468
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460898"
---
# <a name="integrated-vendor-master"></a>통합 공급업체 마스터

[!include [banner](../../includes/banner.md)]



*공급업체* 라는 용어는 기업에 상품이나 서비스를 공급하는 공급업체 조직 또는 개인 사업자를 나타냅니다. *공급업체* 는 Microsoft Dynamics 365 Supply Chain Management에서 확립된 개념이지만 Customer Engagement 앱에는 공급업체 개념이 없습니다. 그러나 **계정/연락처** 테이블을 오버로드하여 공급업체 정보를 저장할 수 있습니다. 통합 공급업체 마스터는 Customer Engagement 앱에 명시적인 공급업체 개념을 도입합니다. 새 공급업체 디자인을 사용하거나 공급업체 데이터를 **계정/연락처** 테이블에 저장할 수 있습니다. 이중 쓰기는 두 가지 접근 방식을 모두 지원합니다.

두 접근 방식 모두에서 공급업체 데이터는 Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service 및 Power Apps 포털 간에 통합됩니다. Supply Chain Management에서 데이터는 구매 요청 및 구매 주문과 같은 워크플로우에 사용할 수 있습니다.

## <a name="vendor-data-flow"></a>공급업체 데이터 흐름

Dataverse의 **계정/연락처** 테이블에 공급업체 데이터를 저장하지 않으려면 새로운 공급업체 디자인을 사용할 수 있습니다.

![공급업체 데이터 흐름.](media/dual-write-vendor-data-flow.png)

**계정/연락처** 테이블에 공급업체 데이터를 계속 저장하려면 확장된 공급업체 디자인을 사용할 수 있습니다. 확장된 공급업체 디자인을 사용하려면 이중 쓰기 솔루션 패키지에서 공급업체 워크플로를 구성해야 합니다. 자세한 내용은 [공급업체 설계 간에 전환](vendor-switch.md)을 참조하세요.

![확장된 공급업체 데이터 흐름.](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Power Apps 포털을 셀프 서비스 공급업체에 사용하는 경우 공급업체 정보는 재무 및 운영 앱으로 직접 흐를 수 있습니다.

## <a name="templates"></a>템플릿

공급업체 데이터에는 공급업체 그룹, 주소, 연락처 정보, 지불 프로필 및 송장 프로필과 같은 공급업체에 대한 모든 정보가 포함됩니다. 다음 표와 같이 공급업체 데이터 상호 작용 중에 함께 작동하는 테이블 맵 모음입니다.

금융 및 운영 앱 | Customer Engagement 앱     | 설명
----------------------------|-----------------------------|------------
[CDS 연락처 V2](mapping-reference.md#115) | 연락처 | 이 템플릿은 고객과 공급 업체 모두에 대한 모든 기본, 보조 및 삼차 연락처 정보를 동기화합니다.
[이름 접미사](mapping-reference.md#155) | msdyn_nameaffixes | 이 템플릿은 고객과 공급 업체 모두에 대해 이름 접미사 참조 데이터를 동기화합니다.
[지급 일자 라인 CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | 이 템플릿은 고객과 공급 업체 모두에 대한 지급 일자 라인 참조 데이터를 동기화합니다.
[지불일 CDS](mapping-reference.md#158) | msdyn_paymentdays | 이 템플릿은 고객과 공급 업체 모두에 대한 지급 날짜 참조 데이터를 동기화합니다.
[지불 일정 라인](mapping-reference.md#159) | msdyn_paymentschedulelines | 고객과 공급 업체 모두에 대한 지급 일정 라인 참조 데이터를 동기화합니다.
[지불 일정](mapping-reference.md#160) | msdyn_paymentschedules | 이 템플릿은 고객과 공급 업체 모두에 대한 지급 일정 참조 데이터를 동기화합니다.
[지불 조건](mapping-reference.md#161) | msdyn_paymentterms | 이 템플릿은 고객과 공급 업체 모두에 대한 지급 조건(지급 조건) 참조 데이터를 동기화합니다.
[공급업체 V2](mapping-reference.md#202) | msdyn_vendors | 공급업체를 위한 맞춤형 솔루션을 사용하는 기업은 금융 및 운영 앱 통합이므로 Dataverse에 도입되는 기본 개념을 활용할 수 있습니다.
[공급업체 그룹](mapping-reference.md#200) | msdyn_vendorgroups | 이 템플릿은 공급업체 그룹 정보를 동기화합니다.
[공급업체 결제 방법](mapping-reference.md#201) | msdyn_vendorpaymentmethods | 이 템플릿은 공급업체 결제 방법 정보를 동기화합니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
