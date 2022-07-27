---
title: 재무 차원 정의
description: 이 절차는 엔터티 지원 재무 차원과 사용자 지정 재무 차원을 추가하는 방법을 보여 줍니다.
author: aprilolson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed6dad64032c03e638c2090471af825dd18560a1
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2021
ms.locfileid: "8450913"
---
# <a name="define-financial-dimensions"></a>재무 차원 정의

[!include [banner](../../includes/banner.md)]

이 절차는 엔터티 지원 재무 차원과 사용자 지정 재무 차원을 추가하는 방법을 보여 줍니다.  이 가이드는 USMF 데모 회사를 사용합니다.


## <a name="create-an-entity-backed-financial-dimension"></a>엔터티 지원 재무 차원 만들기
1. **탐색 창 > 모듈 > 총계정원장 > 계정 차트 > 차원> 재무 차원** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **사용자 값 위치** 필드에서 재무 차원의 기준이 되는 시스템 정의 엔터티를 선택합니다. 
4. **차원 이름** 필드에 재무 차원을 설명하는 값을 입력합니다. 이름은 시스템 정의 엔터티와 다를 수 있지만 공백이나 특수 문자를 포함할 수 없습니다.
5. **활성화** 를 클릭합니다. 재무 차원을 활성화하면 재무 차원 이름으로 테이블이 업데이트되고 삭제된 차원이 제거됩니다. 재무 차원을 활성화하기 전에 차원 값을 입력할 수 있지만 재무 차원은 활성화될 때까지 사용할 수 없습니다.  
6. 활성화 메시지에서 **닫기** 를 클릭합니다.
7. **활성화** 를 클릭합니다. 차원 활성화는 특정 날짜 및 시간에 일괄 처리되도록 예약할 수 있습니다.  
8. **작업 창** 에서 **차원 값** 을 클릭합니다. 일부 차원 값은 회사에 따라 다릅니다. 차원 값 목록에 회사 이름이 표시되는지 보고 특정 회사의 값인지 확인할 수 있습니다.  

## <a name="create-a-custom-financial-dimension"></a>사용자 지정 재무 차원 만들기
1. 페이지를 닫습니다.
2. **새로 만들기** 를 클릭합니다.
3. **다음 값 사용** 필드에서 **사용자 지정 차원** 을 선택합니다.
4. **차원 이름** 필드에 재무 차원을 설명하는 값을 입력합니다.
    - 이름에는 공백이나 특수 문자를 사용할 수 없습니다.  
    - 계정 마스크를 지정하여 차원 값에 입력할 수 있는 정보의 양과 유형을 제한할 수도 있습니다.   
    - 문자나 하이픈과 같이 각 차원 값에 대해 동일한 문자를 입력할 수 있습니다. 또한 숫자 기호(#)와 앰퍼샌드(&)를 문자 및 숫자의 자리 표시자로 입력할 수 있습니다. 이는 차원 값이 생성될 때마다 변경됩니다. 숫자의 자리 표시자로 숫자 기호(#)를 사용하고 문자의 자리 표시자로 앰퍼샌드(&)를 사용합니다.  예: 차원 값을 문자 CC와 숫자 3개로 제한하려면 형식 마스크로 CC-###을 입력합니다.  
5. **활성화** 를 클릭합니다. 재무 차원을 활성화하면 재무 차원 이름으로 테이블이 업데이트되고 삭제된 차원이 제거됩니다. 재무 차원을 활성화하기 전에 차원 값을 입력할 수 있지만 재무 차원은 활성화될 때까지 사용할 수 없습니다.     
6. **활성화** 를 클릭합니다. 차원 활성화는 특정 날짜 및 시간에 일괄 처리되도록 예약할 수 있습니다.      
7. **작업 창** 에서 **차원 값** 을 클릭합니다.
8. **새로 만들기** 를 클릭합니다.
9. **차원 값** 필드에 재무 차원 값을 설명하는 이름을 입력합니다.
10. **설명** 필드에 재무 차원 값을 설명하는 설명을 입력합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
