---
title: 공급업체 계정 만들기
description: 이 절차는 공급업체 계정을 만들고 주소 및 연락처 정보를 추가하는 방법을 보여줍니다.
author: Henrikan
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16abc34b881fffdb9f278fd097efbcdc693b235f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448300"
---
# <a name="create-a-vendor-account"></a>공급업체 계정 만들기

[!include [banner](../../includes/banner.md)]

이 절차는 공급업체 계정을 만들고 주소 및 연락처 정보를 추가하는 방법을 보여줍니다. 이 절차에서는 구매 및 재정적 목적을 위해 모든 필드를 채우는 방법을 보여주지 않습니다. 해당 필드에 대해 자세히 알아보려면 필드 설명을 읽으세요. 데모 데이터 회사 USMF 또는 자체 데이터에서 이 절차를 사용할 수 있습니다. 공급업체 계정은 일반적으로 조달 전문가 또는 수취 계정 담당자가 만듭니다.


## <a name="create-a-vendor-account"></a>공급업체 계정 만들기
1. **탐색 창 > 모듈 > 조달 및 소싱 > 공급업체 > 모든 공급업체** 로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **공급업체 계정** 필드에 값을 입력합니다.
    - 값이 자동으로 채워질 수 있습니다. 자동으로 채워지는 경우 이 단계를 건너뛸 수 있습니다.  
    - 개인 또는 조직에 대한 공급업체 계정을 생성할 수 있습니다. 사용 가능한 필드에 영향을 미칩니다. 이 예에서는 조직에 대한 공급업체 계정을 만듭니다.   
4. **이름** 필드에 값을 입력하거나 선택합니다. 공급업체가 시스템에 이미 등록된 당사자인 경우 드롭다운을 사용하여 이 필드에서 선택할 수 있으며 새 공급업체 계정은 이미 등록된 주소와 연락처 정보를 상속합니다.
5. **그룹** 필드에 값을 입력하거나 선택합니다. 공급업체 그룹은 결제 조건, 정산 기간, 판매세 그룹, 기본 원장 계정, 제품 필터 코드 또는 공급 예측 구성을 포함한 재고 전기 원장 계정과 같은 공통 매개 변수가 있는 공급업체를 그룹화하는 데 사용됩니다.
6. **직원 수** 필드에 숫자를 입력합니다.
7. **조직 번호** 필드에 값을 입력합니다.

## <a name="add-an-address"></a>주소 추가
1. **주소** 섹션을 펼칩니다.
2. **추가** 를 클릭합니다.
3. **목적** 필드에서 값을 입력하거나 선택합니다. 하나 이상의 목적을 선택할 수 있습니다. 이들은 주어진 목적에 대한 올바른 주소를 선택하는 데 사용됩니다. 예를 들어 목적이 "송장"인 경우 송장을 보낼 때 해당 주소가 사용됩니다.
4. **이름 또는 설명** 필드에 값을 입력합니다.
5. **국가/지역** 필드에서 값을 입력하거나 선택합니다. 주소 세부 정보를 입력합니다. 선택한 국가/지역은 국가/지역의 주소 형식에 따라 표시되는 필드를 결정합니다. 
6. **확인** 을 클릭합니다.

## <a name="add-contact-information"></a>연락처 추가 정보
1. **연락처 정보** 섹션을 확장합니다.
2. **추가** 를 클릭합니다.
3. **설명** 필드에 값을 입력합니다.
4. **유형** 필드에서 옵션을 선택합니다.
5. **연락처/주소** 필드에 값을 입력합니다. 기본 연락처인 경우 기본 확인란을 선택할 수 있습니다.  
6. **저장** 을 클릭합니다.
7. 페이지를 닫습니다.
8. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]