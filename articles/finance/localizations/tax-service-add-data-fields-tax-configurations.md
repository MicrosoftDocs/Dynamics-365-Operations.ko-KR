---
title: 세금 구성에 데이터 필드 추가
description: 이 항목에서는 데이터 필드를 추가하여 세금 구성을 사용자 지정하는 방법을 설명합니다.
author: Kai-Cloud
ms.date: 10/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 590c2d62995f260ba4277e1031349b0dc43f1417
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451081"
---
# <a name="add-data-fields-in-tax-configurations"></a>세금 구성에 데이터 필드 추가

[!include [banner](../includes/banner.md)]

이 항목에서는 [세금 통합에 추가된 데이터 필드](tax-service-add-data-fields-tax-integration-by-extension.md)를 사용하여 세금 구성을 사용자 정의하는 방법을 설명합니다.

## <a name="customize-the-tax-data-model"></a>데이터 모델 사용자 지정

1. Microsoft Dynamics 365 Finance에서 **전자 보고** > **세금 구성** 으로 이동합니다.
2. 구성 트리에서 **세금 계산 데이터 모델** 을 선택합니다. 그런 다음 작업 창에서 **구성 만들기** 를 선택합니다. 

  > [!NOTE] 
  > 사용 가능한 구성 공급자가 없는 경우 하나를 만들고 세금 구성을 위해 활성화합니다. 자세한 내용은 [구성 공급자 생성 및 활성으로 표시](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하십시오.
  
3. 드롭다운 대화 상자에서 **이름으로 세금 문서 모델 선택: 세금 계산 데이터 모델, Microsoft** 를 선택하고 새 세금 데이터 모델의 이름을 입력한 다음 **구성 만들기** 를 선택합니다.
4. 방금 만든 세금 데이터 모델을 선택한 다음 작업 창에서 **디자이너** 를 선택합니다.
5. 데이터 모델 트리를 확장하고 **라인** 을 선택한 다음 **새로 만들기** 를 선택합니다.
6. **노드 만들기** 대화 상자에서 이름을 입력하고 항목 유형을 지정한 다음 **추가** 를 선택합니다.
7. 필요한 열을 추가합니다.
8. 작업 창에서 **저장** 을 선택한 다음 **완료** 를 선택합니다.
9. 페이지를 닫고 세금 데이터 모델의 완성된 버전을 봅니다.

## <a name="customize-the-tax-configuration"></a>세금 구성 사용자 지정

1. Finance에서 **전자 보고** > **세금 구성** 으로 이동합니다.
2. 구성 트리에서 **세금 계산 구성** 을 선택합니다. 그런 다음 작업 창에서 **구성 만들기** 를 선택합니다.
3. 드롭다운 대화 상자에서 **이름으로 세금 서비스 구성 선택을 선택: 세금 계산 구성, Microsoft** 를 선택하고 새 세금 구성의 이름을 입력한 다음 **구성 만들기** 를 선택합니다.
4. 방금 만든 세금 구성을 선택한 다음 작업 창에서 **디자이너** 를 선택합니다.
5. **속성** 섹션의 **데이터 모델** 필드에서 이전에 만든 사용자 지정 세금 데이터 모델을 선택합니다.
6. **데이터 모델 버전** 필드에서 세금 데이터 모델의 완성된 버전을 선택합니다.
7. **추가** 를 선택하고 필요한 세금 조치를 추가합니다.
8. 작업 창에서 **저장** 을 선택한 다음 **완료** 를 선택합니다.
9. 페이지를 닫고 세금 구성의 완성된 버전을 봅니다.

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a>맞춤형 세금 구성의 세금 기능 구현

1. RCS(Regulatory Configuration Service)에서 **세계화 기능** > **세금** 으로 이동합니다.
2. **추가** 를 선택하고 새 기능에 대한 정보를 입력한 다음 **기능 만들기** 를 선택합니다.
3. **버전** 탭에서 기능을 선택한 다음 **편집** 을 선택합니다.
4. **일반** 탭의 **구성 버전** 필드에서 사용자 지정된 세금 구성 및 버전을 선택합니다.
5. **열 관리** 대화 상자에서 사용자 지정 세금 측정에 포함할 헤더 및 라인 열을 선택한 다음 오른쪽 화살표 버튼을 선택하여 **선택한 열** 목록에 추가합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
