---
title: Human Resources 매개 변수 구성
description: 이 항목에서는 Dynamics 365 Human Resources에서 회사별 매개 변수를 설정하는 방법을 설명합니다.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fd9bb907f95ba4c368871a470ca9b2bc807646ee
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451972"
---
# <a name="configure-human-resources-parameters"></a>Human Resources 매개 변수 구성

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

일부 Human Resources 매개 변수의 설정은 회사 간에 공유되는 반면 회사별로 다른 매개 변수의 설정도 있습니다. 이 항목에서는 회사별 Human Resources 매개 변수를 설정하는 방법을 설명합니다.

Human Resources 매개 변수를 설정하는 데 두 페이지가 사용됩니다. 회사 간에 공유되는 매개 변수의 경우 **Human Resources 공유 매개 변수** 페이지를 사용합니다. 회사별 매개 변수(즉, 설정이 단일 회사에 적용됨)의 경우 **Human Resource 매개 변수** 페이지를 사용합니다.

![Human Resources 매개 변수로 이동합니다.](./media/hr-employee-self-service-human-resources-parameters.png)

**Human Resources 매개 변수** 페이지에서 설정은 6개의 탭으로 나뉘어 있습니다.

- **일반**
- **모집**(이 탭은 Dynamics 365 Human Resources에 포함되지 않음)
- **보상**
- **번호 시퀀스**
- **FMLA**
- **직원 셀프 서비스**
- **관리자 셀프 서비스**
- **복리후생 관리**
- **휴가 및 부재**
- **지급 방법**

각 탭에는 단일 회사와 관련된 정보가 포함되어 있습니다.

## <a name="general"></a>일반

**일반** 탭의 설정은 부재, 부상 및 질병, 신입사원에 대한 정보의 표시를 정의합니다. 이 탭의 설정은 작업할 때 표시되는 일부 기본 항목도 정의합니다. 특히 이 탭에서 다음을 수행할 수 있습니다.

- 미결 부재 거래에 적용할 색상 선택.
- 보고서에 사용할 스타일 시트 지정.
- 교육 과정과 부재 등록 간의 통합 활성화.
- 이 통합을 제어하는 데 사용되는 부재 코드 선택.
- 부상 및 질병 인시던트를 보관할 기간을 표시.
- 새 작업자를 채용할 때 표시되는 기본 식별 번호를 지정.
- 근속 연수를 계산하는 데 사용되는 날짜 지정. 

