---
title: 자유 텍스트 송장 템플릿 생성
description: 이 절차는 자유 텍스트 송장 템플릿을 만드는 방법을 보여줍니다.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7baa29ad341bdf7ff874bd7f69cf483b7afc075a
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8451597"
---
# <a name="create-a-free-text-invoice-template"></a>자유 텍스트 송장 템플릿 생성

[!include [banner](../includes/banner.md)]

이 연습에서는 USMF 데모 회사를 사용합니다. 이 절차는 A/R 송장 관리 및 처리를 담당하는 사용자를 위한 것입니다.

## <a name="create-a-template"></a>템플릿 만들기

1. **수취 계정 > 송장 > 반복 송장 > 자유 텍스트 송장 템플릿** 으로 이동합니다.
    * 이 페이지를 사용하여 송장 라인, 요금, 회계 분포 템플릿 및 원장 계정 정보를 포함할 수 있는 자유 텍스트 송장 템플릿을 생성하십시오.  
2. **새로 만들기** 를 클릭하여 새 자유 텍스트 송장 템플릿을 생성합니다.
3. **템플릿 이름** 필드에 값을 입력합니다.
    * '템플릿 이름'은 자유 텍스트 송장 템플릿을 고유하게 식별합니다. 두 개의 템플릿이 동일한 '템플릿 이름'을 가질 수 없습니다.  
4. **설명** 필드에 템플릿에 대한 설명을 입력합니다.
5. **송장 라인** 탭을 확장합니다.
6. **설명** 필드에 송장 라인에 대한 설명을 입력합니다.
7. **주 계정** 필드에서 수익 계정을 선택합니다.
    * **고객 전기 프로필** 페이지에서 총 송장 금액에 대한 고객 크레딧의 상계 거래 계정을 선택할 수 있습니다.  
8. **판매세 그룹** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
    * 현재 송장 라인에 대한 판매세 그룹은 고객 계정에 대한 기본 판매세 그룹입니다.  
9. 목록에서 선택한 행의 링크를 클릭합니다.
10. **품목세 그룹** 필드에서 현재 송장 라인에 대한 품목 판매세 그룹을 선택합니다.
11. 목록에서 선택한 행의 링크를 클릭합니다.
12. **단가** 필드에 송장 라인의 단위당 가격을 입력하거나 조회합니다
    * 이 금액에 **수량** 필드를 곱하여 송장 라인 금액을 결정합니다.  
13. 자유 텍스트 송장 템플릿에 새 라인을 추가합니다.
14. **설명** 필드에 송장 라인에 대한 설명을 입력합니다.
15. **주 계정** 필드에서 수익 계정을 선택합니다.
    * **고객 전기 프로필** 페이지에서 총 송장 금액에 대한 고객 크레딧의 상계 거래 계정을 선택할 수 있습니다.  
16. **판매세 그룹** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
    * 현재 송장 라인에 대한 판매세 그룹은 고객 계정에 대한 기본 판매세 그룹입니다.  
17. 목록에서 선택한 행의 링크를 클릭합니다.
18. **품목 판매세 그룹** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
    * 현재 송장 라인에 대한 품목 판매세 그룹입니다.  
19. 목록에서 선택한 행의 링크를 클릭합니다.
20. 송장 라인의 단위 수를 입력하거나 봅니다.
    * 송장 라인 금액을 결정하기 위해 이 숫자에 단가 필드의 값이 곱해집니다.  
21. 청구서 라인의 단가를 입력하거나 봅니다. 
    * 송장 라인 금액을 결정하기 위해 이 금액에 **수량** 필드의 값이 곱해집니다.  
22. 개별 라인 및 모든 하위 라인에 대한 회계 분포를 조회하고 수정합니다.
    * 회계 분포는 수익, 세금 또는 요금이 자유 텍스트 송장에 대해 설명되는 방법과 같이 금액이 설명되는 방법을 정의합니다.  
23. 선택한 송장 라인에 대한 회계 분포를 갱신합니다.
24. **닫기** 를 클릭합니다.

## <a name="save-a-free-text-invoice-as-a-template"></a>자유 텍스트 송장을 템플릿으로 저장
기존 자유 텍스트 송장을 템플릿으로 저장할 수도 있습니다. **송장** 탭에서 **템플릿에 저장** 을 선택할 때 템플릿의 이름과 설명을 입력합니다. 해당 이름의 템플릿이 이미 존재하는 경우 해당 이름의 템플릿이 이미 존재한다는 알림이 표시됩니다. **확인** 을 클릭하여 교체할 수 있습니다. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
