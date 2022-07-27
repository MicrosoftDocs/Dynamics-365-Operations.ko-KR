---
title: 은행 분개장 복합 엔터티 업데이트
description: 이 주제에서는 복합 BankJournalEntity에 BankTransactionType 필드를 추가하는 데 필요한 단계를 나열합니다.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0d4334e9aa333aad116f0a0291d9175268661f11
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451033"
---
# <a name="update-the-bank-journal-composite-entity"></a>은행 분개장 복합 엔터티 업데이트

[!include [banner](../includes/banner.md)]

이 주제에서는 복합 BankJournalEntity에 BankTransactionType 필드를 추가하는 데 필요한 단계를 나열합니다.

다음 단계를 사용하여 추가 BankTransactionType 필드를 복합 BankJournalEntity에 추가합니다.

1.  다음 은행 분개장 복합 엔터티, 엔터티 및 준비 테이블을 컴파일하고 동기화합니다.
    -   복합 엔터티\\BankJournalEntity
    -   엔터티\\BankJournalHeaderEntity
    -   엔터티\\BankJournalLineEntity
    -   테이블\\BankJournalHeaderStaging
    -   테이블\\BankJournalLineStaging

2.  데이터 관리\\데이터 프로젝트
    -   **원본 데이터** 레이아웃에 **은행 거래** 를 노출합니다.
        -   원본 데이터 형식 = XML-Element
        -   엔터티 이름 = 은행 분개장
        -   업로드 데이터 파일 = 새 버전 SampleBankJournalCompositeEntity.xml
        -   **예** 를 클릭하여 기존 파일을 덮어씁니다.
        -   **예** 를 클릭하여 새 매핑을 새로 생성합니다.
        -   은행 거래 유형이 매핑되었는지 확인합니다.
            -   라인 엔터티에서 **맵 보기** 를 클릭합니다.
            -   은행 거래 유형이 원본에서 준비로 매핑되었는지 확인합니다.

3.  새 명세서를 가져옵니다.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
