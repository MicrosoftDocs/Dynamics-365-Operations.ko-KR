---
title: 인스턴스 제거
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources의 시험 사용 또는 프로덕션 환경을 제거하는 프로세스를 안내합니다.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e32058280d0cb1eab436bc25bd29bc3e39fabc92
ms.sourcegitcommit: 49f7528d3268abe15e40f719956e1ec8696a6f4e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2021
ms.locfileid: "8451939"
---
# <a name="remove-an-instance"></a>인스턴스 제거

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Microsoft Dynamics 365 Human Resources의 시험 사용 또는 프로덕션 환경을 제거하는 프로세스를 설명합니다.

## <a name="remove-a-test-drive-environment"></a>시험 사용 환경 제거

Human Resources 시험 사용에는 60일 만료 정책이 적용됩니다. 그러나 시험 사용 환경의 소유자는 다음 단계를 완료하여 평가판을 조기에 종료할 수 있습니다. 

1. [Power Apps 관리 센터](https://admin.businessplatform.microsoft.com/)로 이동합니다.
2. **환경** 을 선택합니다.
3. TestDrive - 별칭@도메인과 비슷한 명명 패턴을 가진 시험 사용 환경을 선택합니다.
4. **삭제** 를 선택하고 삭제를 확인합니다. 

기존 시험 사용 환경이 제거됩니다. 제거되면 새로운 시험 사용 환경에 등록할 수 있습니다. 

## <a name="remove-a-production-environment"></a>프로덕션 환경 제거

이 항목에서는 클라우드 솔루션 공급자(CSP) 또는 엔터프라이즈 아키텍처(EA) 계약을 통해 Human Resources를 구매했다고 가정합니다. 

단일 Human Resources 환경은 단일 Power Apps 환경에 포함되므로 두 가지 옵션을 고려해야 합니다. 첫 번째 옵션은 전체 Power Apps 환경을 제거하는 것이고 두 번째 옵션은 Human Resources만 제거하는 것입니다. 첫 번째 옵션은 명시적으로 Human Resources를 프로비저닝할 목적으로 Power Apps 환경을 만들고 구현을 막 시작했거나 설정된 통합이 없는 경우 선호됩니다. 두 번째 옵션은 Power Apps 및 Power Automate에서 활용되는 풍부한 데이터로 채워진 Power Apps 환경이 설정된 경우에 적합합니다.

> [!Important]
> Power Apps 환경을 제거하기 전에 Human Resources 범위를 벗어나는 풍부한 데이터 통합에 사용되지 않는지 확인하세요. 또한 기본 Power Apps 환경은 제거할 수 없습니다. 

Human Resources와 관련 앱 및 흐름을 포함하여 전체 Power Apps 환경을 제거하려면 다음을 수행합니다.

1. [Power Apps 관리 센터](https://admin.businessplatform.microsoft.com/)로 이동합니다.
2. **환경** 을 선택합니다.
3. 제거할 환경을 선택합니다.
4. **삭제** 를 선택하고 삭제를 확인합니다. 
5. 삭제가 완료될 때까지 기다립니다.
6. Human Resources에 가입할 때 사용한 계정으로 [Lifecycle Services(LCS)](https://lcs.dynamics.com/Logon/Index)에 로그인합니다. 
7. 환경이 포함된 Human Resources 프로젝트를 선택합니다. 
8. LCS 프로젝트에서 **Human Resources 앱 관리** 타일을 선택합니다. 
9. 제거할 인스턴스를 선택합니다. 
10. **인스턴스 제거** 를 선택하고 결정을 확인합니다.  

기존 Power Apps 환경에서 Human Resources 환경을 제거하려면 다음 단계를 완료합니다. 이 기능이 LCS에서 직접 활성화될 때까지는 고객 지원팀과 Human Resources DevOps 팀에 문의해야 할 필요성은 일시적입니다.

1. 제거 요청을 시작하려면 고객 지원팀에 문의하세요.
2. 고객 지원팀은 Human Resources DevOps 팀과 함께 제거 요청을 시작합니다. 
3. 환경이 제거되었다는 메시지를 받은 후 계속합니다.
4. Human Resources에 가입할 때 사용한 계정으로 LCS에 로그인합니다. 
5. 환경이 포함된 Human Resources 프로젝트를 선택합니다. 
6. LCS 프로젝트에서 **Human Resources 앱 관리** 타일을 선택합니다. 
7. 배포 상태가 **제거됨** 으로 표시되는 제거하려는 인스턴스를 선택합니다.
8. **인스턴스 제거** 를 선택하고 결정을 확인합니다. 

## <a name="recover-a-soft-deleted-environment"></a>일시 삭제된 환경 복구

Human Resources 환경이 연결된 Power Apps 환경을 삭제하면 Lifecycle Services의 Human Resources 환경 상태가 **일시 삭제됨** 이 됩니다. 이 경우 사용자는 Human Resources에 연결할 수 없습니다.

환경을 복원하려면 다음을 수행합니다.

1. [Power Apps 환경 복구](/power-platform/admin/recover-environment.md)의 지침을 따릅니다.

2. Human Resources 환경을 복원하려면 고객 지원팀에 문의하세요. 자세한 내용은 [지원받기](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md)를 참조하세요.

> [!Warning]
> Power Apps 환경은 삭제 후 7일 동안만 저장됩니다. 7일 이내에 환경을 복구해야 합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
