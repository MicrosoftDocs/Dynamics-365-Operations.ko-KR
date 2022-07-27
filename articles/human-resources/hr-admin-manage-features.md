---
title: Human Resources의 기능 관리
description: 이 항목에서는 기능 관리 기능과 사용 방법을 설명합니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2d5a27c02df841dfbb17a9375aaf75f93d05cd8e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452575"
---
# <a name="manage-features-in-human-resources"></a>Human Resources의 기능 관리


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources의 새로운 기능을 지속적으로 출시함에 따라 고객이 최대한 빨리 새로운 기능을 경험할 수 있도록 하고자 합니다. Microsoft는 일반 공급이 거의 준비되고 광범위한 테스트를 거친 미리 보기 기능을 제공합니다. 일반 공급을 위해 출시하기 전에 고객 피드백과 유효성 검사의 최종 라운드를 수행하기 위한 것입니다.

Human Resources의 새로운 기능에 대한 자세한 내용은 [Human Resources의 새로운 기능](hr-admin-whats-new.md) 및 [Dynamics 365 및 Power Platform 릴리스 계획](/dynamics365/release-plans/?panel=products1#pivot=products)을 참조하세요.

**기능 관리** 작업 영역에는 각 릴리스에서 제공되는 기능 목록이 표시됩니다. 기본적으로 새 기능은 꺼져 있습니다. 작업 영역을 사용하여 해당 기능을 켜고 설명서를 볼 수 있습니다. 기능 관리에 대한 자세한 내용은 [기능 관리 개요](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하세요.

모든 새로운 기능은 최소 30일, 일반적으로 30~60일 동안 미리 보기로 유지됩니다. 주요 기능은 일반적으로 미리 보기 기간 이후 매년 10월과 4월에 사용할 수 있습니다. **기능 관리** 작업 영역에 새로운 기능이 표시되면 바로 켤 수 있습니다. 일부 기능은 기본적으로 켜져 있을 수 있습니다.

기능이 정식 제공되면 프로덕션 환경에서 켜거나 끌 수 있습니다. **기능 관리** 작업 영역에는 미리 보기 기능이 필수가 되는 시기가 표시됩니다. 이 날짜는 일반적으로 반년 릴리스 계획에 맞춰 10월 1일 또는 4월 1일로 정합니다. 필수 기능은 끌 수 없습니다. 필수가 될 때까지 모든 환경에서 기능을 켜고 끌 수 있습니다.

## <a name="enable-or-disable-preview-features"></a>미리 보기 기능 활성화 또는 비활성화

미리 보기 기능에 액세스하려면 먼저 환경에서 활성화해야 합니다. 미리 보기 기능을 활성화하거나 비활성화하는 방법은 환경에 따라 다릅니다.

> [!IMPORTANT]
> 미리 보기 기능은 **샌드박스** 환경에서만 사용할 수 있습니다. 미리 보기 기능을 켜면 해당 환경에 있는 조직의 모든 사용자에 대해 활성화됩니다. 미리 보기 기능을 끄면 비활성화되어 사용자가 액세스할 수 없게 됩니다. 미리 보기 기능은 Human Resources에서 제한적으로 지원됩니다. 제한된 개인 정보 및 보안 조치가 적용되고 인적 자원 서비스 수준 계약(SLA)에 포함되지 않습니다. 미리 보기 기능으로 개인 데이터(즉, 사용자를 식별할 수 있는 모든 정보)를 처리하거나 법률 또는 규정 준수 요구 사항이 적용되는 기타 데이터를 처리해서는 안 됩니다.

1. Human Resources에서 **시스템 관리** 를 선택합니다.

2. **기능 관리** 타일을 선택합니다.

3. 미리 보기 기능을 활성화하려면 목록에서 해당 기능을 선택한 다음 **활성화** 를 선택합니다. 미리 보기 기능을 비활성화하려면 목록에서 해당 기능을 선택한 다음 **비활성화** 를 선택합니다.

## <a name="enable-or-disable-benefits-management"></a>복리후생 관리 활성화 또는 비활성화

복리후생 관리를 활성화하려면 [미리 보기 기능 활성화 또는 비활성화](hr-admin-manage-features.md?enable-or-disable-preview-features)에 나온 같은 단계를 사용하세요.

> [!IMPORTANT]
> **프로덕션** 환경에서 복리후생 관리를 활성화한 후에는 비활성화할 수 없습니다. 그러나 **샌드박스** 환경에서는 복리후생 관리를 비활성화할 수 있습니다.

복리후생 관리 구성 및 사용에 대한 자세한 내용은 [복리후생 관리 개요](hr-benefits-management-overview.md)를 참조하세요.

복리후생 관리는 **복리후생** 작업 영역의 기능을 대체합니다. 복리후생 관리 미리 보기 기능을 활성화하면 **복리후생** 작업 영역에서 더는 다음 양식에 액세스할 수 없습니다.

- **복리후생**
- **복리후생 요소**
- **기여 계산 비율**
- **복리후생 등록 결과**
- **복리후생 만료 및 연장 결과**
- **혜택 자격 정책 규칙 유형**
- **복리후생 자격 정책**
- **자격 이벤트**

이 페이지의 정보를 읽기 전용 모드로 볼 수 있습니다. 정보를 수정하려면 먼저 복리후생 관리를 비활성화해야 합니다(**샌드박스** 환경에만 해당).

## <a name="enable-or-disable-leave-and-absence"></a>휴가 및 휴무 활성화 또는 비활성화

휴가 및 휴무를 활성화하려면 [미리 보기 기능 활성화 또는 비활성화](hr-admin-manage-features.md?enable-or-disable-preview-features)에 나온 같은 단계를 사용하세요.

> [!IMPORTANT]
> 휴가 및 휴무에서 **여러 휴무 유형** 기능을 활성화한 후에는 비활성화할 수 없습니다. 이는 **샌드박스** 및 **프로덕션** 환경에 모두 적용됩니다.

휴가 및 휴무 미리 보기 기능에 대한 자세한 내용은 [휴가 및 휴무 미리 보기 기능](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)을 참조하세요.

## <a name="send-us-feedback"></a>피드백 보내기

미리 보기 기능에 대한 귀하의 경험에 대해 듣고 싶습니다. 이러한 기능이나 기타 기능을 사용할 때 다음 사이트에 정기적으로 피드백을 게시해 주세요.

- [커뮤니티](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – 이 사이트는 사용자가 사용 사례에 관해 논의하고, 질문하며, 커뮤니티의 도움을 받을 수 있는 훌륭한 리소스입니다.
- 제품에서 원하는 기능이나 기존 기능에 적용해야 한다고 생각하는 변경 사항에 대해 알려주세요. 제품에 대한 아이디어는 [Human Resources 아이디어](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)에서 제안하세요.
    
피드백이나 제품 리뷰 제출에는 개인 데이터(사용자를 식별할 수 있는 모든 정보)를 포함하지 마세요. 수집된 정보는 추가로 분석될 수 있으며 해당 개인 정보 보호법에 따라 요청에 응답하는 데 사용되지 않습니다. 이러한 프로그램에 따라 별도로 수집되는 개인 데이터에는 [Microsoft 개인정보보호정책](https://privacy.microsoft.com/privacystatement)이 적용됩니다.

## <a name="see-also"></a>참고 항목

- [Human Resources의 새로운 기능](hr-admin-whats-new.md)
- [Dynamics 365 및 Power Platform 릴리스 계획](/dynamics365/release-plans/?panel=products1#pivot=products)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