![일반 탭.](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a>모집

**모집** 탭의 설정은 지원자에게 자동으로 발송되는 서신에 사용되는 문서 유형을 정의합니다. 요청하지 않은 지원에 사용된 구인 프로젝트를 표시할 수도 있습니다.

**구인 프로젝트 에이징** 에 정의된 기간은 **구인 관리** 작업 영역의 **에이징 프로젝트** 타일에 포함되는 구인 프로젝트를 결정합니다. 지원 마감 경고에 대해 정의된 기간은 **구인** 작업 영역의 **지원 마감 임박** 타일에 지원 마감이 임박한 구인 프로젝트를 표시하는 데 사용됩니다.

구인에 대한 자세한 내용은 [구직 후보자 모집](hr-personnel-recruit.md)을 참조하세요.

## <a name="compensation"></a>보상

Dynamics 365 Finance에서 **보상** 탭의 설정은 사용자가 고정 또는 변동 보상 계획에 대한 정보를 저장할 것인지 확인해야 하는지를 정의합니다. **저장 유효성 검사 활성화** 를 선택하면 사용자가 보상 관련 페이지를 닫을 때 기록을 저장할지 묻는 메시지가 나타납니다. 보상 관리의 일부 페이지에서는 사용자가 정보를 삭제할 수 없습니다. 사용자에게 정보를 저장할지 확인하라는 메시지를 표시하면 저장되고 나중에 삭제할 수 없는 정보의 양을 제한할 수 있습니다. **저장 유효성 검사 활성화** 를 선택 취소하면 사용자가 준비되기 전에 레코드가 즉시 저장됩니다. 성과 관리를 사용하면 **보상** 탭에서 성과를 평가할 때 보상 계획에 할당된 모델 대신 사용할 평가 모델을 선택할 수도 있습니다.

Human Resources에서 **보상** 탭을 사용하여 보상 계획에 대한 액세스를 제한하고 기본 통화를 설정할 수 있습니다.

보상에 대한 자세한 내용은 [보상 계획 개요](hr-compensation-overview.md)를 참조하세요.

![보상 탭.](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a>번호 시퀀스

**번호 시퀀스** 탭의 설정은 다음과 같이 Human Resources의 항목에 ID를 자동으로 할당하는 데 사용되는 순서를 결정합니다.

- 애플리케이션
- 부재 등록
- 보상 프로세스 결과
- 사례 번호
- 과정
- 과정 의제

번호 시퀀스 참조 및 코드를 유지하려면 **번호 시퀀스** 목록 페이지를 사용합니다(**조직 관리 > 번호 시퀀스 > 번호 시퀀스** 선택).

자세한 내용은 [번호 시퀀스 개요](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)를 참조하세요.

> [!NOTE]
> 근로 시간은 1,250시간을 초과할 수 없으며 고용 기간은 12개월을 초과할 수 없습니다. 이 최대값은 미국 연방법에 따릅니다.

![번호 시퀀스 탭.](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a>FMLA

FMLA 탭에서 FMLA 자격 요건 및 FMLA 권한 시간을 설정합니다. 자세한 내용은 [휴가 및 부재 매개 변수 구성](hr-leave-and-absence-parameters.md)을 참조하세요.

![FMLA 탭.](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a>직원 셀프 서비스

**직원 셀프 서비스** 탭의 설정은 **직원 셀프 서비스** 가 직원에게 표시되는 방식에 영향을 줍니다. 이 탭에서 다음 작업을 완료할 수 있습니다.

- **직원 셀프 서비스** 작업 영역에 대한 이름 입력
- 관리자가 직원에 관해 입력할 수 있는 정보 선택
- 직원에게 유용한 링크 추가
- 직원이 비즈니스 연락처 세부 정보를 추가하거나 편집하지 못하도록 제한. 자세한 내용은 [개인 정보 편집 제한](hr-employee-self-service-restrict-editing.md)을 참조하세요.

**직원 셀프 서비스** 를 설정하는 방법에 대한 자세한 내용은 [직원 및 관리자 셀프 서비스 개요](hr-employee-manager-self-service-overview.md)를 참조하세요.

![직원 셀프 서비스 탭.](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a>관리자 셀프 서비스

**관리자 셀프 서비스** 탭의 설정은 관리자가 **관리자 셀프 서비스** 에서 보는 내용에 영향을 줍니다. 이 탭에서 다음 옵션을 구성할 수 있습니다.

- 만료되는 레코드 범위
- 관리자가 만료되는 레코드에서 볼 수 있는 정보
- 관리자가 확장 부하 직원 대한 열린 직책을 볼 수 있는지 여부
- 기존 작업자 보기
- 관리자에게 유용한 링크

**관리자 셀프 서비스** 를 설정하는 방법에 대한 자세한 내용은 [직원 및 관리자 셀프 서비스 개요](hr-employee-manager-self-service-overview.md)를 참조하세요.

![관리자 셀프 서비스 탭.](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a>복리후생 관리

**복리후생 관리** 탭에서 복리후생 관리를 위한 이메일 옵션을 구성할 수 있습니다. 복리후생 관리 설정 및 사용 방법은 [복리후생 관리 개요](hr-benefits-management-overview.md)를 참조하세요.

![복리후생 관리 탭.](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a>휴가 및 부재

휴가 및 부재의 설정 및 사용에 대한 자세한 내용은 [휴가 및 부재 개요](hr-leave-and-absence-overview.md)를 참조하세요.

## <a name="payment-methods"></a>지급 방법

**지급 방법** 탭에서는 조직에서 지원하는 지급 방법을 선택할 수 있습니다. 보상 구성에 대한 자세한 내용은 [보상 계획 개요](hr-compensation-overview.md)를 참조하세요.

![지급 방법 탭.](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
