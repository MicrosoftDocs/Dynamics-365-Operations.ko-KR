---
title: Financial Reporting 개요
description: 이 항목에서는 Microsoft Dynamics 365 Finance에서 Financial Reporting에 액세스하는 위치와 Financial Reporting 기능을 사용하는 방법을 설명합니다.
author: aprilolson
ms.date: 07/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1fbdab1f4f81bbdb8b0b5cb3e6a5237196d7dc76
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451417"
---
# <a name="get-started-with-financial-reporting"></a>Financial Reporting 시작 

[!include [banner](../includes/banner.md)]

이 항목에서는 Financial Reporting에 액세스하는 위치와 Financial Reporting 기능을 사용하는 방법을 설명합니다. 여기에는 제공되는 기본 재무 보고서에 대한 설명도 포함됩니다.

## <a name="accessing-financial-reporting"></a>Financial Reporting 액세스

**Financial Reporting** 메뉴는 다음 위치에서 찾을 수 있습니다.

- **총계정원장** &gt; **문의 및 보고**
- **예산 책정** &gt; **문의 및 보고** &gt; **기본 예산 책정**
- **예산 책정** &gt; **문의 및 보고** &gt; **예산 계획**
- **예산 책정** &gt; **문의 및 보고** &gt; **예산 통제**
- 통합

법인에 대한 재무 보고서를 만들고 생성하려면 해당 법인에 대한 다음 정보를 설정해야 합니다.

- 회계 달력
- 원장
- 계정 차트
- 통화
- 하나 이상의 계정에 거래 게시
- MainAccount는 **Financial Reporting 설정** 페이지(**총계정원장 > 원장 설정 > Financial Reporting 설정**)의 **선택됨** 열에 나열됩니다.

## <a name="granting-security-access-to-financial-reporting"></a>Financial Reporting에 대한 보안 액세스 권한 부여

Financial Reporting 기능은 보안 역할을 통해 적절한 권한과 의무가 할당된 사용자가 사용할 수 있습니다. 다음 섹션에는 관련 역할과 이러한 권한 및 의무가 나열되어 있습니다.

### <a name="duties"></a>의무

| 의무 레이블                            | 설명                                                             | AOT 이름                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Financial Reporting 보안 유지 | Financial Reporting 보안을 유지하고 관리 작업을 수행합니다. | FinancialReportsSecurityMaintain |
| 재무 보고서 유지            | 재무 보고서를 디자인하고 유지합니다.                                  | FinancialReportsMaintain         |
| 재무 보고서 생성            | 재무 보고서를 생성하고 새로 고칩니다.                                 | FinancialReportsGenerate         |
| 재무 성과 검토          | 재무 성과를 검토하고 분석합니다.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>권한

| 권한 레이블                       | 설명                                                             | AOT 이름                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Financial Reporting 보안 유지 | Financial Reporting 보안을 유지하고 관리 작업을 수행합니다. | FinancialReportsSecuritySystemMaintain |
| 재무 보고서 유지            | 재무 보고서를 디자인하고 유지합니다.                                  | FinancialReportsMaintainReports  |
| 재무 보고서 생성            | 재무 보고서를 생성하고 새로 고칩니다.                                 | FinancialReportsGenerateReports  |
| 재무 보고서 보기                | 재무 보고서를 봅니다.                                                 | FinancialReportsView             |

### <a name="roles"></a>역할

| 권한 레이블                       | 의무                                  | 역할                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Financial Reporting 보안 유지 | Financial Reporting 보안 유지 | 보안 관리자                                                          |
| 재무 보고서 유지            | 재무 보고서 유지            | 회계 관리자, 회계 감독자, 재무 관리자, 예산 관리자 |
| 재무 보고서 생성            | 재무 보고서 생성            | CEO, CFO, 회계사                                                            |
| 재무 보고서 보기                | 재무 성과 검토          | 할당되지 않음                                                                   |

사용자가 추가되거나 역할이 변경된 후 사용자는 몇 분 이내에 Financial Reporting에 액세스할 수 있습니다. 

> [!NOTE]
> sysadmin 역할은 Financial Reporting의 모든 역할에 추가됩니다.

## <a name="report-deletions-and-expirations"></a>보고서 삭제 및 만료

보고서를 생성한 사용자는 자기 보고서를 삭제할 수 있습니다. **Financial Reporting 보안 유지** 의무가 있는 사용자는 다른 사람의 보고서를 삭제할 수 있습니다. 

