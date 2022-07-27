---
title: 혜택 관리에서 Affordable Care Act 보고서 생성
description: 이 항목에서는 혜택 관리 부서에서 Affordable Care Act(ACA) 고용주 권한에 대해 양식 1095-B 및 양식 1095-C에 보고된 정보를 추적하는 방법에 대해 설명합니다.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 79bd8e02aeac1be94e735373740cf9508f494a06
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452185"
---
# <a name="generate-aca-reports-in-benefits-management"></a>혜택 관리에서 ACA 보고서 생성


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

혜택 관리는 Affordable Care Act(ACA) 고용주 권한에 대해 양식 1095-B 및 양식 1095-C에 보고된 정보를 추적합니다. 이전 **혜택** 작업 공간의 ACA 보고 기능과 마찬가지로 이 기능은 미국의 법인에만 적용됩니다.

이 기능을 사용하려면 먼저 **고급 혜택 관리** 를 켜야 합니다. 혜택 관리에 대한 중요한 주의 사항을 포함하여 자세한 내용은 [혜택 관리 활성화 또는 비활성화](hr-admin-manage-features.md#enable-or-disable-benefits-management)를 참조하십시오.

> [!IMPORTANT]
> ACA 보고 기능은 **혜택 관리** 작업 공간 또는 이전 **혜택** 작업 공간에서만 사용할 수 있으며 두 가지 모두에서 사용할 수는 없습니다. 예를 들어, 혜택 관리로 전환한 경우 ACA 보고 기능은 이전 **혜택** 작업 공간이 아닌 **혜택 관리** 작업 공간에서만 사용할 수 있습니다.
>
> 등록 연도 중간에 혜택 관리로 전환할 경우 혜택 관리에서 전체 연도의 직원 데이터를 올바르게 구성해야 합니다. 이렇게 하면 한 해 동안 정확한 보고 정보를 받을 수 있습니다.

## <a name="getting-started"></a>시작하기

1095 양식에 대한 정보를 추적하려면 먼저 하나 이상의 Affordable Care 서비스 그룹을 만듭니다. 이러한 그룹은 다음 정보를 나타냅니다.

- 직원에게 제공된 보장 제안
- 비용이 연방 빈곤선을 초과하는 경우 최저 월 보험료에 대한 직원의 몫
- 해당되는 경우, 고용주가 사용하는 세이프 하버

Affordable Care 보장 그룹은 동일한 조건을 가진 여러 직원 기록에 대한 이 정보를 관리하는 데 도움이 됩니다. 한 명 이상의 직원에게 그룹을 쉽게 할당할 수 있습니다.

### <a name="create-or-edit-an-affordable-care-coverage-group"></a>Affordable Care 보장 그룹 생성 또는 편집

1. **혜택 관리** 작업 공간에서 **Affordable Care 보장 그룹** 을 선택합니다.

    ![Affordable Care 보장 그룹을 선택합니다.](./media/hr-benefits-management-aca-coverage-group.png)

2. **새로 만들기** 를 선택하여 새 Affordable Care 보장 그룹을 만들거나 **편집** 을 선택하여 기존 그룹을 변경합니다.

    ![새로 만들기 또는 편집을 선택합니다.](./media/hr-benefits-management-aca-new.png)

3. 다음 필드를 설정합니다.

    | 필드 | 설명 |
    |---|---|
    | 이름 | 그룹 이름을 입력합니다. |
    | 설명 | 그룹에 대한 설명을 입력합니다. |
    | 보장 범위 제공 | 직원, 배우자 또는 파트너 및 부양가족에게 제공되는 보상 범위입니다. |
    | 직원 비용 분담금 | 직원이 책임지는 금액입니다. |
    | 적용 섹션 4980H 세이프 하버 | 4980H 세이프 하버 또는 전환 구제 코드입니다. |
    | 계획 시작 월 | 혜택 계획 연도가 시작되는 월을 선택합니다. |
    | 그룹 유효 기간 시작 | 이 레코드가 유효한 첫 번째 날짜입니다. |
    | 그룹 유효 기간 종료 | 이 레코드가 유효한 마지막 날짜입니다. 만료 날짜가 없으면 **없음** 을 입력합니다. |

    ![보장 그룹을 만듭니다.](./media/hr-benefits-management-aca-new-group.png)

4. **저장** 을 선택합니다.

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a>Affordable Care 서비스 그룹에 여러 직원을 할당합니다.

1. **혜택 관리** 작업 공간에서 **Affordable Care 보장 그룹** 을 선택합니다.
2. 직원을 할당할 그룹을 선택합니다.
3. **대량 할당** 을 선택합니다.

    ![대량 할당을 선택합니다.](./media/hr-benefits-management-aca-mass-assignment.png)

4. 목록에서 직원을 선택한 다음 **할당** 을 선택합니다.

    ![선택한 직원을 그룹에 할당합니다.](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a>여러 버전의 보장 옵션 유지

모든 보장 그룹의 여러 버전을 유지할 수 있습니다. 조직에서 변경되거나 제공되는 혜택이 있는 경우 새 그룹을 만들고 해당 그룹에 직원을 재할당하지 않고도 그룹 정보를 최신 상태로 유지할 수 있습니다.

Affordable Care 보장 그룹을 만든 후에는 해당 그룹에 직원을 대량 할당할 수 있습니다. 또한 그룹에 직원을 개별적으로 할당하고 ACA 정보가 추적 및 보고되는지 여부를 지정할 수 있습니다.

직원의 ACA 정보를 추적하고 보고할 필요가 없는 경우 **보고서 적용 범위** 옵션을 **아니요** 로 설정할 수 있습니다. 예를 들어, ACA 보고가 필요하지 않은 시간제 직원이 있을 수 있습니다.

### <a name="override-default-values-for-an-employee"></a>직원의 기본값 무시

Affordable Care 보장 범위에 할당된 직원의 경우 다른 값이 필요한 월에 대해 다음 옵션을 변경할 수 있습니다.

- 보장 범위 제공
- 직원 비용 분담금
- 적용 섹션 4980H 세이프 하버

> [!NOTE]
> 2020 ACA 보고서의 경우, 직장 및 가정 우편 번호를 모두 양식 1095-C에 신고해야 합니다. 현재 활성 위치를 기준으로 값이 자동으로 채워집니다. 연도 중 어느 한 위치가 달라진 경우 값을 재정의해야 합니다. 1095-C 보고서의 **ZIP 코드** 필드(17행)는 다음과 같이 **보장 제공** 코드에 **1L** ~ **1Q** 가 포함된 경우에만 생성됩니다.
>
> - **1L, 1M 또는 1N:** 주 거주지 우편번호
> - **1O, 1P, 1Q:** 주 직장 우편 번호

Affordable Care 보장 그룹의 값에 대한 예외를 입력하려면 다음 단계를 따르십시오.

1. **인사 관리** 작업 영역에서 **연결** 을 선택한 다음 **작업자** 를 선택합니다.
2. 목록에서 직원을 선택합니다.
3. **고용** 탭의 **추가 정보** 섹션에서 **Affordable Care 보장** 을 선택합니다.

    ![직원 한 명에 대한 옵션을 변경합니다.](./media/hr-benefits-management-aca-change-single-employee.png)

4. **편집** 을 선택합니다.
5. 변경이 필요한 각 달에 대해 **기본값 재정의** 확인란을 선택한 다음 필요에 따라 다른 값을 변경합니다.

    ![기본값을 재정의합니다.](./media/hr-benefits-management-aca-override-default.png)

6. **저장** 을 선택합니다.

## <a name="report-health-care-coverage"></a>의료 서비스 범위 보고

정규직 및 비상근 직원을 위한 고용주가 후원하는 자체 보험 의료 보험 적용 범위를 추적해야 합니다. 각 직원을 부양가족과 함께 1095-C 보고서에 포함시키십시오.

혜택 계획을 보고해야 하는지 여부를 나타내려면 다음 단계를 따르십시오.

1. **혜택 관리** 작업 공간에서 **혜택 계획** 을 선택합니다.
2. 보고할 혜택 계획을 선택합니다.
3. **편집** 을 선택합니다.
4. **Affordable Care Act에 따라 보고됨** 옵션을 **예** 로 설정합니다.

    ![의료 서비스 보장을 보고합니다.](./media/hr-benefits-management-aca-report-coverage.png)

5. **저장** 을 선택합니다.

직원이 부양가족에 대한 의료보험 혜택을 선택한 경우, 부양가족의 보장기간은 부양가족이 등록되거나 제외된 날짜에 따라 결정됩니다. 부양가족에 대한 적용 일자는 부양가족이 등록 연도 동안 계획에서 자격이 있고 활성 상태였던 기간을 기준으로 자동으로 계산됩니다.

## <a name="generate-1095-b-and-1095-c-forms"></a>1095-B 및 1095-C 양식 생성

ACA 1095-B 및 1095-C 양식을 생성한 후 각 직원에게 배포할 수 있습니다. 또한 양식 1095-C 및 해당 1094-C 전송 파일을 전자적으로 생성하여 IRS(내부 세무 서비스)로 전송할 수 있습니다.

1. **혜택 관리** 작업 공간에서 **ACA 1095-B 양식** 또는 **ACA 1095-C 양식** 을 선택합니다.
2. 필요에 따라 매개 변수를 변경한 다음 **확인** 을 선택합니다.

    > [!NOTE]
    > 500명 이상의 직원을 대상으로 1095-C 양식을 인쇄하는 경우 둘 이상의 PDF 파일을 받게 됩니다. **문서 관리 매개 변수** 페이지의 **최대 파일 크기(MB)** 필드 값을 **150** 으로 늘리는 것이 좋습니다. (페이지를 빠르게 열려면 탐색 모음의 검색 필드를 사용하십시오.)
    >
    > ![최대 파일 크기를 변경합니다.](./media/hr-benefits-management-aca-maximum-file-size.png)

3. 보고서 상태를 확인하고 보려면 탐색 모음의 검색 필드를 사용하여 **전자 보고 작업** 페이지를 여십시오.

    ![전자 보고 작업 페이지를 검색합니다.](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. 보려는 보고서를 선택한 다음 **파일 표시** 를 선택합니다.

    ![파일을 표시합니다.](./media/hr-benefits-management-aca-show-files.png)

5. **열기** 를 선택합니다.

    ![파일을 엽니다.](./media/hr-benefits-management-aca-open-file.png)

6. 브라우저 창의 맨 아래에 나타나는 알림 표시줄에서 zip 파일을 열고 보고서를 선택합니다. PDF 파일을 보거나 인쇄할 수 있습니다.

    ![샘플 1095-C 양식.](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a>ACA 보장 범위 보기

**직원 Affordable Care 보장** 페이지에는 다음 정보가 표시됩니다.

- 각 보장 그룹에 할당된 직원
- 보고서에 포함될 필요가 없는 직원
- 할당되지 않은 직원

이 정보를 보려면 다음 단계를 따릅니다.

1. **혜택 관리** 작업 공간에서 **직원 Affordable Care 보장** 을 선택합니다.
2. **그룹 이름** 필드에서 그룹을 선택합니다.

    ![ACA 보장을 봅니다.](./media/hr-benefits-management-aca-view-coverage.png)

Affordable Care 보장 그룹의 기본값을 재정의한 경우 변경된 값 옆에 별표가 나타납니다. 모든 12개월에 대한 값이 동일하고 재정의되지 않은 경우 **모든 12개월** 열에 값이 표시됩니다.

ACA 보고 불가로 표시된 직원과 양식 1095-C가 필요하지 않은 직원을 볼 수 있습니다. **필터 기준** 필드에서 **보고 가능한 ACA 없음** 을 선택합니다.

그룹에 할당되지 않았거나 만료된 그룹에 할당된 직원을 볼 수 있습니다. **필터 기준** 필드에서 **할당되지 않았거나 만료된 그룹** 을 선택합니다.

### <a name="export-to-excel"></a>Excel로 내보내기

목록을 Microsoft Excel로 내보내려면 다음 단계를 따릅니다.

1. **Microsoft Office에서 열기** 버튼을 선택합니다.
2. **내부 사용을 위한 HCM Human Resources 임시 테이블** 을 선택합니다.
3. **다운로드** 를 선택합니다.

### <a name="view-aca-reportable-dependents"></a>ACA 보고 가능 피부양자 보기

자가 보험 혜택을 제공하기 때문에 보험 가입자를 신고해야 하는 경우, **ACA 보고 가능** 으로 표시된 혜택 계획에 따라 보험에 가입된 피부양자를 볼 수 있습니다. 작업 창에서 **피부양자 보장 보기** 를 선택합니다.

![피부양자 보장을 봅니다.](./media/hr-benefits-management-aca-view-dependent-coverage.png)

직원의 피부양자에 대한 보장 정보가 표시됩니다.

![피부양자 보장.](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> 이 페이지에는 **ACA 보고 가능** 으로 표시된 혜택 계획만 표시됩니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
