---
title: ER 형식 출력에서 문서 관리 파일 사용(1부 - 데이터 모델 준비)
description: 이번에는 ER 출력에서 문서 관리 파일(첨부 파일)을 사용하도록 전자 보고(ER) 형식을 구성하는 방법에 대해 설명합니다. (1부)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aa4996100a839a8440bad8724680c5799e032064d4a5ec0fbbc0f2af2641b8fb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460713"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a>ER 형식 출력에서 문서 관리 파일 사용(1부 - 데이터 모델 준비)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 ER 출력에서 문서 관리 파일(첨부 파일)을 사용하도록 전자 보고(ER) 형식을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 모든 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 '구성 공급자를 만들고 활성으로 표시' 절차의 단계를 완료해야 합니다.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Microsoft에서 제공하는 구성 목록에 액세스
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.

    'Litware, Inc.' 공급자를 사용할 수 있으며 활성으로 표시됩니다.  

2. 'Litware, Inc.'를 선택합니다. 공급자:
3. 저장소를 클릭합니다.

    '작업 리소스' 유형의 저장소가 이미 존재하는 경우 현재 하위 작업의 나머지 단계를 건너뜁니다.  

4. 추가를 클릭하여 드롭 대화 상자를 엽니다.
5. 구성 리포지토리 유형 필드에 '작업 리소스'를 입력합니다.
6. 리포지토리 만들기를 클릭합니다.
7. '확인'을 클릭합니다.

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a>Microsoft에서 제공하는 고객 송장 모델 구성 가져오기
1. 필터 표시를 클릭합니다.
2. 다음 필터를 적용합니다. '다음으로 시작' 필터 연산자를 사용하여 '이름' 필드에 '작업 리소스'의 필터 값을 입력합니다. '다음으로 시작' 필터 연산자를 사용하여 '설명' 필드에 '' 필터 값 입력
3. 필터 표시를 클릭합니다.
4. 열기를 클릭합니다.
5. 트리에서 '고객 송장 모델'을 선택합니다.

    가져올 모델 구성 '고객 송장 모델'을 선택합니다.  

6. 가져오기를 클릭합니다.

    선택한 구성의 버전 1에 대해 가져오기를 클릭합니다.  

7. “예.
8. 페이지를 닫습니다.
9. 페이지를 닫습니다.
10. 보고 구성을 클릭합니다.
11. 트리에서 '고객 송장 모델'을 선택합니다.

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a>문서 관리 파일에 대한 액세스를 지원하는 파생 모델을 작성하십시오.
Microsoft에서 제공한 구성에서 파생된 고객 송장 모델의 자체 구성을 생성합니다. 이 구성을 사용하여 문서 관리 파일에 대한 액세스를 구현하고 이 모델을 기반으로 만들 전자 문서에 사용할 수 있도록 합니다.  
1. 구성 만들기를 클릭하여 드롭 대화 상자를 엽니다.
2. 새로 만들기 필드에 '이름에서 파생: 고객 송장 모델, Microsoft'.
3. 이름 필드에 '고객 송장 모델(사용자 지정)'을 입력합니다.
4. 구성 만들기를 클릭합니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]