릴리스 10.0.8에 만료 날짜의 개념이 도입되었습니다. 기능 관리 작업 영역 내의 **모든** 페이지에서 새로운 필수 기능이 활성화됩니다. **재무 보고서 보존 정책** 기능에는 다음 변경 사항이 포함됩니다.
* 새로 생성된 보고서는 생성일로부터 90일의 만료 날짜가 자동으로 표시됩니다.
* 기능이 설치되기 전의 기존 보고서에는 90일의 만료 기간이 주어집니다. Financial Reporting 서비스가 실행되고, 보고서가 생성되며, 서비스가 만료 날짜 없는 기존 보고서를 업데이트할 때까지 날짜가 잠시 공백으로 표시될 수 있습니다. 
* **Financial Reporting 보안 유지** 를 가진 사용자는 이 기능에 액세스할 수 있습니다. **재무 보고서 만료 유지** 권한이 부여되고 **재무 보고서 유지** 의무를 수행하는 사용자는 만료 기간을 수정할 수도 있습니다. 현재 두 가지 보존 옵션을 사용할 수 있습니다. 

    * 90일의 만료 기간.
    * 보고서가 만료되지 않도록 설정하는 옵션.

90일과 같은 만료 기간을 선택하면 오늘로부터 90일 동안 적용됩니다. 이것은 보고서가 생성될 때 설정된 원래 생성 날짜로부터 90일과는 다른 동작입니다. 

추가 옵션은 향후 기능에서 고려됩니다. 기본값은 90일 만료이며 적절한 권한이 있는 사용자는 **재무 보고서** 목록 페이지에서 기본값을 무시할 수 있습니다.

## <a name="default-reports"></a>기본 보고서

