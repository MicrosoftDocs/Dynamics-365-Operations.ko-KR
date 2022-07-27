---
title: 사이트 및 창고 적용 범위에 대한 기준 계획, 창고는 필수임
description: 이 항목에서는 적용 범위 차원으로 사이트 및 창고가 있는 항목이 계획되는 방법에 대해 설명합니다. 창고 차원은 필수입니다.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 360d84f7d9087cc9d6e39cb573b8e85381d02da0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449233"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a>사이트 및 창고 적용 범위에 대한 기준 계획, 창고는 필수임

[!include [banner](../includes/banner.md)]

이 항목에서는 적용 범위 차원으로 사이트 및 창고가 있는 항목이 계획되는 방법에 대해 설명합니다. 창고 차원은 필수입니다.

이 기준 계획 시나리오에는 다음 조건이 포함됩니다.

-   사이트 차원은 필수로 설정되며 수요 트랜잭션에 입력해야 합니다.
-   창고 차원은 필수로 설정되며 수요 트랜잭션에 입력해야 합니다.
-   사이트 및 창고 차원은 적용 범위 계획을 위해 설정됩니다. 적용 범위 계획을 위해 다른 차원도 설정할 수 있습니다. 그러나 다중 사이트 기능의 영향을 받지 않습니다.

다음 그래픽은 기준 계획이 어떻게 진행되는지 보여줍니다. 그래픽에서 참조되는 매개 변수와 해당 위치는 다음과 같습니다.
-   창고는 **수동** 으로 설정됩니다. **재고 관리 &gt; 설정 &gt; 재고 분석 &gt; 창고** 를 클릭합니다. **기준 계획** 빠른 탭에서 **수동** 필드를 확인합니다.
-   항목 적용 범위가 항목에 대해 정의됩니다. **제품 정보 관리 &gt; 제품 &gt; 출시된 제품** 을 클릭합니다. 항목을 선택한 다음 작업 창의 **계획** 탭에서 **항목 적용 범위** 를 클릭합니다.
-   다시 채우기 관계는 창고에 대해 정의됩니다. **재고 관리 &gt; 설정 &gt; 재고 분석 &gt; 창고** 를 클릭합니다. **기준 계획** 빠른 탭에서 **주요 창고** 필드 그룹을 확인하세요.
-   기본 주문 유형은 생산, 구매 주문 또는 칸반으로 설정됩니다. **제품 정보 관리 &gt; 제품 &gt; 출시된 제품** 을 클릭합니다. 항목을 선택한 다음 작업 창의 **계획** 탭에서 **기본 주문 설정** 을 클릭합니다. **기본 주문 설정** 양식에서 **기본 주문 유형** 을 확인합니다.

![사이트 및 창고 적용 범위에 대한 수요는 필수입니다.](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



## <a name="additional-resources"></a>추가 리소스

[기준 계획 및 다중 사이트 기능 개요](master-plan-multisite-functionality.md)

[현장 적용 범위용 기준 계획, 필수 창고](master-plan-site-coverage-warehouse-mandatory.md)

[현장 적용 범위용 기준 계획, 창고는 필수가 아님](master-plan-site-coverage-warehouse-not-mandatory.md)

[사이트 및 창고 적용 범위에 대한 기준 계획, 창고는 필수 사항이 아님](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[BOM 버전 확인](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]