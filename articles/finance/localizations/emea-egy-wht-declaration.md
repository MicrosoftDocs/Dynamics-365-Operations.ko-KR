---
title: 이집트에 대한 원천징수세 신고
description: 이 항목에서는 이집트에 대한 원천세 신고를 구성하고 생성하는 방법에 대해 설명합니다.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8d78af13e0b3879afd0b6dae7b1a9ece651c3fd2
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2021
ms.locfileid: "8450946"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a>이집트에 대한 원천징수세 신고(EG-00005)

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a>개요
이 항목에서는 이집트의 법인에 대한 원천세 신고 및 원천세 신고 양식 41 및 11을 설정하고 생성하는 방법에 대해 설명합니다. 

모든 이집트 법인은 현지 공급업체 및 서비스 제공업체에서 보유하는 모든 세금을 요약한 양식 41을 준비해야 합니다. 양식 41 외에도 양식 11을 생성하여 외국 제공자로부터 과세되는 모든 보유세를 자세히 설명해야 합니다. 

Dynamics 365 Finance의 **원천징수 세금 신고** 보고서에는 다음과 같은 보고서가 포함되어 있습니다.

- 신고서 번호 41
- 신고서 번호 11
    
    
## <a name="prerequisites"></a>전제 조건
법인의 기본 주소는 이집트에 있어야 합니다.
**기능 관리** 작업 공간에서 다음 기능을 실행해야 합니다.

   - **전역 원천징수세**