Financial Reporting은 22개의 기본 재무 보고서를 제공합니다. 모든 보고서는 기본 주 계정 범주를 사용합니다. 이러한 보고서를 그대로 사용하거나 Financial Reporting 요구를 충족하는 시작점으로 사용할 수 있습니다. 이러한 기본 보고서에는 손익 계산서 및 대차 대조표와 같은 기존 재무제표 외에도 만들 수 있는 다양한 유형의 재무 보고서를 보여주는 보고서가 포함됩니다. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| 기본 보고서                                                                                         | 설명                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 12개월 수시 단일 열 손익 계산서 – 기본값 | 단일 열에서 지난 12개월 동안 조직의 수익성을 봅니다.                                                                                                                                                                                                                                      |
| 12개월 추세 손익 계산서 – 기본값                 | 지난 12개월 동안 각 조직의 수익성을 봅니다. 이 12개월은 두 회계 연도에 걸쳐 있을 수 있습니다.                                                                                                                                                                                             |
| 실제 대 예산 – 기본값                                | 원래 예산에 대한 모든 계정의 자세한 잔액 정보를 보고 수정 예산을 차이가 있는 실제와 비교합니다.                                                                                                                                                                          |
| 감사 세부 정보 – 기본값                                  | 모든 계정의 자세한 잔액 정보를 봅니다. 이 보고서는 사용자 ID, 데이터를 마지막으로 수정한 사용자, 마지막 수정 날짜 및 분개장 ID와 같은 추가 거래 정보와 함께 보고 통화 및 현지 통화로 출금 및 입금 잔액을 표시합니다. |
| 잔액 목록 – 기본값                                   | 모든 계정의 자세한 잔액 정보를 봅니다. 이 보고서는 바우처와 같은 추가 거래 정보와 함께 현재 기간 및 연도 누계의 개시 및 마감 잔액, 출금 및 입금 잔액을 보여줍니다.                                                                    |
| 대차 대조표 – 기본값                                   | 해당 연도의 조직 재무 상태를 봅니다.                                                                                                                                                                                                                                                             |
| 대차 대조표 및 손익 계산서 나란히 – 기본값 | 조직의 재무 상태와 해당 연도의 수익성을 나란히 봅니다.                                                                                                                                                                                                                              |
| 현금 흐름 – 기본값                                       | 조직의 현금 유입과 유출에 대한 통찰력을 얻습니다.                                                                                                                                                                                                                                   |
| 자세한 JE 및 TB 검토 – 기본값                      | 모든 계정에 대한 개시 잔액 및 활동 정보를 봅니다.                                                                                                                                                                                                                                                      |
| [상세 시산표 - 기본값](trial-balance-financial-reports.md)| 차변 및 신용 잔액이 있는 모든 계정의 잔액 정보와 이러한 순 잔액을 거래 날짜, 바우처 및 분개장 설명과 함께 봅니다.                                                                                                                                  |
| 비용 3년 분기별 추세 – 기본값             | 지난 3년에 걸쳐 12분기 동안의 비용에 대한 통찰력을 얻습니다.                                                                                                                                                                                                                                   |
| 재무 캡션 JE 및 TB 검토 – 기본값            | 자산, 부채, 자기 자본, 매출, 비용, 이익 또는 손실 재무 캡션에 대한 잔액 및 활동에 대한 개요를 봅니다.                                                                                                                                                                           |
| [손익 계산서 – 기본값](income-statement-financial-report.md)| 현재 기간 및 연도 누계의 조직 수익성을 봅니다.                                                                                                                                                                                                                                   |
| 원장 거래 목록 – 기본값                        | 모든 계정의 자세한 잔액 정보를 봅니다. 이 보고서는 거래 날자, 분개장 번호, 바우처, 게시 유형 및 추적 번호와 같은 추가 거래 정보와 함께 출금 및 입금 잔액을 보여줍니다.                                                                            |
| 비율 – 기본값                                          | 해당 연도 조직의 지급 능력, 수익성 및 효율성 비율을 봅니다.                                                                                                                                                                                                                           |
| 수시 12개월 비용 – 기본값                       | 지난 12개월 동안 각 지출에 대한 통찰력을 얻습니다. 이 12개월은 두 회계 연도에 걸쳐 있을 수 있습니다.                                                                                                                                                                                                       |
| 수시 분기 손익 계산서 – 기본값               | 작년 및 연도 누계에 조직의 분기별 수익성을 봅니다.                                                                                                                                                                                                                   |
| 대차 대조표 나란히 – 기본값                      | 해당 연도의 조직 재무 상태를 봅니다. 이 보고서는 자산과 부채, 주주 지분을 나란히 표시합니다.                                                                                                                                                                                |
| [요약 시산표 – 기본값](trial-balance-financial-reports.md)| 개시 및 마감 잔액, 출금 및 입금 잔액이 있는 모든 계정에 대한 잔액 정보를 순 차액과 함께 봅니다.                                                                                                                                                                  |
| [연간 요약 시산표 – 기본값](trial-balance-financial-reports.md)| 현재 연도와 이전 연도의 개시 및 마감 잔액, 출금 및 입금 잔액이 있는 모든 계정에 대한 잔액 정보를 순 차액과 함께 봅니다.                                                                                                                           |
| 주간 판매 및 할인 – 기본값                     | 한 달의 매주 판매 및 할인에 대한 통찰력을 얻습니다. 이 보고서에는 총 4주가 포함됩니다.                                                                                                                                                                                                              |
| 사용 가능한 예산 자금 – 기본값                         | 모든 계정에서 사용 가능한 수정 예산, 실제 지출, 예산 예약 및 예산 자금의 세부 비교를 봅니다.                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>재무 보고서 열기

**Financial Reporting** 메뉴를 선택하면 해당 회사의 기본 재무 보고서 목록이 표시됩니다. 그런 다음 보고서를 열거나 수정할 수 있습니다. 기본 보고서 중 하나를 열려면 보고서 이름을 선택합니다. 보고서를 처음 열면 자동으로 이전 달에 대해 생성됩니다. 예를 들어 2019년 8월에 보고서를 처음 여는 경우 2019년 7월 31일에 대한 보고서가 생성됩니다. 보고서를 연 후 특정 데이터를 드릴다운하고 보고서 옵션을 변경하여 보고서 탐색을 시작할 수 있습니다.

## <a name="creating-and-modifying-financial-reports"></a>재무 보고서 만들기 및 수정

재무 보고서 목록에서 새 보고서를 만들거나 기존 보고서를 수정할 수 있습니다. 적절한 권한이 있는 경우 작업 창에서 **새로 만들기** 를 선택하여 새 재무 보고서를 만들 수 있습니다. Report Designer 프로그램이 장치에 다운로드됩니다. Report Designer가 시작된 후 새 보고서를 만들 수 있습니다. 새 보고서를 저장하면 재무 보고서 목록에 나타납니다. 목록에는 Dynamics 365 Finance에서 사용 중인 회사에 대해 생성된 보고서만 표시됩니다. 

## <a name="reporting-tree-definitions"></a>보고 트리 정의

