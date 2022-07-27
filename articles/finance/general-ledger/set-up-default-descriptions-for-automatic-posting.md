---
title: 자동 게시에 대한 기본 설명 설정
description: 이 항목에서는 총계정원장에 자동으로 게시되는 회계 항목을 설명하는 데 사용되는 기본 텍스트를 설정하는 방법을 설명합니다. 자유 형식 텍스트를 사용하거나 고정 변수를 선택하여 기본 설명 텍스트를 설정할 수 있습니다.
author: aprilolson
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 89ea19753abdc4e5d4219a123a832bb3606515a43b439d5f94a9619857b6c7d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450211"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a>자동 게시에 대한 기본 설명 설정

[!include [banner](../includes/banner.md)]

이 항목에서는 총계정원장에 자동으로 게시되는 회계 항목을 설명하는 데 사용되는 기본 텍스트를 설정하는 방법을 설명합니다. 자유 형식 텍스트를 사용하거나 고정 변수를 선택하여 기본 설명 텍스트를 설정할 수 있습니다.

> [!NOTE]
> 일부 국가 또는 지역의 일부 거래 유형의 경우 해당 거래 유형과 관련된 Microsoft Dynamics AX 데이터베이스 필드의 텍스트를 포함할 수도 있습니다. 거래 유형, 국가 및 지역의 목록은 이 항목의 뒷부분의 [선택 사항: 기본 설명에 다른 텍스트 추가](#optional-add-other-text-to-default-descriptions)를 참조하세요.

## <a name="set-up-default-descriptions"></a>기본 설명 설정

1. **조직 관리** \> **설정** \> **기본 설명** 으로 이동합니다.
2. 작업 창에서 **새로 만들기** 를 선택합니다.
3. **설명** 필드에 기본 설명을 생성할 거래 유형을 선택합니다.
4. **언어** 필드에서 설명이 적용되는 언어를 선택합니다.
5. **텍스트** 필드에 기본 설명을 입력합니다. 필드에 텍스트를 입력하거나 다음 자유 텍스트 변수 중 하나 이상을 사용할 수 있습니다.

    - **%1** – 거래 날짜를 추가합니다.
    - **%2**– 총계정원장에 게시되는 문서 유형에 해당하는 식별자를 추가합니다. 예를 들어 송장과 관련된 거래 유형의 경우 **%2** 변수는 송장 번호를 추가합니다.
    - **%3**– 총계정원장에 게시되는 문서 유형과 연관된 식별자를 추가합니다. 예를 들어 송장과 관련된 거래 유형의 경우 **%3** 변수는 고객 계정 번호를 추가합니다.

## <a name="optional-add-other-text-to-default-descriptions"></a>선택 사항: 기본 설명에 다른 텍스트 추가

일부 국가 또는 지역의 일부 거래 유형의 경우 기본 설명에 해당 거래 유형과 관련된 데이터 필드의 텍스트가 포함될 수 있습니다. 다음 목록은 이 옵션을 사용할 수 있는 거래 유형과 국가 및 지역을 보여줍니다.

**거래 유형**

다음 문서 유형과 관련된 거래 유형의 기본 설명에 다른 텍스트를 추가할 수 있습니다.

- 고객 송장
- 고객 대변표
- 고객 현금 지불
- 공급업체 지불
- 판매 주문
- 구매 주문
- 재고 분개장
- 마스터 계획(MRP)
- 고정 자산

**국가 및 지역**

이 옵션은 다음 국가 및 지역에서 사용할 수 있습니다.

- 브라질
- 중국
- 체코
- 동유럽
- 헝가리
- 인도
- 일본
- 리투아니아
- 라트비아
- 폴란드
- 러시아

### <a name="add-text-to-default-descriptions"></a>기본 설명에 텍스트 추가

이 항목 앞부분의 [기본 설명 설정](#set-up-default-descriptions) 섹션의 단계를 완료한 후 다음 단계에 따라 기본 설명에 다른 텍스트를 추가할 수 있습니다.

1. **매개 변수** 빠른 탭에서 **추가** 를 선택합니다.
2. **참조 테이블** 필드에서 설명에 매개 변수 데이터를 추가할 데이터베이스 테이블을 선택합니다.
3. **참조 필드** 필드에서 설명에 매개 변수 데이터를 추가할 필드를 선택합니다.
4. 매개 변수를 더 추가하려면 1~3단계를 반복합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]