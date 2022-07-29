---
title: 이중 쓰기 설정 안내
description: 이번에는 이중 쓰기 설정이 지원되는 시나리오에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 10/12/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6de449b14bcdd82336e3e255bf62ad069d3daaf5
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460819"
---
# <a name="guidance-for-dual-write-setup"></a>이중 쓰기 설정 안내

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



Finance and Operations 환경과 Dataverse 환경 간에 이중 쓰기 연결을 설정할 수 있습니다.

+ **재무 및 운영 환** 경은 **재무 및 운영 앱**(예: Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce 및 Dynamics 365 Human Resources)을 위한 기본 플랫폼을 제공합니다.
+ **Dataverse 환경** 은 **고객 참여 앱**(Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing Dynamics 365 Project Service Automation 등)을 위한 기본 플랫폼을 제공합니다.

> [!IMPORTANT]
> Dynamics 365 Finance의 인사 모듈은 이중 쓰기 연결을 지원하지만 Dynamics 365 Human Resources 앱은 지원하지 않습니다.

설정 메커니즘은 구독 및 환경에 따라 다릅니다.

+ 재무 및 운영 앱의 새 인스턴스의 경우 이중 쓰기 연결 설정은 Microsoft Dynamics LCS(Lifecycle Services)에서 시작됩니다. Microsoft Power Platform에 대한 라이선스가 있는 경우 테넌트에 라이선스가 없으면 새 Dataverse 환경이 제공됩니다.
+ 기존 인스턴스 재무 및 운영 앱의 경우 이중 쓰기 연결 설정은 재무 및 운영 환경에서 시작됩니다.

엔터티에서 이중 쓰기를 시작하기 전에 초기 동기화를 실행하여 양쪽에서 기존 데이터를 처리할 수 있습니다. 재무 및 운영 앱과 고객 참여 앱. 두 환경 간에 데이터를 동기화할 필요가 없는 경우 초기 동기화를 건너뛸 수 있습니다.

초기 동기화를 사용하면 기존 데이터를 한 앱에서 다른 앱으로 양방향으로 복사할 수 있습니다. 이미 있는 환경과 해당 환경의 데이터 유형에 따라 몇 가지 설정 시나리오가 있습니다.

다음 설정 시나리오가 지원됩니다.