재무 보고서를 작성하는 데 사용되는 구성 요소 중 하나는 보고 트리 정의입니다. 보고 트리 정의는 조직의 구조와 계층 구조를 정의하는 데 도움이 됩니다. 이는 재무 데이터의 차원 관계에 기반을 두는 교차 차원 계층 구조입니다. 보고 단위 수준 및 트리의 모든 단위에 대한 요약 수준의 정보를 제공합니다.

보고 트리를 무제한으로 생성하여 조직의 데이터를 다양한 방식으로 표시할 수 있습니다. 각 보고 트리에는 부서와 요약 단위의 조합이 포함될 수 있지만 보고서 정의는 한 번에 하나의 보고 트리에만 연결할 수 있습니다. 

## <a name="update-the-financial-reporting-version-through-slipstreaming"></a>슬립스트리밍을 통해 Financial Reporting 버전 업데이트

금융 및 운영 앱은 매달 업데이트됩니다. 그러나 Financial Reporting이 반드시 해당 주기에 따라 업데이트되는 것은 아닙니다. 또한 고객은 금융 및 운영 앱에 대한 업데이트를 구현하는 시기에 대해 더 많은 옵션을 선택할 수 있습니다. Financial Reporting 업데이트는 자동으로 설치됩니다. Financial Reporting에는 서비스 업데이트가 구현될 때, 가동 중지 시간이 시작될 때 또는 고객 환경이 유지 관리 모드일 때 고객 환경에서 사용되는 지정된 버전이 있습니다. 모든 고객 구현이 동일한 버전의 Financial Reporting으로 설정되기 때문에 이 프로세스를 *슬립스트리밍* 또는 *트루업* 이라고 합니다.

각 버전에서 릴리스된 변경 사항은 [Dynamics 365 Finance의 새로운 기능 또는 변경된 기능](../../finance/get-started/whats-new-home-page.md)에서 찾을 수 있습니다. 플랫폼 업데이트 및 버그 수정은 각 릴리스에 대한 페이지 하단의 "추가 리소스" 섹션에서 찾을 수 있습니다.

선택한 슬립스트림 버전은 프로덕션 준비가 된 Financial Reporting의 검토되고 검증된 버전입니다. Dynamics 365 Finance의 이전 또는 이후 버전과 호환됩니다. 예를 들어 Financial Reporting은 최신 10.0.19 빌드이고 고객은 여전히 애플리케이션 버전 10.0.16을 사용할 수 있습니다.

> [!NOTE]
> 고객이 이전 버전으로 이동할 수 있는 유일한 상황(다운그레이드 시나리오)은 Microsoft가 문제로 인해 트루업 롤아웃을 중단하는 경우입니다. 수정 사항이 제공되는 즉시 자동으로 적용됩니다.

슬립스트림 프로세스는 완전히 자동화되며 고객의 조치가 필요하지 않습니다. 세 가지 토폴로지는 각각 약간 다른 방식으로 슬립스트림을 사용합니다.

- **온-프레미스** – 온프레미스 배포는 슬립스트림 및 트루업을 지원하지 않습니다.
- **서비스 제공 인프라(IaaS)** – Financial Reporting 업데이트를 시도하는 모든 작업 중에 슬립스트림 논리가 적용됩니다. 여기에는 이진 업데이트 또는 이진 업데이트를 포함한 브로드캐스트가 포함됩니다.
- **셀프 서비스** – Financial Reporting 가동 중지 시간이 필요한 모든 작업이 슬립스트림 논리를 적용합니다.

    - 이진 업데이트 또는 이진 업데이트를 포함한 브로드캐스트
    - S 패치 또는 기타 인프라 가동 중지 시간
    - AOT 패키지 배포

## <a name="troubleshooting-issues-opening-report-designer"></a>Report Designer를 여는 문제 해결

Report Designer를 열 때 문제를 일으킬 수 있는 몇 가지 일반적인 사항이 있습니다. 이러한 문제점과 해결 방법은 다음과 같습니다.

문제 1: **새로 만들기** 또는 **편집** 을 선택하면 Report Designer가 시작되지 않습니다.

