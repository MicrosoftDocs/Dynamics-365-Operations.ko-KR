---
title: 표준 비용과 함께 BOM 계산에 사용되는 정보
description: BOM(자재 명세서) 계산은 여러 출처의 데이터를 사용하여 제조 품목의 표준 비용을 계산합니다. 출처에는 품목, 청구서 라우팅, 간접 비용 계산 공식 및 원가 계산 버전에 대한 정보가 포함됩니다.
author: AndersGirke
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcGroup, BOMCalcTable, ProdParmBOMCalc
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65571
ms.assetid: ca17e6dd-b16a-4bbc-8682-b16345ab9906
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b1aa33c11f7cfbbde2a278bef25189ac697d19
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448792"
---
# <a name="information-used-in-bom-calculations-with-standard-costs"></a>표준 비용과 함께 BOM 계산에 사용되는 정보

[!include [banner](../includes/banner.md)]

BOM(자재 명세서) 계산은 여러 출처의 데이터를 사용하여 제조 품목의 표준 비용을 계산합니다. 출처에는 품목, 청구서 라우팅, 간접 비용 계산 공식 및 원가 계산 버전에 대한 정보가 포함됩니다.

표준 원가 BOM 계산에 사용되는 구매 품목 정보에는 다음이 포함됩니다.
-   비용 − 구매 항목의 비용은 표준 비용에 대한 비용 산정 버전에서 사이트별 비용 레코드로 유지됩니다. 각 비용 레코드에는 유효 날짜가 있으며 BOM 계산 날짜에 따라 사용할 비용 레코드가 결정됩니다. 예를 들어, 미래 계산 날짜가 있는 BOM 계산은 보류 상태와 미래 유효 날짜가 있는 비용 레코드를 사용할 수 있습니다.
-   비용 그룹 − 구매 품목에 할당된 비용 그룹은 제조 품목의 계산된 비용에서 비용 세분화의 기초를 제공합니다.
-   항목의 BOM 계산 그룹에 포함된 경고 조건을 통해 BOM 계산에서 잠재적 문제를 식별할 수 있습니다. 구매한 항목의 비용이 0이거나 BOM의 수량이 0이거나 오래된 비용 레코드가 있는 경우일 수 있습니다. BOM 계산을 시작할 때 적용 가능한 경고 조건을 무시할 수 있습니다.

표준 원가 BOM 계산에 사용되는 제조 품목 정보에는 다음이 포함됩니다.
-   재고에 대한 표준 주문 수량 − 재고에 대한 품목의 표준 주문 수량은 BOM 계산에서 일정 비용을 상각하기 위한 기본 회계 로트 크기 역할을 합니다. 회계 로트 크기는 지정된 경우 주문 수량 배수도 반영합니다.
-   항목의 BOM 계산 그룹에 포함된 경고 조건을 통해 BOM 계산에서 잠재적 문제를 식별할 수 있습니다. 제조 품목에 BOM 또는 경로가 없는 경우를 예로 들 수 있습니다. BOM 계산을 시작할 때 적용 가능한 경고 조건을 무시할 수 있습니다.

표준 원가 BOM 계산에 사용되는 자재 명세서 정보에는 다음이 포함됩니다.
-   BOM 버전 − 제조 품목에 지정된 BOM 버전은 유효 시작일과 종료일, 승인 및 활성 상태를 갖습니다. 청구서 버전은 회사 전체 또는 사이트별로 다를 수 있으며 선택적으로 수량 중단점을 반영할 수 있습니다.
-   BOM 라인 항목 수량 − 구성 요소에는 일반적으로 필요한 가변 수량이 있지만 일정할 수도 있습니다. 구성 요소 수량은 일반적으로 하나의 상위 항목을 생산하기 위해 표시되지만 소수 자릿수 문제를 처리하기 위해 100당 또는 1000당 표시될 수 있습니다. 구성 요소 수량은 측정을 기반으로 계산할 수도 있습니다.
-   BOM 라인 항목 스크랩 - 구성 요소는 계획된 스크랩에 대해 가변 또는 일정 수량을 가질 수 있습니다.
-   BOM 라인 항목 유효 날짜 − 구성 요소는 유효한 시작 날짜와 종료 날짜를 가질 수 있습니다.
-   BOM 라인 품목 생산 유형 − 일정 비용 상각을 위한 원가계산 로트 크기는 BOM 계산 수량과 주문 생산 전개 모드를 반영합니다. BOM 계산은 제조된 구성요소가 표준 주문 수량 대신 정확한 수량으로 생산될 것이라고 가정하기 때문입니다.
-   제조된 구성요소에 대한 하위 BOM − 제조된 구성요소는 BOM 계산에서 항목의 현재 활성 BOM 버전 대신 사용되는 지정된 BOM 버전을 선택적으로 가질 수 있습니다.
-   제조된 구성요소의 하위 경로 − 제조된 구성요소는 BOM 계산에서 항목의 현재 활성 경로 버전 대신 사용되는 지정된 경로 버전을 선택적으로 가질 수 있습니다.
-   작업 번호 및 작업 스크랩 백분율의 영향 - 작업 번호는 구성 요소를 특정 작업에 연결하며 작업에는 스크랩 백분율이 있을 수 있습니다. 연결을 통해 BOM 계산에서 구성품의 필수 수량에 대한 여러 작업의 스크랩 퍼센트 및 누적 스크랩 퍼센트를 설명할 수 있습니다.
-   비용 계산에서 BOM 라인 항목 무시 − BOM 계산을 위해 구성 요소를 무시할 수 있습니다.

