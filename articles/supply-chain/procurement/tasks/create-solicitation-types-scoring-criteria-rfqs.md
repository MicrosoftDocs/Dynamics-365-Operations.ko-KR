---
title: 견적 요청에 대한 요청 유형 및 점수 기준 만들기
description: 이 가이드에서는 요청 유형을 만들고 이를 채점 방법과 연결하는 방법을 보여줍니다.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d55b91def8b8edf8310cfa0bfe9d2bcc321ee6a6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448201"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>견적 요청에 대한 요청 유형 및 점수 기준 만들기

[!include [banner](../../includes/banner.md)]

이 가이드에서는 요청 유형을 만들고 이를 채점 방법과 연결하는 방법을 보여줍니다. 또한 견적 요청(견적 요청)에서 요청 유형을 사용하여 기본 채점 방법을 설정하는 방법을 보여줍니다. 이러한 작업은 일반적으로 구매 관리자가 수행합니다. 데모 데이터 회사 USMF 또는 자체 데이터에서 이 절차를 사용할 수 있습니다. 시작하기 전에 채점 방법을 사용할 수 있어야 합니다.


## <a name="create-a-solicitation-type"></a>요청 유형 만들기
1. 조달 및 소싱 > 설정 > 견적 요청 > 요청 유형으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에 값을 입력합니다.
4. 설명 필드에 값을 입력합니다.
5. 채점 방법 필드에서 이 요청 유형에 사용할 채점 방법을 선택합니다.
6. 저장을 클릭합니다.
7. 페이지를 닫습니다.

## <a name="use-the-solicitation-type"></a>요청 유형 사용
1. 조달 및 소싱 > 견적 요청 > 모든 견적 요청으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 요청 유형 필드에서 방금 만든 요청 유형을 선택합니다. 
    *   
4. 확인을 클릭합니다.
5. 채점 기준을 클릭합니다.
    * 표시되는 채점 기준은 요청 유형과 연결한 채점 방법의 기준입니다. 이 페이지에서 기준을 추가하거나 삭제할 수 있습니다. 다른 채점 방법에서 기준을 복사하여 새로 추가하는 것도 가능합니다.  
6. 기준 복사를 클릭합니다.
7. 채점 방법 필드에서 값을 입력하거나 선택합니다.
8. 확인을 클릭합니다.
9. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]