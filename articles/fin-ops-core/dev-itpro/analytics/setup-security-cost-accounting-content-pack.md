---
title: 원가 회계 분석 Power BI 콘텐츠를 위한 보안 설정
description: 이 항목에서는 원가 회계의 액세스 수준 보안을 Microsoft Power BI의 행 수준 보안으로 전파하는 방법에 대해 설명합니다.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f519a38b381da0efc1e91ba0f2015780d086550c3e38810e6845a0fc07976767
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460729"
---
# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>원가 회계 분석 Power BI 콘텐츠를 위한 보안 설정

[!include [banner](../includes/banner.md)]

이 항목에서는 원가 회계의 액세스 수준 보안을 Microsoft Power BI의 행 수준 보안으로 전파하는 방법에 대해 설명합니다. 이 기능은 사용자가 액세스 권한이 부여된 Power BI 데이터만 볼 수 있게 합니다.

## <a name="overview"></a>개요

**원가 회계 분석** Microsoft Power BI 콘텐츠는 Power BI 행 수준 보안을 사용하여 사용자의 액세스를 제한합니다. 보안은 비용 회계 매개변수에 설정된 액세스 수준 조직 계층을 기반으로 합니다. **원가 회계 분석** Power BI 콘텐츠에 대한 자세한 내용은 [원가 회계 분석 Power BI 콘텐츠](cost-accounting-analysis-content-pack.md)를 참조하세요.

## <a name="setup"></a>설정
Power BI로 액세스 수준 보안을 전파하려면 Power BI 콘텐츠의 소유자가 다음 단계를 따라야 합니다.

> [!NOTE]
> **원가 회계 분석** Power BI 콘텐츠를 게시하는 사용자는 자동으로 소유자가 됩니다. 소유자만 Power BI에 보안을 설정할 수 있습니다. 또한 소유자가 PowerBI.com에 다른 사용자를 추가할 때까지 소유자를 제외한 누구도 **원가 회계 분석** Power BI 콘텐츠의 데이터를 볼 수 없습니다.

1. Power BI에 정의 파일을 게시합니다.
2. PowerBI.com에 로그인합니다.
3. **원가 회계 분석** Power BI 콘텐츠의 데이터 세트를 찾습니다.
4. 보안 페이지를 엽니다.

    ![보안 페이지 열기.](./media/CA-picture-1.png)

5. **비용 개체 컨트롤러** 역할이 이미 생성되었습니다. 원가 회계 액세스 수준 조직 계층의 일부인 다른 구성원을 추가합니다.

    ![구성원 추가.](./media/CA-picture-2.png)

**비용 개체 컨트롤러** 역할에 에 추가된 사용자는 원가 회계 액세스 수준 조직 계층 구조의 정의에 따라 볼 수 있는 데이터만 볼 수 있습니다.

> [!NOTE]
> 행 수준 보안은 Power BI에서 포함된 타일 및 보고서에 적용됩니다.

## <a name="updating-security"></a>보안 업데이트
비용 회계에서 액세스 수준 보안이 업데이트되고 Power BI가 이러한 업데이트를 반영하도록 하려면 **원가 회계 분석** Power BI 콘텐츠에 대해 엔터티 저장소를 업데이트해야 합니다. 엔티티 저장소 업데이트를 완료한 후 PowerBI.com에서 아티팩트를 업데이트해야 합니다. 엔터티 스토어 업데이트 작업 방법에 대한 자세한 내용은 [Power BI와 엔터티 스토어 통합](power-bi-integration-entity-store.md#update-entity-store)을 참조하세요. **원가 회계 분석** Power BI 콘텐츠의 소유자는 새 사용자에게 조직 계층에 대한 액세스 권한이 부여된 경우 콘텐츠도 엔터티 저장소 업데이트를 수행해야 합니다. 또한 소유자는 새 사용자를 행 수준 보안이 적용되도록 PowerBI.com **비용 개체 컨트롤러** 역할에 추가해야 합니다.

## <a name="disabling-security"></a>보안 비활성화
조직에서 데이터 액세스를 제한하려고 한다고 가정합니다. 어떤 이유로 원가 회계를 실행할 때 보안 매개변수가 비활성화된 경우 소유자는 사용자를 대신 Power BI의 **원가 회계사** 역할에 추가해야 합니다. 활성화된 상태에서 비활성화된 상태로 보안을 변경하는 경우 **비용 개체 컨트롤러** 역할에서 사용자를 제거하는 것이 좋습니다. 보안을 다시 활성화하면 그 반대의 경우도 마찬가지입니다. 사용자는 두 역할에 모두 속할 수 있습니다. 공동 액세스는 두 역할의 결합입니다. **원가 회계 분석** Power BI 콘텐츠의 경우 공동 액세스 권한이 있는 사용자는 무제한 데이터 액세스 권한을 가집니다. 제한된 액세스를 적용하는 것이 목표인 경우 사용자는 **비용 개체 컨트롤러** 역할에만 할당되어야 합니다. 이러한 행 수준 보안 업데이트는 즉시 적용됩니다. 영향을 받는 사용자는 브라우저를 새로 고쳐야 합니다.

## <a name="additional-resources"></a>추가 리소스
Power BI 행 수준 보안에 대해 자세히 알아보려면 [Power BI에서 모델에 대한 보안 관리](https://powerbi.microsoft.com/documentation/powerbi-admin-rls/#manage-security-on-your-model)를 참조하세요.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]