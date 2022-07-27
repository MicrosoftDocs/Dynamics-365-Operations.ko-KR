---
title: 고급 은행 조정 MT940 가져오기 – 복합 데이터 엔터티 업그레이드
description: MT940 형식을 지원하려면 은행 거래 내역서 가져오기 엔터티에 시퀀스 번호를 추가해야 합니다.
author: panolte
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c891a5139ff7de85e6762513f57236e24f1644529d7825c9ce5e1dfda50fbad8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450406"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>고급 은행 조정 MT940 가져오기 – 복합 데이터 엔터티 업그레이드

[!include [banner](../includes/banner.md)]

MT940 형식을 지원하려면 은행 거래 내역서 가져오기 엔터티에 시퀀스 번호를 추가해야 합니다. 

다음 단계를 사용하여 MT940 형식을 지원하는 은행 거래 내역서 가져오기 엔터티를 추가합니다.

1.  다음을 컴파일하고 동기화합니다.
    -   복합 엔티티\\BankStatementImportEntity
    -   엔터티\\BankStatementBalanceEntity
    -   엔터티\\BankStatementDocumentEntity
    -   엔터티\\BankStatementEntity
    -   엔터티\\BankStatementLineEntity
    -   테이블\\BankStatementStaging

2.  자료 관리\\데이터 프로젝트.
    1.  MT940 가져오기 프로젝트 로드
        1.  XSLT를 변경합니다.
            -   **맵 보기** 를 클릭합니다.
            -   은행 거래 내역서 문서에서 **맵 보기** 를 클릭합니다.
            -   **변환** 클릭
            -   BankReconiliation-to-Composite.xslt 파일을 삭제합니다.
            -   BankReconiliation-to-Composite.xsl의 새 버전을 추가합니다.

        2.  **소스 데이터** 레이아웃에 **시퀀스 번호** 를 노출합니다.
            1.  소스 데이터 형식 = XML-요소.
            2.  엔티티 이름 = 은행 거래 내역서.
            3.  업로드 데이터 파일 = 새 버전 SampleBankCompositeEntity.xml.
            4.  **예** 를 클릭하여 기존 파일을 덮어씁니다.
            5.  **예** 를 클릭하여 새 매핑을 생성합니다.
            6.  **SequenceNumber** 가 매핑되었는지 확인합니다.
                -   명령문 엔티티에서 **맵 보기** 를 클릭합니다.
                -   **SequenceNumber** 가 소스에서 스테이징으로 매핑되었는지 확인합니다.

3.  새 명세서를 가져옵니다.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]