* Internet Explorer에서 **설정** 을 선택한 다음 **인터넷 옵션** 을 선택합니다. **보안** 탭을 선택하고 신뢰할 수 있는 사이트를 선택한 다음 **사이트** 를 선택합니다. **영역에 웹 사이트 추가** 에서 "\*\.dynamics.com"을 입력하고(따옴표 제외) **추가** 를 선택합니다. 
* Internet Explorer에서 **설정** 을 선택한 다음 **인터넷 옵션** 을 선택합니다. **보안** 탭을 선택하고 신뢰할 수 있는 사이트를 선택합니다. 이 영역의 보안 수준이라고 표시된 영역에서 옵션을 **보통 낮음** 으로 변경합니다.
* 브라우저에서 팝업 차단기를 비활성화합니다.
* 워크스테이션에 Microsoft .NET Framework 4.6.2 이상을 설치해야 합니다. 이 버전의 Microsoft .NET 프레임워크는 [Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=53345)에서 다운로드하고 설치할 수 있습니다.
* Chrome 브라우저를 사용하는 경우 ClickOnce 확장을 설치해야 Report Designer 클라이언트를 다운로드할 수 있습니다. Chrome을 시크릿 모드로 실행하는 경우 시크릿 모드에 ClickOnce 확장이 활성화되어 있는지 확인합니다. Chrome ClickOnce 확장에 대한 자세한 내용은 [클라우드 배포를 위한 시스템 요구 사항](../../fin-ops-core/fin-ops/get-started/system-requirements.md)을 참조하세요.
* Chrome 브라우저에서 Microsoft Edge를 사용하는 경우 Edge Chromium용 ClickOnce 확장을 설치할 필요가 없습니다. 그러나 Report Designer 클라이언트를 다운로드하려면 ClickOnce 옵션을 활성화해야 합니다. 시크릿 모드로 실행하는 경우 시크릿 모드에 ClickOnce 확장이 활성화되어 있는지 확인합니다.

    1. Microsoft Edge에서 새 브라우저를 엽니다.
    2. **edge://flags** 를 입력하고 **Enter** 를 누릅니다.
    3. **ClickOnce 지원** 옵션을 찾거나 이 직접 링크 **edge://flags/#edge-click-once** 를 사용합니다.
    4. 드롭다운 메뉴 옵션을 **사용** 으로 설정합니다.
    5. **브라우저 재시작** 을 선택합니다.

문제 2: 사용자에게 Financial Reporting을 사용하는 데 필요한 사용 권한이 할당되지 않았습니다. 

