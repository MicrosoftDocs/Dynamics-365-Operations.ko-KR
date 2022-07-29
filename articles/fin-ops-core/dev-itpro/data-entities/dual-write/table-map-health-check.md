---
title: 테이블 맵 상태 확인에 대한 오류 코드
description: 이 항목에서는 테이블 맵 상태 확인의 오류 코드에 대해 설명합니다.
author: nhelgren
ms.date: 10/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: nhelgren
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 916f3cfca3bae7a073ce4e956a12080ee01c8d31
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8461037"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>테이블 맵 상태 확인에 대한 오류 코드

[!include [banner](../../includes/banner.md)]



이 항목에서는 테이블 맵 상태 확인의 오류 코드에 대해 설명합니다.

## <a name="error-100"></a>오류 100

오류 메시지는 "재무 및 운영 권장 사항을 실행하는 데 필요한 최소 재무 및 운영 플랫폼 버전은 PU 43입니다"입니다.

이 기능을 사용하려면 재무 및 운영 앱 버전 10.0.19 이상에 대한 플랫폼 업데이트가 필요합니다.

## <a name="error-400"></a>오류 400

오류 메시지는 "엔티티 \{재무 및 운영 UniqueEntityName\}에 대한 비즈니스 이벤트 등록 데이터가 없으며, 이는 맵이 실행되고 있지 않거나 모든 필드 매핑이 단방향임을 의미합니다."

## <a name="error-500"></a>오류 500

오류 메시지는 "프로젝트 \{프로젝트 이름\}에 대한 프로젝트 구성을 찾을 수 없습니다. 프로젝트가 활성화되지 않았거나 모든 필드 매핑이 고객 참여에서 재무 및 운영으로 단방향일 수 있습니다."

테이블 맵에 대한 매핑을 확인합니다. Customer Engagement 앱에서 재무 및 운영 앱으로 단방향인 경우 재무 및 운영 앱에서 Dataverse로의 실시간 동기화를 위해 트래픽이 생성되지 않습니다.

## <a name="error-900"></a>오류 900

오류 메시지는 "잘못된 소스 필터 \{sourceFilter\} 형식이 엔터티 \{재무 및 운영 UniqueEntityName\}에 있습니다."

재무 및 운영 앱의 테이블 맵에 지정된 소스 필터가 구문상 올바르지 않습니다. 필터 기준을 확인하려면 [라이브 동기화 문제 해결](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps)을 참조하세요.

## <a name="error-1000"></a>오류 1000

오류 메시지는 "이중 쓰기 라이브 동기화에 사용되는 엔티티 \{재무 및 운영 UniqueEntityName\} 쿼리가 \{재무 및 운영 EntityFilterQueryString\}입니다. 쿼리 기준을 충족하는 레코드는 라이브 동기화를 위해 선택됩니다."

반환된 엔터티 쿼리는 엔터티에 대한 지원 SQL 쿼리입니다. 라이브 동기화를 위해 선택되는 비즈니스 데이터를 결정하는 쿼리에서 내부 조인 또는 필터를 확인합니다. 내부 조인 및 필터는 이중 쓰기 라이브 동기화를 위해 선택되는 각 레코드에 대해 충족되어야 하는 필수 조건입니다.

## <a name="error-1300"></a>오류 1300

오류 메시지는 "가상 필드 \{s.EntityFieldName\} 엔터티 \{재무 및 운영 EntityMetadata.EntityProperties.LogicalEntityName\}이 이중 쓰기에 대해 추적되지 않을 수 있습니다."

재무 및 운영 테이블의 가상 필드는 추적에 사용할 수 없습니다. 실시간 동기화는 데이터를 동기화할 수 있지만 열에 적용된 변경 사항을 선택할 수는 없습니다.

## <a name="error-1500"></a>오류 1500

오류 메시지는 "데이터 원본 \{datasource.DataSourceName\}에 대한 추적을 활성화하려면 고객 참여에 대한 비 조회 필드에 매핑된 필드가 하나 이상 있어야 합니다.

엔터티의 데이터 원본에 이중 쓰기에 대해 매핑된 필드가 없습니다. 기본 테이블에 대한 변경 사항은 이중 쓰기에 대해 추적되지 않습니다.

## <a name="error-1600"></a>오류 1600

오류 메시지는 "데이터 소스: \{datasource.DataSourceName\} 엔터티 \{재무 및 운영 EntityMetadata.EntityProperties.LogicalEntityName\}에 범위가 있습니다. 범위 조건을 충족하는 레코드만 아웃바운드에 대해 선택됩니다."

금융 및 운영 앱의 엔터티에는 필터 범위가 활성화된 데이터 원본이 있을 수 있습니다. 이러한 범위는 라이브 동기화의 일부로 선택되는 레코드를 정의합니다. 일부 레코드가 재무 및 운영 앱에서 Dataverse로 건너뛴 경우 레코드가 엔터티의 범위 기준을 충족하는지 확인합니다. 이 검사를 수행하는 간단한 방법은 다음 예제와 유사한 SQL 쿼리를 실행하는 것입니다.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>오류 1700

오류 메시지는 "테이블: \{datasourceTable.Key.subscribedTableName\} 엔터티 \{datasourceTable.Key.entityName\}가 엔티티 \{origTableToEntityMaps.EntityName\}에 대해 추적됩니다. 여러 엔터티에 대해 동일한 테이블을 추적하면 라이브 동기화 트랜잭션의 시스템 성능에 영향을 줄 수 있습니다."

여러 엔터티에서 동일한 테이블을 추적하는 경우 테이블을 변경하면 연결된 엔터티에 대한 이중 쓰기 평가가 트리거됩니다. 필터 절은 유효한 레코드만 보내지만 장기 실행 쿼리 또는 최적화되지 않은 쿼리 계획이 있는 경우 평가에서 성능 문제가 발생할 수 있습니다. 이 문제는 비즈니스 관점에서 피할 수 없습니다. 그러나 여러 엔터티에 교차 테이블이 많은 경우 엔터티를 단순화하거나 엔터티 쿼리에 대한 최적화를 확인하는 것을 고려해야 합니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
