---
title: 구성 가능한 제품에 대한 판매 주문 만들기
description: 이 절차는 판매 주문의 제품에 구성 템플릿을 적용하는 방법을 보여줍니다.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e42f121d1efa66f85a3dd811606962b907ed177d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448324"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>구성 가능한 제품에 대한 판매 주문 만들기

[!include [banner](../../includes/banner.md)]

이 절차는 판매 주문의 제품에 구성 템플릿을 적용하는 방법을 보여줍니다. 이 예에서는 USMF 데모 데이터 회사의 D0006 스피커 모델을 사용합니다. 일반적으로 판매 주문 처리자는 이 절차를 사용합니다.

## <a name="create-a-sales-order"></a>판매 주문 만들기

1. **영업 및 마케팅 \> 작업 영역 \> 판매 주문 처리 및 조회** 로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **판매 주문** 을 선택합니다.
1. **고객 계정** 필드에서 *US-001* 을 선택합니다. 
1. **확인** 을 선택합니다.
1. **품목 번호** 필드에서 *D0006* 을 선택합니다.
    * 이 작업의 경우 구성 가능한 제품을 선택해야 합니다.  
1. **제품 및 공급** 을 선택합니다.
1. **라인 구성** 을 선택합니다.
    * 선택한 구성에 따라 가격이 변경되었으며 **케이블 포함** 필드가 이제 *True* 로 설정됩니다.  
    * 기본 가격과 케이블에 대해 선택된 설정을 기록해 둡니다.  
1. **적재 템플릿** 을 선택합니다.
    * 이 예에서는 템플릿을 적용하여 미리 정의된 구성을 선택하는 방법을 보여줍니다. 이 절차를 작업 가이드로 사용하고 사용 가능한 다른 속성 값을 보려면 **잠금 해제** 단추를 선택해야 합니다.  
1. **확인** 을 선택합니다.
1. **확인** 을 선택합니다.
1. **라인 세부 정보** 섹션을 확장합니다.
1. **제품** 탭을 선택합니다.
    * 항목의 구성이 이제 제품 치수 아래에 나열됩니다.  
1. 페이지를 닫습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]