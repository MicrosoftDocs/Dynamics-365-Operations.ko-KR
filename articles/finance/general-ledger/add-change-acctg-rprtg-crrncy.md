---
title: 회계 또는 보고 통화 변경
description: 이 문서에서는 회계 또는 통화 보고를 변경하거나 원장 설정에 통화 보고를 추가하는 방법에 대해 설명합니다.
author: kweekley
ms.date: 05/05/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b02432c8e0bdf52c2a588f67a581b78e682b1bf8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904618"
---
# <a name="change-the-accounting-or-reporting-currency"></a>회계 또는 보고 통화 변경

[!include [banner](../includes/banner.md)]

이 문서에서는 회계 또는 통화 보고를 변경하거나 원장 설정에 통화 보고를 추가하는 방법에 대해 설명합니다.

## <a name="symptom"></a>증상

회계 또는 통화 보고를 변경하거나 원장 설정에 통화 보고를 추가하려 합니다. 이 현상은 일반적으로 다음 시나리오에서 발생합니다.

- 법인을 설정할 때 잘못된 회계 또는 통화 보고가 설정되었습니다. 이제 해당 통화를 변경해야 합니다.
- 법인이 설정될 때 통화 보고가 지정되었지만, 조직은 이제 통화 보고를 제거하려 합니다.
- 조직은 Microsoft Dynamics 365 Finance로의 업그레이드 또는 마이그레이션을 진행 중이며, 회계 또는 통화 보고를 변경하려 합니다.

이중 통화 기능을 사용하지 않았던 조직에서 이 기능을 사용하려 합니다. 이 문제는 일반적으로 다음 시나리오에서 발생합니다.

- 법인을 설정할 때 통화 보고가 지정되지 않았습니다. (통화 보고는 선택 사항입니다.) 이제 통화 보고를 추가하려 합니다.

## <a name="resolution"></a>해결책

가장 중요한 고려 사항은 거래(실제 또는 예산)가 원장 설정을 위해 법인에 전기되었는가 여부입니다. **거래(실제 또는 예산)가 법인에 전기되었다면 회계 또는 통화 보고를 변경하거나 통화 보고를 추가할 수 없습니다.** 거래 전기 여부에 따라, 다음 섹션 중 하나의 단계를 따릅니다.

### <a name="no-transactions-have-been-posted"></a>거래가 전기되지 않음

1. 통화를 업데이트하는 법인에서 **총계정원장 \> 원장 설정 \> 원장** 으로 이동합니다.
2. **원장** 페이지에서 **편집** 을 선택합니다.
3. **통화** 빠른 탭에서 법인에 사용할 회계 통화 및 통화 보고를 선택합니다.
4. **저장** 을 선택합니다.

**원장** 페이지에서 회계 통화 및 통화 보고 필드를 사용할 수 없다면, 법인에 하나 이상의 거래(실제 또는 예산)가 전기되었다는 뜻입니다. 따라서 통화를 변경할 수 없습니다. 이 경우에는 다음 섹션의 단계를 따르십시오.

### <a name="transactions-have-been-posted"></a>거래가 전기됨

**거래가 법인에 전기된 경우, 회계 및 통화 보고를 변경하거나 추가하는 유일한 방법은 올바른 통화가 있는 새 법인을 만드는 것입니다.** 시스템의 데이터 관리를 통해 현재 법인의 설정 레코드와 마스터 레코드를 새 법인으로 복사하면 이 프로세스를 쉽게 수행할 수 있습니다.

회계 및 통화 보고 변경은 자주 발생합니다. 총계정원장은 물론 모든 보조원장(수취 계정, 지급 계정, 재고, 프로젝트 등), 모든 ISV(독립 소프트웨어 공급업체) 솔루션 및 금액을 저장하기 위해 만든 확장에도 영향을 미칩니다.

각 금액을 찾고 다른 통화로 환산하는 과정은 오류가 자주 발생합니다. 따라서 엔지니어링 팀은 회계 및 통화 보고를 변경하거나 추가하는 스크립트를 승인하지 않습니다. 또한 Microsoft Dynamics AX 2012에서 제공했던 도구로 회계 및 통화 보고를 변경하거나 추가할 수 있지만, 이 도구는 AX 2012 R3와 Finance 모두에서 사용이 중단되었습니다.

설정 및 마스터 데이터를 현재 법인에서 새 법인으로 복사하려면 다음 단계를 따르세요.

1. **작업 영역 \> 데이터 관리** 로 이동합니다.
2. **가져오기/내보내기** 그룹에서 **템플릿** 을 선택합니다.
3. 템플릿을 사용할 수 있는지 확인하세요. 사용할 수 있는 템플릿이 없다면 **기본 템플릿 로드** 를 선택하고 템플릿이 생성될 때까지 기다립니다.
4. **데이터 관리** 작업 영역으로 돌아갑니다.
5. **법인에 복사** 를 선택합니다.
6. 그룹 이름과 설명을 입력합니다.
7. **원본 법인** 필드에서 데이터를 복사할 법인을 선택합니다.
8. **대상 법인** 빠른 탭에서 **법인 만들기** 를 선택하여 원본 법인의 데이터를 붙여넣을 수 있는 새 법인을 만듭니다. **기존 선택** 을 선택하여 데이터를 기존 법인에 복사합니다.
9. 선택 사항: **숫자 시퀀스 복사** 필드를 **예** 로 설정합니다. (이 단계는 데이터를 복사할 때 하는 것이 좋습니다.)
10. **선택한 법인** 영역에서 **템플릿 추가** 를 선택합니다.
11. 사용할 템플릿을 선택합니다. 새 법인에 제안된 템플릿에는 **025 - 총계정원장** 과 **재무** 가 있습니다. 사용 가능한 다른 템플릿을 모두 검토하여 자신의 요구 사항에 맞는 템플릿이 있는지 확인하면 도움이 됩니다.
12. **법인에 복사** 를 선택하여 선택된 법인을 만들고 대상 법인으로 복사하는 배치 프로세스를 시작합니다.
13. 프로세스가 완료되면, 거래가 전기되기 전에 원장으로 이동하여 이 문서의 앞부분에서 설명한 방법에 따라 회계 및 통화 보고를 업데이트합니다.

회계 또는 통화 보고를 변경하기 위해 새 법인을 만들었다면, 기초 잔액이 이전 법인의 통화에서 새 통화로 환산되었는지 확인하세요.

이전 단계를 보여주는 비디오가 필요하다면 [법인으로 복사](https://community.dynamics.com/365/b/techtalks/posts/copy-into-legal-entity-october-24-2017)를 시청하세요.
