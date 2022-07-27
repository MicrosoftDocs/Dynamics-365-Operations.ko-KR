---
title: 회계 소스 탐색기
description: 이 문서에서는 총계정원장 회계 항목 이면의 소스 정보에 대한 자세한 분석에 사용할 수 있는 회계 소스 탐색기에 대한 정보를 제공합니다.
author: rcarlson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: roschlom
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ab098aa36d6fa6c34beaaa31ecfbb1eb47840e343d7dee3d9cd3034d6ff8f9c8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450526"
---
# <a name="accounting-source-explorer"></a>회계 소스 탐색기

[!include [banner](../includes/banner.md)]

이 문서에서는 총계정원장 회계 항목 이면의 소스 정보에 대한 자세한 분석에 사용할 수 있는 회계 소스 탐색기에 대한 정보를 제공합니다.

회계 소스 탐색기는 소스 정보를 보여주는 새로운 페이지입니다. 회계 소스 탐색기를 독립 실행형 도구로 사용하거나 총계정원장 회계 항목 이면의 세부 정보를 분석할 수 있습니다. 예를 들어 회계 소스 탐색기를 사용하여 추적 잔액의 잔액 또는 바우처 거래에 대한 가장 자세한 소스 정보를 얻을 수 있습니다. 그런 다음 MS Excel로 내보내기 기능을 사용하여 Microsoft Excel에서 정보를 추가로 분할할 수 있습니다(예: 피벗 테이블 또는 피벗 테이블 보고서).

회계 소스 탐색기는 총계정원장이 표시하는 것과 동일한 원장 계정당 총액을 항상 표시합니다(예: 시산표). 시산표에서와 같이 세그먼트를 별도의 열에 표시할 수 있습니다. 적절한 재무 차원 집합을 선택하기만 하면 됩니다. 

매개 변수를 사용하여 분석의 날짜 간격을 정의할 수 있습니다. 이 기능은 시산표의 기능과도 유사합니다.

소스 문서 프레임워크를 사용하는 모든 문서에 대해 회계 소스 탐색기는 회계 분배 및 해당되는 경우 프로젝트 회계 분배를 기반으로 추가 정보를 표시합니다. 이 정보에는 금액 유형, 프로젝트, 활동, 범주 및 라인 속성이 포함됩니다. 다음은 수행할 수 있는 분석의 몇 가지 예입니다.

-   각 차이는 청구 차이와 같은 화폐 금액 유형으로 표시되기 때문에 구매 주문과 공급업체 송장 간의 차이
-   프로젝트, 사업부 및 기본 계정당 청구 가능 시간 및 청구 불가 시간 및 비용

소스 문서 참조 ID 개념을 사용하는 소스 문서의 경우 회계 소스 탐색기는 고객, 공급업체, 작업자, 제품, 수량, 단위 텍스트 및 설명과 같은 더 많은 세부사항을 표시합니다. 다음은 수행할 수 있는 분석의 몇 가지 예입니다.

-   경비 보고서를 기반으로 한 회계 기간 동안 사업부 및 호텔 브랜드별 호텔 비용
-   벤더별, 제품별, 부서별 할인

이러한 문서의 경우 회계 소스 탐색기에서 실제 소스 문서로 이동할 수도 있습니다.

> [!NOTE]
> 버전 10.0.20부터 **업데이트** 단추는 페이지에 데이터를 입력하기 위해 실행되는 초기 쿼리를 제한하는 두 가지 추가 범위를 제공합니다. 이러한 추가 범위는 서비스 업데이트로 버전 10.0.19에서도 사용할 수 있습니다. 다음 필드가 추가되었습니다.
>
> - 상품권에서 상품권으로
> - 주 계정에서 주 계정으로

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
