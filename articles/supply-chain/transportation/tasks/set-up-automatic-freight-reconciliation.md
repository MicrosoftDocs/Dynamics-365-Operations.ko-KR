---
title: 자동 운임 조정 설정
description: 이 절차는 자동 운임 조정을 위한 데이터를 설정하는 방법을 보여줍니다.
author: Henrikan
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1dbe3c683d869f86bc7231c68839f431cc61d6b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448759"
---
# <a name="set-up-automatic-freight-reconciliation"></a>자동 운임 조정 설정

[!include [banner](../../includes/banner.md)]

이 절차는 자동 운임 조정을 위한 데이터를 설정하는 방법을 보여줍니다. 이는 일반적으로 창고 관리자가 수행합니다. 데모 데이터 회사 USMF에서 이 절차를 사용할 수 있습니다.


## <a name="set-up-the-freight-bill-type"></a>운임 청구서 유형 설정
1. 운송 관리 > 설정 > 운임 조정 > 운임 청구서 유형으로 이동합니다.
    * 운임 청구서 유형은 운임 청구서와 운송업체 송장이 일치되어야 하는 방법을 정의합니다.  
2. 새로 만들기를 클릭합니다.
3. 운임 청구서 유형 필드에 값을 입력합니다.
4. 엔진 어셈블리 필드에 'Microsoft.Dynamics.Ax.Tms.dll'을 입력합니다.
    * 이것은 표준 운송 관리 매칭 엔진 코드 라이브러리입니다.  
5. 엔진 클래스 필드에 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'를 입력합니다.
    * 이것은 표준 운송 관리 매칭 엔진 클래스입니다.  
6. 새로 만들기를 클릭합니다.
7. 설명 필드에서 운임 청구서와 운송업체 송장과 일치해야 하는 값을 선택합니다.  
8. 일치 필수 필드에서 '예'를 선택합니다.
    * 이 필드를 예로 설정하면 설명 필드에서 선택한 값이 운임 청구서와 운송업체 송장 모두에서 일치해야 함을 의미합니다. 아니요로 설정하면 이들 중 하나에서 필드가 비어 있을 수 있습니다.  
9. 저장을 클릭합니다.

## <a name="set-up-the-freight-bill-type-assignment"></a>운임 청구서 유형 할당 설정
1. 페이지를 닫습니다.
2. 운송 관리 > 설정 > 운임 조정 > 운임 청구서 유형 할당으로 이동합니다.
    * 운임 청구서 유형 할당은 특정 운송업체에 사용되는 운임 청구서 유형을 할당하는 데 사용됩니다.   
3. 새로 만들기를 클릭합니다.
4. 모드 필드에 값을 입력하거나 선택합니다.
5. 운송업체 필드에 값을 입력하거나 선택합니다.
6. 운송비 청구서 유형 필드에서 이전에 생성한 운송비 청구서 유형을 선택합니다.
7. 페이지를 닫습니다.

## <a name="set-up-the-audit-master"></a>감사 마스터 설정
1. 운송 관리 > 설정 > 운임 조정 > 감사 마스터로 이동합니다.
    * 감사 마스터는 자동 운임 조정에 대한 허용 한도를 정의합니다. 운임 청구서와 운송업체 송장의 금액이 얼마나 다를 수 있는지 지정하고 조정이 발생하도록 허용합니다. 또한 불일치를 처리하는 방법을 정의합니다.  
2. 새로 만들기를 클릭합니다.
3. 감사 마스터 ID 필드에 값을 입력합니다.
4. 운송업체 필드에서 이전과 동일한 운송업체를 선택합니다.
5. 운송비 청구서 유형 필드에서 이전에 생성한 운송비 청구서 유형을 선택합니다.
6. 허용 범위 섹션을 펼칩니다.
7. 최소 허용 수준 필드에 숫자를 입력합니다.
8. 최대 허용 수준 필드에 숫자를 입력합니다.
9. 결과 섹션을 펼칩니다.
10. 초과 지불 사유 코드 필드에 값을 입력하거나 선택합니다.
    * 금액이 운임 청구서와 운송업체 송장에서 다른 경우 초과 지급 및 미달 지급 사유 코드는 차액이 허용 범위 내에 있는 한 차액을 등록해야 하는 계정을 지정합니다.  
11. 미달 지불 사유 코드 필드에 값을 입력하거나 선택합니다.
12. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]