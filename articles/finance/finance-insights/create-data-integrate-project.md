---
title: 데이터 통합 프로젝트 만들기
description: 이 토픽에서는 데이터 통합 프로젝트를 만드는 방법을 설명합니다.
author: ShivamPandey-msft
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 50f435f9d461667a1908baa529d73766085c183a
ms.sourcegitcommit: 6526acd0300d9c5800d3d7675d54e23090d031df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/10/2022
ms.locfileid: "8451528"
---
# <a name="create-a-data-integration-project"></a>데이터 통합 프로젝트 만들기

[!include [banner](../includes/banner.md)]

이 토픽에서는 데이터 통합 프로젝트를 만드는 방법을 설명합니다.

1. Microsoft Dynamics 365 Finance에 로그인합니다.
2. **작업 영역 \> 데이터 관리** 로 이동하여 **데이터 엔터티** 를 선택합니다. 다음 단계로 이동하기 전에 모든 데이터 항목이 새로 고쳐질 때까지 기다리십시오.
3. [Power Apps 포털](https://make.powerapps.com/)을 열고 다음 단계를 따릅니다.

    1. 적절한 환경을 선택하십시오.
    2. 왼쪽 탐색 창에서 **Dataverse \> 연결** 을 선택합니다.
    3. 다음 항목의 적절한 인스턴스에 연결합니다.

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. [Power Apps 환경](https://admin.powerapps.com/environments)을 열고 다음 단계를 따릅니다.

    1. **데이터 통합** 을 선택합니다.
    2. **연결 세트** 를 선택합니다.
    3. **새로운 연결 세트** 를 선택합니다.
    4. 연결 이름을 입력합니다.
    5. 다음 항목에 대해 적절한 연결을 선택하십시오.

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

    6. 적절한 조직 매핑을 선택합니다.
    7. **만들기** 를 선택합니다.

5. [Power Apps 환경](https://admin.powerapps.com/environments)을 열고 다음 단계를 따릅니다.  

    1. 방금 생성한 연결 세트를 사용하여 다음 템플릿에 대한 데이터 통합 프로젝트를 만듭니다.

        - 고객 지불 인사이트 결과(CDS에서 재무 및 운영 10.0.17 이상으로)
        - 현금 흐름 시계열 결과(CDS에서 재무 및 운영으로)
        - 예산 시계열 결과(CDS에서 재무 및 운영으로)

    2. 각 프로젝트에 적절한 일정을 설정합니다.

> [!NOTE]
> Dataverse에 필요한 엔터티가 표시되지 않는 경우 **신용 및 수금** > **설정** > **Finance Insights** > **Finance Insights 매개 변수** 로 이동하여 **고객 지불 예측** 기능을 활성화한 다음 **예측 모델 만들기** 를 선택합니다. AI 모델 배포가 완료되면 통합 생성에 필요한 Dataverse 엔터티가 배포됩니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