* 사용자에게 사용 권한이 없는지 확인하려면 "Financial Reporting 서버에 연결할 수 없습니다. 계속하고 다른 서버 주소를 지정하려면 예를 선택하세요." 오류에서 **예** 를 선택합니다. 그런 다음 **연결 테스트** 를 선택합니다. 사용 권한이 없으면 "연결 시도에 실패했습니다. 사용자에게 서버에 연결할 적절한 사용 권한이 없습니다. 시스템 관리자에게 문의하세요."라는 메시지가 표시됩니다.
* 필요한 사용 권한은 [Financial Reporting에 대한 보안 액세스 권한 부여](#granting-security-access-to-financial-reporting)에 나열되어 있습니다. Financial Reporting의 보안은 이러한 사용 권한을 기반으로 합니다. 이러한 사용 권한(또는 이러한 사용 권한을 포함하는 다른 보안 역할)이 할당되지 않으면 액세스할 수 없습니다. 
* **회사 사용자 공급자와 회사 간** 통합 작업(사용자 통합이라고도 함)은 5분 간격으로 실행됩니다. Financial Reporting에 사용 권한 변경이 적용되는 데 최대 10분이 소요될 수 있습니다. 

    다른 사용자가 Report Designer를 열 수 있는 경우 **도구** 를 선택한 다음 **통합 상태** 를 선택합니다. Financial Reporting을 사용할 수 있는 사용 권한이 할당되었으므로 "회사 사용자 공급자와 회사 간" 통합 맵이 실행되었는지 확인합니다. 

* 다른 오류로 인해 **Dynamics 사용자와 Financial Reporting 사용자 간 통합** 이 완료되지 않았을 수 있습니다. 또는 데이터 마트 재설정이 시작되었지만 아직 완료되지 않았거나 다른 시스템 오류가 발생했을 수 있습니다. 나중에 프로세스를 다시 실행해 보세요. 문제가 지속되면 시스템 관리자에게 문의하세요.

문제 3: **ClickOnce Report Designer** 로그인 페이지를 진행할 수 있지만 Report Designer에서 로그인을 완료할 수 없습니다. 

* 로그인 자격 증명을 입력할 때 로컬 컴퓨터에 설정된 시간과 Financial Reporting 서버의 시간의 차이는 5분 이내여야 합니다. 5분 이상 차이가 있으면 시스템은 로그인을 허용하지 않습니다. 
* 컴퓨터의 시간이 Financial Reporting 서버의 시간과 다른 경우 컴퓨터 시간을 자동으로 설정하는 Windows 옵션을 활성화하는 것이 좋습니다. 

## <a name="troubleshoot-report-designer-issues-with-event-viewer"></a>이벤트 뷰어로 Report Designer 문제 해결

이벤트 뷰어를 사용하여 Financial Reporting을 사용할 때 발생하는 몇 가지 문제를 분석할 수 있습니다. 

### <a name="what-happens-when-you-have-connections-issues-with-financial-reporting"></a>Financial Reporting에 연결 문제가 있는 경우 어떻게 해야 합니까? 

다음은 Microsoft 지원과 대화를 더 효율적으로 진행하고 더 빠른 해결을 위해 취할 수 있는 몇 가지 단계입니다. 
 
다음 단계는 Financial Reporting에 대한 이벤트 뷰어 메시지를 설정하는 프로세스를 안내합니다. 이벤트 뷰어가 생성하는 로그는 지원 엔지니어가 연결 문제의 원인을 신속하게 식별하는 데 도움이 됩니다. 지원에 문의할 때 티켓과 함께 이 로그의 사본을 제출하세요.


1. RegisterETW.zip 파일을 클라이언트 워크스테이션(데스크톱 선호)에 복사하고 [RegisterETW.zip](https://dev.azure.com/msdyneng/e6f12261-a46a-4af1-ac0c-e22bc2c5a478/_apis/git/repositories/ff923027-67f0-43fb-b63c-6d6b6423840f/Items?path=%2F.attachments%2FRegisterETW-c1a35291-6aa6-4462-a2bc-4ba117fd5f8e.zip&download=false&resolveLfs=true&%24format=octetStream&api-version=5.0-preview.1&sanitize=true&versionDescriptor.version=wikiMaster)의 압축을 풉니다.
2. Windows 이벤트 뷰어가 닫혀 있는지 확인합니다.
3. 관리자 PowerShell 명령 프롬프트를 열고 RegisterETW.ps1이 있는 디렉터리로 이동합니다.
4. .\RegisterETW.ps1 명령을 실행합니다.

    **RegisterETW 스크립트 완료** 메시지로 PowerShell의 출력을 확인합니다.

    이벤트 뷰어를 다시 열면 **Microsoft > Dynamics** 아래에 다음과 같은 로그가 표시됩니다.

    * MR-Client
    * MR-DVT
    * MR-Integration
    * MR-Logger
    * MR-Reporting
    * MR_SchedulerTasks
    * MR-Sql
    * MR-TraceManager

5. Report Designer에서 문제를 재현합니다.
6. 이벤트 뷰어를 사용하여 MR-Logger 이벤트를 내보냅니다.

## <a name="troubleshoot-issues-connecting-to-financial-reporting"></a>Financial Reporting 연결 문제 해결

문제: "Financial Reporting 서버에 연결할 수 없습니다." 오류가 표시됩니다.

* Chrome 및 Edge 인터넷 브라우저에서 문제가 발생하는지 확인합니다.
* 문제가 한 브라우저에서만 발생하는 경우 ClickOnce 문제일 수 있습니다. 
* 연결 오류 메시지가 표시되면 **테스트** 를 선택하여 연결을 테스트하고 어떤 메시지가 나타나는지 확인합니다. 
* 이 문제는 다른 사용자가 Financial Reporting에 액세스하지 못한 결과일 수 있습니다. 사용자에게 액세스 권한이 없으면 사용 권한이 없다는 메시지가 표시됩니다.
* 여러 브라우저에서 문제가 발생하는 경우 워크스테이션의 시간 기록계가 자동으로 설정되어 있는지 확인합니다.
* Dynamics 365 Finance의 보안 관리자 권한과 네트워크 도메인에 대한 관리자 권한이 있는 사용자와 협력하여 워크스테이션에 로그인하여 연결할 수 있는지 확인하세요. 이러한 사용자가 연결할 수 있다면 문제는 네트워크 사용 권한과 관련이 있을 수 있습니다.
* 워크스테이션에서 방화벽을 일시적으로 비활성화합니다. 그런 다음 Report Designer에 연결할 수 있다면 방화벽에 문제가 있는 것입니다. 조직의 IT 부서와 협력하여 문제를 해결합니다.

## <a name="additional-resources"></a>추가 리소스

- [재무 보고 보기](view-financial-reports.md)
- [재무 보고서의 보고 트리 정의](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