+ [새로운 재무 및 운영 앱 인스턴스 및 새로운 고객 참여 앱 인스턴스](#new-new)
+ [새로운 재무 및 운영 앱 인스턴스 및 기존 고객 참여 앱 인스턴스](#new-existing)
+ [데이터가 있는 새로운 재무 및 운영 앱 인스턴스와 새로운 고객 참여 앱 인스턴스](#new-data-new)
+ [데이터와 기존 고객 참여 앱 인스턴스가 있는 새로운 재무 및 운영 앱 인스턴스](#new-data-existing)
+ [기존 재무 및 운영 앱 인스턴스 및 새로운 고객 참여 앱 인스턴스](#existing-new)
+ [기존 재무 및 운영 앱 인스턴스 및 기존 고객 참여 앱 인스턴스](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>새로운 재무 및 운영 앱 인스턴스 및 새로운 고객 참여 앱 인스턴스

데이터가 없는 재무 및 운영 앱의 새 인스턴스와 고객 참여 앱의 새 인스턴스 간에 이중 쓰기 연결을 설정하려면 Lifecycle Services에서 [이중 쓰기 설정](lcs-setup.md)의 단계를 따르십시오. 연결 설정이 완료되면 다음 작업이 자동으로 발생합니다.

- 비어 있는 새로운 재무 및 운영 환경이 프로비저닝됩니다.
- CRM 프라임 솔루션이 설치된 빈 고객 참여 앱의 새 인스턴스가 프로비저닝됩니다.
- DAT 회사 데이터에 대해 이중 쓰기 연결이 설정됩니다.
- 라이브 동기화를 위해 테이블 맵이 활성화됩니다.

그러면 두 환경 모두 라이브 데이터 동기화를 위한 준비가 됩니다.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>새로운 재무 및 운영 앱 인스턴스 및 기존 고객 참여 앱 인스턴스

데이터가 없는 재무 및 운영 앱의 새 인스턴스와 고객 참여 앱의 기존 인스턴스 간에 이중 쓰기 연결을 설정하려면 Lifecycle Services에서 [이중 쓰기 설정](lcs-setup.md)의 단계를 따르십시오. 연결 설정이 완료되면 다음 작업이 자동으로 발생합니다.

- 비어 있는 새로운 재무 및 운영 환경이 프로비저닝됩니다.
- DAT 회사 데이터에 대해 이중 쓰기 연결이 설정됩니다.
- 라이브 동기화를 위해 테이블 맵이 활성화됩니다.

그러면 두 환경 모두 라이브 데이터 동기화를 위한 준비가 됩니다.

기존 Dataverse 데이터를 재무 및 운영 앱과 동기화하려면 다음 단계를 따르십시오.

1. 재무 및 운영 앱에서 새 회사를 만드십시오.
2. 이중 쓰기 연결 설정에 회사를 추가합니다.
3. 세 글자로 된 ISO(International Organization for Standardization) 회사 코드를 사용하여 Dataverse 데이터를 [부트스트랩](bootstrap-company-data.md)합니다.
4. 데이터를 동기화하려는 테이블에 대해 **초기 동기화** 함수를 실행합니다.

예시 및 대체 접근 방식에 대한 링크는 이 항목 뒷부분의 [예시](#example) 섹션을 참조하십시오.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>데이터가 있는 새로운 재무 및 운영 앱 인스턴스와 새로운 고객 참여 앱 인스턴스

데이터가 있는 금융 및 운영 앱의 새 인스턴스와 고객 참여 앱의 새 인스턴스 간에 이중 쓰기 연결을 설정하려면 [새 금융 및 운영 앱 인스턴스와 새 고객 참여 앱 인스턴스](#new-new)의 단계를 따르십시오. 이 항목의 앞부분에 있는 섹션을 참조하십시오. 연결 설정이 완료되면 데이터를 고객 참여 앱과 동기화하려면 다음 단계를 따르십시오.

1. LCS 페이지에서 재무 및 운영 앱을 열고 로그인한 다음 **데이터 관리 \> 이중 쓰기** 로 이동합니다.
2. 데이터를 동기화하려는 테이블에 대해 **초기 동기화** 함수를 실행합니다.

예시 및 대체 접근 방식에 대한 링크는 [예시](#example) 섹션을 참조하십시오.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>데이터와 기존 고객 참여 앱 인스턴스가 있는 새로운 재무 및 운영 앱 인스턴스

데이터가 있는 재무 및 운영 앱의 새 인스턴스와 고객 참여 앱의 기존 인스턴스 간에 이중 쓰기 연결을 설정하려면 [새 재무 및 운영 앱 인스턴스와 기존 고객 참여 앱 인스턴스](#new-existing)의 단계를 따르십시오. 이 항목의 앞부분에 있는 섹션을 참조하십시오. 연결 설정이 완료되면 데이터를 고객 참여 앱과 동기화하려면 다음 단계를 따르십시오.

1. LCS 페이지에서 재무 및 운영 앱을 열고 로그인한 다음 **데이터 관리 \> 이중 쓰기** 로 이동합니다.
2. 데이터를 동기화하려는 테이블에 대해 **초기 동기화** 함수를 실행합니다.

기존 Dataverse 데이터를 재무 및 운영 앱과 동기화하려면 다음 단계를 따르십시오.

1. 재무 및 운영 앱에서 새 회사를 만드십시오.
2. 이중 쓰기 연결 설정에 회사를 추가합니다.
3. 3자리 ISO 회사 코드를 사용하여 Dataverse 데이터를 [부트스트랩](bootstrap-company-data.md)합니다.
4. 데이터를 동기화하려는 테이블에 대해 **초기 동기화** 함수를 실행합니다.

예시 및 대체 접근 방식에 대한 링크는 [예시](#example) 섹션을 참조하십시오.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>기존 재무 및 운영 앱 인스턴스 및 새로운 고객 참여 앱 인스턴스

재무 및 운영 앱의 기존 인스턴스와 고객 참여 앱의 새 인스턴스 간의 이중 쓰기 연결 설정은 재무 및 운영 환경에서 발생합니다.

1. [재무 및 운영 앱에서 연결을 설정합니다](enable-dual-write.md).
2. 데이터를 동기화하려는 테이블에 대해 **초기 동기화** 함수를 실행합니다.

예시 및 대체 접근 방식에 대한 링크는 [예시](#example) 섹션을 참조하십시오.

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>기존 재무 및 운영 앱 인스턴스 및 기존 고객 참여 앱 인스턴스

재무 및 운영 앱의 기존 인스턴스와 고객 참여 앱의 기존 인스턴스 간의 이중 쓰기 연결 설정은 재무 및 운영 환경에서 발생합니다.

1. [재무 및 운영 앱에서 연결을 설정합니다](enable-dual-write.md).
2. 기존 Dataverse 데이터를 재무 및 운영 앱과 동기화하려면 3자리 ISO 회사 코드를 사용하여 Dataverse 데이터를 [부트스트랩](bootstrap-company-data.md)합니다.
3. 데이터를 동기화하려는 테이블에 대해 **초기 동기화** 함수를 실행합니다.

예시 및 대체 접근 방식에 대한 링크는 [예시](#example) 섹션을 참조하십시오.

## <a name="example"></a>예시

예는 [고객 V3 활성화 - 연락처 테이블 맵](enable-entity-map.md#enable-table-map)을 참조하십시오.

초기 동기화를 실행해야 하는 각 엔터티의 데이터 볼륨을 기반으로 하는 대체 접근 방식은 [초기 동기화 고려 사항](initial-sync-guidance.md)을 참조하십시오.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]