---
title: ACA(Affordable Care Act) 보고서 생성
description: Affordable Care Act(ACA) 보고서는 Affordable Care Act의 **고용주 필수** 부분을 지원하는 양식 1095-B 및 1095-C를 생성합니다.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c8f336e31e77391ef7e2bc2dca901e6a78fbb914
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452296"
---
# <a name="generate-aca-reports"></a>ACA 보고서 생성


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Affordable Care Act(ACA) 보고서는 Affordable Care Act의 **고용주 필수** 부분을 지원하는 양식 1095-B 및 1095-C를 생성합니다.

> [!NOTE]
> ACA 보고 기능은 미국 법인만 사용할 수 있습니다.

## <a name="getting-started"></a>시작하기

1095-B 및 1095-C 양식에 대한 정보를 추적하려면 먼저 하나 이상의 Affordable Care 보장 그룹을 만들어야 합니다. Affordable Care 보장 그룹은 다음을 나타냅니다.

- 고용인에 대한 보장 제공
- 비용이 연방 빈곤선을 초과하는 경우 최저 월 보험료에 대한 직원의 몫
- 해당되는 경우, 고용주가 사용하는 세이프 하버

Affordable Care 보장 그룹을 사용하면 조건이 동일한 모든 직원 기록을 변경하지 않고도 이러한 필드에 대한 정보를 관리할 수 있습니다. 페이지의 **대량 할당** 옵션을 사용하여 한 명 이상의 직원에게 저렴한 의료 보장 그룹을 쉽게 할당할 수 있습니다.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>보장 그룹의 여러 버전을 유지 관리

모든 보장 그룹의 여러 버전을 유지할 수 있습니다. 이 기능을 사용하면 새 그룹을 만들고 해당 그룹에 직원을 재할당하지 않고도 변경할 수 있습니다. 

ACA 보장 그룹을 만든 후 **대량 할당** 옵션을 사용하여 직원에게 그룹을 대량 할당할 수 있습니다. 또한 ACA 정보를 추적 및 보고할지 여부를 개별적으로 지정하고 직원을 Affordable Care 서비스 그룹에 할당할 수도 있습니다.

시간제 직원과 같은 일부 ACA 보장 정보는 추적할 필요가 없습니다. 이 경우 **보장 보고** 필드를 **아니요** 로 설정합니다. 추적 가능한 ACA 정보를 가진 각 직원을 Affordable Care 서비스 그룹에 할당해야 하지만 값이 서로 다른 몇 개월 동안 다음 옵션을 변경할 수 있습니다.

- **보장 범위 제공**
- **직원 비용 분담금**
- **세이프 하버**

Affordable Care 보장 그룹 값에 대한 예외를 입력하려면 **고용 탭** 의 **추가 정보** 섹션 아래의 **직원 세부 정보** 페이지에서 **Affordable Care 보장** 링크를 선택합니다.

## <a name="reporting-health-care-coverage"></a>의료 서비스 보장 보고

정규직 직원에게 제공되는 건강보험 보장 범위 추적 외에도, 고용주가 고용인이 등록한 고용주가 후원하는 자가 보험 보장 범위를 제공하는 경우(고용 상태가 정규직인지 파트타임인지에 관계없이) 추가 정보는 1095-C에 보고해야 합니다. 고용주가 후원하는 혜택 계획의 대상인 각 직원(피부양자 포함)은 대상 월 동안 보고서에 포함되어야 합니다. 

**ACA 보고 가능** 확인란을 선택하여 각 혜택 계획의 보고 여부를 지정할 수 있습니다.

또한 직원이 부양가족 중 하나를 혜택으로 적용받도록 선택한 경우, 부양가족이 각 직원별로 적용되는 날짜를 **혜택 유지 관리** 페이지에 표시할 수 있습니다. 피부양자가 혜택에 포함됨을 나타내려면 **피부양자** 빠른 탭의 작업 창에서 **편집** 버튼을 선택합니다.

**피부양자 보장 날짜 관리자** 페이지에서 종속 항목이 혜택에 포함된 날짜를 지정할 수 있습니다. 이 페이지에 날짜를 입력하면 **혜택 유지 관리** 페이지에서 **보장됨** 확인란이 자동으로 선택됩니다.

## <a name="generate-1095-b-and-1095-c-forms"></a>1095-B 및 1095-C 양식 생성

또한 제품 내에서 1095-B 및 1095-C 양식을 생성하여 각 직원에게 배포할 수 있습니다. 또한 시스템은 1095-C 양식과 1094-CIRS 전송 파일을 전자적으로 생성할 수 있습니다.  

1095-C 양식을 생성할 때 적절한 과세 연도를 입력하고 사회 보장 번호를 가려야 하는지 여부를 지정합니다. 500명 이상의 직원을 대상으로 1095-C 양식을 인쇄하는 경우 둘 이상의 PDF 파일을 받게 됩니다. **문서 관리 매개 변수** 창의 **최대 파일 크기** 를 150MB로 늘리는 것이 좋습니다.

## <a name="viewing-information"></a>정보 보기

**직원 Affordable Care 보장** 페이지를 사용하여 각 보장 그룹에 할당된 직원, 보고서에 포함할 필요가 없는 직원 및 할당되지 않은 직원을 확인할 수 있습니다.

Affordable Care 보장 그룹의 기본값이 재정의된 경우 변경된 값 옆에 별표가 나타납니다. 모든 12개월에 대한 값이 동일하고 재정의되지 않은 경우 **모든 12개월** 열에 값이 인쇄됩니다.

또한 조회 창을 사용하여 ACA 보고 불가로 플래그가 지정된 직원을 파악할 수 있습니다. 보험 적용 여부를 추적할 필요가 없으며 연말에 1095-C를 발급할 필요도 없습니다. 1095-C를 받지 못하는 모든 직원의 목록을 생성하려면 **필터 기준** 필드에서 **ACA 보고 불가** 를 선택합니다.

또한 할당되지 않은 직원(**ACA 보고 보장** 필드가 비어 있음) 또는 **연도** 필드에서 선택한 연도에 대해 만료된 Affordable Care 보장 그룹에 할당된 직원을 볼 수 있습니다.

필터링 옵션을 사용하여 생성된 직원 목록을 Excel로 내보낼 수 있습니다.

자가 보험 보장을 제공하기 때문에 보험 적용 대상자를 보고해야 하는 경우, **ACA 보고 가능** 으로 표시된 혜택 제도에 따라 보험 적용 대상 피부양자를 볼 수 있습니다. 작업 창에서 **피부양자 보장 보기** 를 선택합니다.

> [!NOTE]
> **ACA 보고 가능** 으로 표시된 혜택 계획만 조회 창에 표시됩니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
