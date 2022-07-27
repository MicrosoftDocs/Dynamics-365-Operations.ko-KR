---
title: 운송업체 연료 인덱스 설정
description: 이 가이드는 연료 인덱스 하위 지역, 연료 인덱스 및 운송업체 연료 인덱스를 만드는 방법을 보여줍니다.
author: Henrikan
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFuelIndexRegion,TMSCarrierFuelIndexTable,TMSFuelIndex
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b67219a6cb19b393dce25f77febc194c5ea2a16
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448888"
---
# <a name="set-up-a-carrier-fuel-index"></a>운송업체 연료 인덱스 설정

[!include [banner](../../includes/banner.md)]

이 가이드는 연료 인덱스 하위 지역, 연료 인덱스 및 운송업체 연료 인덱스를 만드는 방법을 보여줍니다. 연료 인덱스 하위 지역은 연료 인덱스를 적용해야 하는 지역을 지정하고, 연료 인덱스는 특정 기간의 연료 가격을 지정합니다. 시간 경과에 따른 연료 가격의 변화를 반영하기 위해 여러 연료 인덱스를 운송업체와 연결할 수 있습니다.  이러한 작업은 일반적으로 운송 조정자가 수행합니다. 데모 데이터 회사 USMF에서 또는 자체 데이터를 사용하여 이 절차를 사용할 수 있습니다.


## <a name="create-a-fuel-index-region"></a>연료 인덱스 하위 지역 생성
1. 운송 관리 > 설정 > 연료 인덱스 > 연료 인덱스 하위 지역으로 이동합니다.
    * 먼저 다양한 유류 할증료를 운영하고 계산하는 여러 하위 지역을 만들어야 합니다.  
2. 새로 만들기를 클릭합니다.
3. 하위 지역 필드에 값을 입력합니다.
4. 이름 필드에 값을 입력합니다.
5. 저장을 클릭합니다.

## <a name="create-a-fuel-index"></a>연료 인덱스 생성
1. 운송 관리 > 설정 > 연료 인덱스 > 연료 인덱스로 이동합니다.
    * 설정한 하위 지역에 대해 현재 연료 가격을 입력해야 합니다.  
2. 새로 만들기를 클릭합니다.
3. 하위 지역 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. 갤런당 가격 필드에 숫자를 입력합니다.
6. 적용 시작 날짜 및 시간 필드에 날짜와 시간을 입력합니다.
7. 저장을 클릭합니다.

## <a name="create-a-carrier-fuel-index"></a>운송업체 연료 인덱스 생성
1. 운송 관리 > 설정 > 연료 인덱스 > 운송업체 연료 인덱스로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 운송업체 연로 인덱스 필드에 값을 입력합니다.
4. 설명 필드에 값을 입력합니다.
5. 새로 만들기를 클릭합니다.
6. 적용 시작 날짜 및 시간 필드에 날짜와 시간을 입력합니다.
7. PPG From 필드에 숫자를 입력합니다.
    * 이 예에서는 PPG From 필드를 1.95로 설정할 수 있습니다.  
8. PPG To 필드에 숫자를 입력합니다.
    * 이 예에서는 PPG To 필드를 2로 설정할 수 있습니다.  
9. 비율 필드에 숫자를 입력합니다.
    * 이 예에서는 비율을 3으로 설정할 수 있습니다.  
10. 통화 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
11. 목록에서 원하는 레코드를 찾아 선택합니다.
12. 목록에서 선택한 행의 링크를 클릭합니다.
13. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]