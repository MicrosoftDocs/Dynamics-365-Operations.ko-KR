---
title: 운송업체 설정
description: 이 토픽에서는 운송업체를 설정하고 서비스, 배송 모드, 운송 입찰, 운송 제약 및 운송료와 같은 세부 정보를 정의하는 방법을 보여줍니다.
author: Henrikan
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e9bc4fefb6aabc0b93d4d96f5930590ef99235b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448036"
---
# <a name="set-up-shipping-carriers"></a>운송업체 설정

[!include [banner](../../includes/banner.md)]

이 토픽에서는 운송업체를 설정하고 서비스, 배송 모드, 운송 입찰, 운송 제약 및 운송료와 같은 세부 정보를 정의하는 방법을 보여줍니다. 그런 다음 운송 조정자는 운송업체를 인바운드 또는 아웃바운드 화물에 지정할 수 있습니다.


## <a name="create-a-new-shipping-carrier"></a>새 운송업체 만들기
1. **탐색 창 > 모듈 > 운송 관리 > 설정 > 운송업체 > 운송업체** 로 이동합니다.
2. 작업 창에서 **새로 만들기** 를 선택합니다.
3. **운송업체** 필드에 값을 입력합니다.
4. **이름** 필드에 값을 입력합니다.
5. **모드** 필드의 드롭다운 메뉴에서 옵션을 선택합니다.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>운송업체에 대한 일반 정보를 입력합니다.
1. **개요** 섹션의 확장을 토글합니다.
2. **운송업체 활성화** 확인란을 선택 또는 선택 취소합니다.
3. **공급업체 계정** 필드의 드롭다운 메뉴에서 옵션을 선택합니다. 운송업체를 지정할 공급업체 계정을 선택합니다.  
4. **운송 입찰 유형** 필드에서 옵션을 선택합니다. **수동** 을 선택하여 운송 입찰 페이지를 사용하거나 **EDI** 를 선택하여 전자 데이터 교환(EDI)을 사용하여 입찰을 업데이트합니다.  
5. **운송업체 등급 활성화** 확인란을 선택 또는 선택 취소합니다.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>운송업체에 필요한 서비스 생성
1. **서비스** 섹션의 확장을 토글합니다.
2. **새로 만들기** 를 선택합니다.
3. **운송업체 서비스** 필드에 값을 입력합니다.
4. **이름** 필드에 값을 입력합니다.
5. **운송 방법** 필드의 드롭다운 메뉴에서 옵션을 선택합니다.

## <a name="set-up-the-address-for-the-carrier-optional"></a>배송사 주소 설정(선택사항)
1. **주소** 섹션의 확장을 토글합니다.
2. **새로 만들기** 를 선택합니다.
3. **이름 또는 설명** 필드에 값을 입력합니다.
4. **국가/지역** 필드의 드롭다운 메뉴에서 옵션을 선택합니다.
5. **우편 번호** 필드의 드롭다운 메뉴에서 옵션을 선택합니다.
6. **거리** 필드에 값을 입력합니다.
7. **확인** 을 선택합니다.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>운송업체에 대한 등급 프로필 설정
1. **평가 프로필** 섹션의 확장을 토글합니다.
2. **새로 만들기** 를 선택합니다.
3. **등급 프로필** 필드에 값을 입력합니다.
4. **이름** 필드에 값을 입력합니다.
5. **사이트** 필드의 드롭다운 메뉴에서 옵션을 선택합니다.
6. **창고** 필드의 드롭다운 메뉴에서 옵션을 선택합니다.
7. **요금 엔진** 필드의 드롭다운 메뉴에서 옵션을 선택합니다. 운송업체와 맺은 계약에 따라 요금 엔진을 선택합니다.  
8. **운임 마스터** 필드의 드롭다운 메뉴에서 옵션을 선택합니다.
9. **배송 시간 엔진** 필드의 드롭다운 메뉴에서 옵션을 선택합니다.
10. **저장** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]