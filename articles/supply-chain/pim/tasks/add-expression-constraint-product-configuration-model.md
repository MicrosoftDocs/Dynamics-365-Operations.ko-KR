---
title: 제품 구성 모델에 식 제약 조건 추가
description: 이 절차는 제품 구성 모델에 새 제약 조건 식을 추가하는 방법을 보여줍니다.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77e8b991a2615a8f5d238acc4655f231edb6ca98
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448228"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>제품 구성 모델에 식 제약 조건 추가

[!include [banner](../../includes/banner.md)]

이 절차는 제품 구성 모델에 새 제약 조건 식을 추가하는 방법을 보여줍니다. 사용자가 금속으로 된 전면 그릴을 선택한 경우 모서리 보호 장치를 스피커에 적용해야 한다고 규정할 수 있는 방법을 보여줍니다. 이 절차는 데모 회사 USMF의 고급 스피커 구성 요소를 사용합니다.

## <a name="create-an-expression-constraint"></a>식 제약 조건 생성

1. **제품 정보 관리 \> 제품 \> 제품 구성 모델** 로 이동합니다.
3. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 이 예에서는 고급 스피커 모델을 사용합니다.  
4. 목록에서 선택한 행의 링크를 선택합니다.
5. **제약 조건** 섹션을 펼칩니다.
6. **추가** 를 선택합니다.
7. **만들기** 를 선택합니다.
8. **이름** 필드에 값을 입력합니다.

## <a name="enter-expression"></a>식 입력

1. **식 편집** 을 선택합니다.
    * 이 단계에서 작업 기록의 사용자 인터페이스를 잠금 해제하면 IntelliSense 및 기호 목록을 사용하여 제약 조건 표현식을 작성할 수 있습니다.  
2. **ConstraintBody** 필드에 'Implies[FrontGrill=="Metal", CornerProtection] '을 입력합니다.
    * 이 표현 논리는 다음과 같습니다. 전면 그릴이 금속이면 모서리 보호 옵션을 선택해야 합니다.  
3. **유효성 확인** 을 선택합니다.
    * 유효성 검사 기능은 제약 조건 식을 통해 실행되고 구문 오류가 있는지 확인합니다.  
4. **닫기** 를 선택합니다.
5. **확인** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]