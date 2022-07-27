---
title: 제품 모델의 경로 유지
description: 이 절차를 실행하려면 제품 구성 모델이 있어야 합니다.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88df8b867ac7f354417add0462e7999747333451
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448993"
---
# <a name="maintain-route-for-a-product-model"></a>제품 모델의 경로 유지

[!include [banner](../../includes/banner.md)]

이 절차를 실행하려면 제품 구성 모델이 있어야 합니다. 이 절차는 데모 회사 USMF의 고급 스피커 모델을 사용하여 프로세스를 설명합니다.

## <a name="add-a-route-operation"></a>경로 작업 추가

1. **제품 정보 관리 \> 제품 \> 제품 구성 모델** 로 이동합니다.
1. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 이 연습에서는 하이엔드 스피커 모델을 선택합니다.  
1. 목록에서 선택한 행의 링크를 선택합니다.
1. **경로 작업** 섹션을 펼칩니다.
1. **추가** 를 선택합니다.
1. **이름** 필드에 값을 입력합니다.
1. **설명** 필드에 값을 입력합니다.
1. **저장** 을 선택합니다.

## <a name="enter-route-operation-details"></a>경로 운영 세부 정보 입력

1. **경로 작업 세부 정보** 를 선택합니다.
1. **작업** 필드에 값을 입력하거나 선택합니다.
1. **작업 번호** 에서 필드에 숫자를 입력합니다.
    * 작업 번호는 경로 순서를 결정합니다.  
    * 경로 작업의 각 특성은 정적 값을 가져오거나 속성에 매핑될 수 있습니다. 속성에 매핑하면 값이 구성의 일부로 설정됩니다.  
1. **경로 그룹** 필드에 값을 입력하거나 선택합니다.
    * 경로 그룹은 비용, 소비 및 설정에 대한 필수 동작을 결정합니다.  
1. **설정** 탭을 선택합니다.
1. **시간** 탭을 선택합니다.
1. **절차 수량** 필드에 숫자를 입력합니다.
    * 한 작업 동안 처리할 수를 결정합니다.  
1. **시간** 필드에 숫자를 입력합니다.
    * 시간 비율을 입력합니다.  
1. **설정** 확인란을 선택합니다.
1. **실행 시간** 필드에 숫자를 입력합니다.
    * 지정한 수량의 처리 시간을 결정합니다.  
1. **리소스 요구 사항** 탭을 선택합니다.
1. **추가** 를 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **요구 사항 유형** 필드에서 옵션을 선택합니다.
    * 보유해야 하는 특정 리소스 또는 기능을 지정할지 여부를 결정합니다.  
1. **요구 사항** 필드에서 값을 입력하거나 선택합니다.
1. **확인** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]