표준 원가 BOM 계산에 사용되는 운영 자원 정보는 다음과 같습니다.
-   시간당 비용 − 운영 자원과 관련된 시간당 비용은 시간 및 실행 시간을 설정하기 위해 할당된 비용 범주로 표시됩니다. 리소스 그룹 및 운영 자원에 대해 이러한 비용 범주를 식별해야 합니다. 비용 범주와 연결된 시간당 비용은 사이트별 또는 회사 전체가 될 수 있습니다.
-   단위당 비용 − 일부 제조 환경에서는 출력 단위당 운영 자원 비용을 할당하며, 이는 수량에 대해 다른 비용 범주로 표시됩니다. 예를 들어, 수량 관련 비용은 노동에 대한 조각 비율을 반영하거나 페인트 제조업체는 출력 갤런당 운영 자원 비용을 할당할 수 있습니다.
-   라우팅 작업에 대한 운영 자원 정보 재정의 - 비용 범주에 대한 리소스 정보는 재정의될 수 있는 작업에 의해 상속됩니다. BOM 계산은 공정순서 작업에 지정된 비용 범주 정보를 사용합니다.
-   비용 범주에 대한 비용 그룹 − 비용 범주에 할당된 비용 그룹은 제조 품목의 계산된 비용에서 비용 세분화를 제공합니다. 예를 들어, 다른 비용 그룹을 사용하여 기계 및 노동 또는 설정 및 실행 시간과 관련된 계산된 비용을 분할할 수 있습니다.

표준 원가 BOM 계산에 사용되는 라우트 정보는 다음과 같습니다.
-   라우트 버전 − 제조 품목에 지정된 라우트 버전은 유효 시작일과 종료일, 승인 및 활성 상태를 갖습니다. 라우트 버전은 회사 전체 또는 사이트별로 다를 수 있으며 선택적으로 수량 중단점을 반영할 수 있어야 합니다.
-   라우팅 작업 시간 − 런타임 및 설정 시간에 대한 시간을 지정할 수 있습니다. 시간당 시간은 일반적으로 하나의 상위 항목을 생산하기 위해 표시되지만 소수 자릿수 문제를 처리하기 위해 100당 또는 1000당 표시될 수 있습니다.
-   보조 자원에 대한 라우팅 작업 시간 - 보조 리소스는 기본 리소스와 동일한 작업 번호 및 동일한 라우팅 작업 시간을 갖습니다. 예를 들어 작업에는 기본 리소스로 기계가 필요하고 보조 리소스로 노동과 도구가 필요할 수 있습니다.
-   공정 순서 폐기 비율 − BOM 계산은 여러 작업에 걸친 폐기 비율 및 누적 폐기 비율을 설명합니다. 이는 공정순서에 필요한 시간과 공정 번호에 연결된 구성품에 필요한 수량에 적용됩니다.
-   라우팅 작업에 대한 비용 범주 - 비용 범주에 대한 작업 리소스 정보는 재정의될 수 있는 작업에 의해 상속됩니다. BOM 계산은 공정순서 작업에 지정된 비용 범주 정보를 사용합니다.

표준 원가 BOM 계산에 사용되는 제조 간접비 정보는 다음과 같습니다.
-   추가 요금 − 추가 요금 계산 공식은 인건비와 같은 특정 비용 그룹에 연결된 값의 백분율(예: 100%)을 반영합니다.
-   요금 − 요금 계산 공식은 노동과 같은 특정 비용 그룹에 연결된 단위당 금액(예: 시간당 USD 10.00)을 반영합니다.
-   시간 기반 간접비 대 자재 기반 간접비 − 제조 간접비는 라우팅 작업이나 자재 구성 요소와 관련될 수 있습니다.

표준 원가 BOM 계산에 사용되는 원가 계산 버전 정보는 다음과 같습니다.
-   원가계산 유형 − 원가계산 버전에는 표준 원가가 포함되어야 합니다. 표준 비용을 사용하는 BOM 계산에는 몇 가지 제한 사항이 적용됩니다. 예를 들어, 이러한 제한은 기타 비용이 단가에 포함되어야 하고 BOM 계산 전개 모드가 단일 레벨이어야 함을 지정합니다.
-   필수 대체 원칙 − 원가 계산 버전은 지정된 원가 계산 버전 또는 활성 비용 레코드 사용과 같은 대체 원칙의 사용을 의무화할 수 있습니다. 필수 대체 원칙은 일반적으로 비용 업데이트에 대한 두 가지 버전 접근 방식에서 증분 업데이트를 나타내는 비용 계산 버전에 적용됩니다.
-   보류 중인 비용에 대한 차단 플래그 − 차단 플래그는 제조 품목에 대한 보류 중인 비용의 BOM 계산을 방지할 수 있습니다.
-   지정된 시작 날짜 − 지정된 시작 날짜는 원가계산 버전과 관련된 모든 BOM 계산에 대한 기본 계산 날짜로 작동합니다.
-   지정된 사이트 − 지정된 사이트는 BOM 계산을 단일 사이트로 제한합니다.
-   비용 계산 버전의 내용에는 비용이 포함되어야 합니다. − 내용에는 비용이 포함되어야 합니다. 제조 품목에 대해 제안된 판매 가격을 계산하기 위해 선택적으로 판매 가격을 포함할 수 있습니다.

BOM 계산을 시작할 때 여러 정보 소스를 지정할 수 있습니다. 여기에는 사이트, 계산 날짜 및 원가 계산 버전이 포함됩니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]