기능을 활성화하는 방법에 대한 자세한 내용은 [기능 관리 개요](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하십시오.

1. **세금** >  **설정** >  **매개 변수** >  **일반원장 매개 변수** 로 이동한 후 **원천징수** 탭에서 **글로벌 원천징수 사용** 을 **예** 로 설정합니다.
2. **전자 보고** 작업 공간에서 리포지토리에서 다음 전자 보고 형식을 가져옵니다.

    - WHT 신고 Excel(EG)

    > [!NOTE]
    > 위의 형식은 **세금 신고 모델** 을 기반으로 하며 **세금 신고 모델 매핑** 을 사용합니다. 이 추가 구성은 자동으로 가져옵니다.

전자 보고 구성을 가져오는 방법에 대한 자세한 내용은 [Lifecycle Services에서 전자 보고 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)를 참조하십시오.

## <a name="download-electronic-reporting-configurations"></a>전자 보고 구성 다운로드

이집트에 대한 WHT 신고 양식의 구현은 전자 보고(ER) 구성을 기반으로 합니다. 구성 가능한 보고의 기능 및 개념에 대한 자세한 내용은 [전자 보고](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)를 참조하십시오.

운영 및 사용자 수용 테스트(UAT) 환경의 경우 [Lifecycle Services에서 전자 보고 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md) 항목의 지침을 따르십시오.

이집트 법인에서 원천징수 신고를 생성하려면 다음 구성을 업로드해야 합니다.

- 세금 신고 model.version.82.xml 이상 버전
- 세금 신고 모델 mapping.version.82.133.xml 이상 버전
- WHT 선언 Excel(EG).version.82.21 이상 버전

LCS(Lifecycle Services) 또는 글로벌 리포지토리에서 ER 구성 다운로드를 완료한 후 다음 단계를 완료하십시오.

1. **전자 보고** 작업 공간으로 이동하고 **보고 구성** 타일을 선택합니다.
1. **구성** 페이지의 작업 창에서 **Exchange > XML 파일에서 로드** 를 선택하십시오.
1. 이전 글머리 기호에 나열된 순서대로 모든 파일을 업로드합니다. 모든 구성이 업로드되면 구성 트리가 Finance에 있어야 합니다.

## <a name="set-up-application-specific-parameters"></a>애플리케이션별 매개 변수 설정

애플리케이션별 매개 변수 옵션을 통해 사용자는 원천징수 **세금 항목 그룹** 의 구성이나 조회 정의에 설정된 기타 기준에 따라 생성된 보고서의 각 행에서 세금 거래를 분류하고 계산하는 방법에 대한 기준을 설정할 수 있습니다.

원천징수 신고서 41에는 원천징수거래가 **할인 코드 유형** 이라는 세무당국의 구분에 따라 분류되어야 하는 특정란이 기재되어 있다. 트랜잭션이 게시될 때 이러한 새로운 분류를 새로운 항목 데이터로 포함하는 대신, 분류는 이집트에 대한 보고서 보류 요건을 충족하기 위해 **구성** > **애플리케이션별 매개 변수 설정** > **설정** 에 소개된 다양한 검색에 따라 결정됩니다. 

다음 구성은 원천징수 신고 양식 41 보고서에서 거래를 분류하는 데 사용됩니다.

- **DiscountTaxTypeLookup**-> 열18 

다음 단계를 완료하여 WHT 선언 및 관련 북 보고서를 생성하는 데 사용되는 다양한 조회를 설정합니다. 

1. **전자 보고** 작업 공간에서 **구성** >  **설정** 을 선택하여 WHT 선언 보고서에서 트랜잭션이 분류되는 방식을 식별하는 규칙을 설정합니다. 
2. 현재 버전을 선택하고 **조회** 빠른 탭에서 조회 이름을 선택합니다. 예를 들어 **DiscountTaxTypeLookup** 이 있습니다. 이 조회는 세무 당국에서 요구하는 할인 유형 목록을 식별합니다.
3. **조건** 빠른 탭에서 **추가** 를 선택하고 **조회 결과** 열의 새 줄에서 **열 18** 의 분류를 나타내는 관련 줄을 선택합니다.
4. **원천징수 세금 항목 그룹** 열에서 분류를 식별하는 데 사용되는 관련 코드를 선택합니다. 예를 들어 **허용된 할인** 입니다.  
5. 사용 가능한 모든 조회에 대해 3단계와 4단계를 반복합니다.
6. **추가** 를 다시 선택하여 최종 레코드 줄을 포함시키고 **조회 결과** 열에서 **적용되지 않음** 을 선택합니다. 
7. 나머지 열에서 **비어 있지 않음** 을 선택합니다. 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a>총계정원장 매개 변수 설정

Microsoft Excel에서 WHT 선언 양식 보고서를 생성하려면 **총계정원장 매개변수** 페이지에서 ER 형식을 정의하십시오.

1. **세금** > **설정** > **총계정원장 매개변수** 로 이동합니다.
2. **원천징수 세금** 탭의 **WHT 선언 형식 매핑** 필드에서 **WHT 선언 Excel(EG)** 을 선택합니다. 필드를 비워 두면 표준 판매세 보고서가 SSRS 형식으로 생성됩니다.


![신고서 양식.](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a>원천징수 신고서 생성
특정 기간에 대한 원천징수 신고서 작성 및 제출 프로세스는 세금 정산 및 후불 작업 중에 게시된 원천징수 거래를 기반으로 합니다. 글로벌 원천징수에 대한 자세한 내용은 [글로벌 원천징수세](../general-ledger/global-withholding-tax-overview.md)를 참조하십시오.

세금 신고 보고서를 생성하려면 다음 단계를 완료하십시오.

1. **세금** > **신고서** > **원천징수세** > **원천징수세 납부* 로 이동합니다.
2. 결산 기간을 선택한 다음 보고서의 시작 날짜를 선택합니다. 
3. 거래 날짜를 입력한 후 **확인** 을 선택합니다.
4. 열리는 대화상자에서 **양식 No 41**, **양식 No 11** 또는 **없음** 중 하나 이상을 선택합니다. **없음** 을 선택하면 표준 보고서가 생성됩니다. 
5. 언어를 선택합니다. 모든 보고서는 **en-us** 및 **ar-eg** 로 번역됩니다.
6. 세금을 납부할 은행의 지점과 이름을 입력합니다.
7. 비즈니스 유형을 선택한 다음 수표 및 문서 번호를 입력합니다. 
8. 업체 유형을 입력합니다. 
9. 양식을 할당하기 위해 등록된 사용자의 이름을 입력하고 **확인** 을 선택하여 보고서 생성을 확인합니다. 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
