---
title: 근태에 대한 급여 프로세스 활성화
description: 이 절차는 근태에 대한 급여 프로세스를 활성화하는 방법을 보여줍니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3b196e25699c43dbac06e950aae0ad8a9457a8d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447922"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a>근태에 대한 급여 프로세스 활성화

[!include [banner](../../includes/banner.md)]

이 절차는 근태에 대한 급여 프로세스를 활성화하는 방법을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.


## <a name="create-a-pay-type-with-a-related-pay-rate"></a>관련 급여 비율로 급여 유형 생성
1. 근태 > 설정 > 급여 > 급여 유형
2. 새로 만들기를 클릭합니다.
3. 급여 유형 필드에 값을 입력합니다.
4. 설명 필드에 값을 입력합니다.
5. 저장을 클릭합니다.
6. 비율을 클릭합니다.
    * 급여 유형별 비율은 특정 시간 간격으로 설정되며 작업자에 대한 개별 비율을 생성할 수 있습니다. 근태에서 급여 유형에 대한 비율을 항상 생성할 필요는 없습니다. 이 정보는 임금을 생성하는 데 사용되는 급여 시스템에 이미 존재할 수 있습니다.  
7. 새로 만들기를 클릭합니다.
8. 목록에서 선택한 행을 표시합니다.
9. 비율 필드에 숫자를 입력합니다.
10. 저장을 클릭합니다.

## <a name="create-a-pay-agreement"></a>급여 계약 만들기
1. 페이지를 닫습니다.
2. 페이지를 닫습니다.
3. 급여 계약으로 이동합니다.
    * 근태 > 설정 > 급여 계약  
4. 새로 만들기를 클릭합니다.
5. 급여 계약 필드에 값을 입력합니다.
6. 설명 필드에 값을 입력합니다.
7. 저장을 클릭합니다.
8. 계약 라인을 클릭합니다.
9. 새로 만들기를 클릭합니다.
10. 목록에서 선택한 행을 표시합니다.
11. 프로필 유형 필드에 값을 입력하거나 선택합니다.
12. 급여 유형 필드에서 값을 입력하거나 선택합니다.

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a>시간 및 등록 작업자에 대한 급여 계약 설정
1. 페이지를 닫습니다.
2. 페이지를 닫습니다.
3. 시간 등록 작업자로 이동합니다.
    * 근태 > 설정 > 시간 등록 작업자  
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. 고용 탭을 클릭합니다.
6. 시간 등록 섹션을 확장합니다.
7. 편집을 클릭합니다.
8. 급여 계약 필드에서 값을 입력하거나 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]