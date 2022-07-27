---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 4월 5일)
description: 이 항목에서는 2021년 4월 5일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 04/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d91ef244f8dd48baf65f5633357a7d81a68f84621b20d39d4e0ee771283a2bab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451897"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-5-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 4월 5일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4074에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 직원이 비즈니스 연락처 세부 정보를 편집하지 못하도록 제한 | [직원이 비즈니스 연락처 세부 정보를 편집하지 못하도록 제한](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [개인 정보 편집 제한](./hr-employee-self-service-restrict-editing.md)|

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 550852 | **승인** 버튼이 **검토** 양식에 설정된 필수 필드의 유효성을 검사하지 않음. | **검토** 양식의 필드를 필수로 설정하고 관리자 역할에 대한 변경을 게시하면 양식이 제대로 유효성을 검사하지 않습니다. |
| 559564 | 해고된 사용자의 경우 고정 보상 변경에 대한 과거 작업자 작업에 오류가 발생함. | 해고 직원 보상의 작업자 작업에 오류가 발생합니다. 직원이 해고된 후 해고 전 직원의 승진 조치에 오류가 발생합니다. |
| 560074 | 고용 범주 드롭다운이 **작업자 유형** 으로 필터링되지 않고 직원 및 계약자에 대한 범주를 표시함. | **직원** 양식의 **고용 범주** 드롭다운에 직원의 작업자 유형에 따라 직원 또는 계약자 범주가 표시되어야 합니다. |
| 567388 | 새로 생성된 직원에 대한 일부 정보가 Dataverse의 **cdm_worker** 테이블과 즉시 동기화되지 않음. | 새 직원 레코드를 만들 때 새 레코드가 Dataverse의 **cdm_worker** 테이블과 동기화되지만 일부 속성이 Dataverse 레코드에 포함되지 않습니다. |
| 563837 | Human Resources에서 사용할 수 없는 기능이 표시됨. | Human Resources에 적용되지 않는 여러 기능이 기능 관리에 표시됩니다. 이러한 기능은 이제 Human Resources에서 활성화할 수 있는 기능 목록에서 제거되었습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |

## <a name="coming-soon"></a>업데이트 예정

| 기능 | 세부 정보 |
| --- | --- |
| 관리자가 직원을 위해 입력한 기술은 워크플로에서 자동 승인될 수 있음 | 업데이트 예정. |
| 플랫폼 업데이트 10.0.17(41) | 플랫폼 업데이트 10.0.17은 2021년 4월 19일 다음 릴리스와 함께 출시될 예정입니다. 자세한 내용은 [금융 및 운영 앱 버전 10.0.17의 플랫폼 업데이트(2021년 4월)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md)를 참조하세요. |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]