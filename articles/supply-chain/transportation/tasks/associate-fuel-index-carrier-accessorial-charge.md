---
title: 연료 지수를 보조 요금으로 운송업체와 연결
description: 이 가이드는 보조 할당, 운송업체 액세서리 요금, 유류 할증료에 대한 보조 마스터를 생성하고 운송업체 연료 인덱스를 운송업체와 연결하는 방법을 보여줍니다.
author: Henrikan
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 458ee935bec970fc02e3222dcb0c176cf5ddd509
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449278"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a>연료 지수를 보조 요금으로 운송업체와 연결

[!include [banner](../../includes/banner.md)]

이 가이드는 보조 할당, 운송업체 액세서리 요금, 유류 할증료에 대한 보조 마스터를 생성하고 운송업체 연료 인덱스를 운송업체와 연결하는 방법을 보여줍니다. 이 가이드를 실행하기 전에 운송업체 연료 지수를 설정해야 합니다. "운송업체 연료 지수 설정" 가이드를 사용하여 이를 수행할 수 있습니다. 이러한 설정 작업은 일반적으로 물류 관리자가 수행합니다. 이 절차를 만드는 데 사용된 데모 데이터는 USMF입니다.


## <a name="create-an-accessorial-master"></a>액세서리 마스터 만들기
1. 운송 관리 > 설정 > 등급 > 보조 마스터로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 보조 마스터 필드에 값을 입력합니다.
4. 이름 필드에 값을 입력합니다.
5. 저장을 클릭합니다.

## <a name="create-a-carrier-accessorial-charge"></a>운송업체 액세서리 요금 생성
1. 운송 관리 > 설정 > 등급 > 운송업체 액세서리 요금으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 운송업체 액세서리 ID 필드에 값을 입력합니다.
4. 배송 운송업체 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
5. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 이 예에서는 Truck Carrier를 선택합니다.  
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. 운송 서비스 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
8. 목록에서 선택한 행의 링크를 클릭합니다.
9. 보조 마스터 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
10. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 이 예에서는 새로 생성된 액세서리 마스터를 선택합니다.  
11. 저장을 클릭합니다.

## <a name="create-an-accessorial-assignment"></a>액세서리 할당 만들기
1. 보조 할당을 클릭합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에 값을 입력합니다.
4. 기준 섹션의 확장을 토글합니다.
    * 기준에서 유류 할증료를 항상 적용하도록 선택하거나, 이 예에서는 특정 지역 내에서만 적용되도록 선택할 수 있습니다.  
5. 보내는 사람 우편번호 필드에 값을 입력합니다.
6. 받는 사람 우편번호 필드에 값을 입력합니다.
7. 계산 섹션의 확장을 토글합니다.
    * 계산 섹션에서 유류 할증료를 계산하는 방법을 지정할 수 있습니다. 이 계산은 계산의 기준으로 선택한 보조 단위에 따라 다릅니다.  
8. 액세서리 요금 유형 필드에서 '유류 할증료'를 선택합니다.
9. 액세서리 단위 필드에서 '마일리지'를 선택합니다.
10. 하위 지역 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
11. 목록에서 선택한 행의 링크를 클릭합니다.
12. 저장을 클릭합니다.

## <a name="update-the-carrier-rating-profile"></a>운송업체 등급 프로필 업데이트
1. 운송 관리 > 설정 > 운송업체 > 운송업체로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 평가 프로필 섹션의 확장을 토글합니다.
4. 편집을 클릭합니다.
5. 운송업체 연료 지수 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]