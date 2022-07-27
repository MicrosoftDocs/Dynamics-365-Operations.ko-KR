---
title: 라이브 전환 FAQ
description: 이 항목에는 Dynamics 365 Human Resources 구현 프로젝트를 라이브 전환하는 방법에 관해 자주 묻는 질문이 나열되어 있습니다.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c449ae6eb84fb4150072c386d02b100ca3cca219
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452323"
---
# <a name="go-live-faq"></a>라이브 전환 FAQ 


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에는 Dynamics 365 Human Resources 구현 프로젝트를 라이브 전환하는 방법에 관해 자주 묻는 질문이 나열되어 있습니다. 

## <a name="when-can-i-configure-and-request-my-production-environment"></a>프로덕션 환경을 언제 구성하고 요청할 수 있습니까? 

일반적으로 프로덕션 환경은 다음 기준을 충족한 후 배포됩니다.

- 모든 사용자 지정의 코드가 완성되었습니다.
- UAT(User Acceptance Test)가 완료되었습니다.
- 고객이 솔루션을 승인했습니다.
- 라이브 전환을 방해하는 문제가 없습니다. 

적격 고객이 이 단계이면 Microsoft FastTrack 팀이 프로젝트 팀과 협력하여 라이브 전환 평가를 수행합니다. 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a>프로덕션 환경을 배포하기 위한 전제 조건은 무엇입니까? 

전제 조건 목록은 [라이브 전환 준비](hr-admin-go-live-prepare.md)를 참조하세요. 

## <a name="what-is-a-go-live-assessment"></a>라이브 전환 평가란?  

라이브 전환 평가는 [Microsoft FastTrack 프로그램](/dynamics365/fasttrack/)의 일부입니다. 솔루션 설계자는 이 검토 중에 구현 프로젝트가 성공적인 전환 및 활성화를 위한 준비가 되었는지 평가합니다. 이 검토는 프로덕션 환경에서 라이브 전환을 요청하기 전에 모든 구현 프로젝트에 필수입니다. 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a>당사의 샌드박스 환경은 미국 중부 데이터 센터에 배포됩니다. 프로덕션 환경을 미국 서부 데이터 센터에 배포하면 좋겠습니다. 프로덕션 구성에서 미국 서부를 데이터 센터로 선택할 수 있습니까? 

LCS는 Human Resources 환경을 배포할 때 다른 데이터 센터를 선택하는 것을 제한하지 않지만 다른 데이터 센터를 선택하지 않는 것이 좋습니다.  

프로덕션 환경을 미국 서부 데이터 센터에 배치하려면 먼저 샌드박스 환경을 미국 서부 데이터 센터에 다시 배포하고 테스트한 후 승인해야 합니다. 

올바른 데이터 센터 선택에 대한 자세한 내용은 [네트워크 요구 사항](../fin-ops-core/fin-ops/get-started/system-requirements.md#network-requirements)을 참조하세요. 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a>Human Resources 환경에서 액세스할 수 있는 Azure 리소스의 수준은 어느 정도입니까?  

Human Resources 환경에 대한 액세스는 제한되어 있습니다. 가상 머신(VM)이나 Microsoft 인터넷 정보 서비스(IIS)에 액세스할 수 없습니다. 또한 Microsoft SQL Server Management Studio를 통해 데이터베이스에 액세스할 수 없습니다. 

Azure 리소스 또는 Dynamics 365 Human Resources 환경에 직접 액세스할 수는 없지만 데이터에 액세스하기 위한 추가 기능이 있습니다.

- 자체 Azure 테넌트에 Azure SQL 데이터베이스를 배포하고 BYOD(Bring Your Own Database) 기능을 사용하여 데이터를 동기화할 수 있습니다. 자세한 내용은 [BYOD(Bring Your Own Database)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md)를 참조하세요.

- Dataverse 통합을 사용하여 선택한 엔터티를 Dataverse 데이터베이스에 동기화할 수 있습니다. 자세한 내용은 [Dataverse 테이블](hr-developer-entities.md)을 참조하세요. 

## <a name="how-often-is-my-production-database-backed-up"></a>내 프로덕션 데이터베이스는 얼마나 자주 백업됩니까? 

데이터베이스는 다음 빈도의 자동 백업으로 보호됩니다.

| 백업 유형 | 빈도 |
| --- | --- |
| 전체 데이터베이스 백업 | 매주 |
| 차등 데이터베이스 백업 | 12~24시간마다 |
| 트랜잭션 로그 백업 | 5~10분마다 |

Microsoft는 지난 14일 이내에 특정 시점 복원(PITR)을 수행할 수 있도록 충분한 백업을 보관합니다. 

자세한 내용은 [자동 SQL 데이터베이스 백업에 대한 자세한 내용](/azure/azure-sql/database/automated-backups-overview?tabs=single-database)을 참조하세요. 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a>내 프로덕션 데이터베이스의 백업 복사본을 요청할 수 있습니까? 

아니요. 그러나 데이터베이스 새로 고침 서비스 요청을 제출하여 프로덕션 환경을 샌드박스 환경으로 복사할 수 있습니다. 자체 Azure 테넌트에 Azure SQL 데이터베이스를 배포하고 BYOD 기능을 사용하여 프로덕션 환경에서 데이터를 동기화할 수 있습니다. 자세한 내용은 [BYOD(Bring Your Own Database)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md)를 참조하세요. 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a>라이브 전환을 위해 샌드박스 환경을 프로덕션으로 이동하려면 어떻게 해야 합니까? 

환경을 샌드박스에서 프로덕션 환경으로 이동하는 데 복사 기능을 사용할 수 없으므로 데이터 패키지를 사용하여 데이터를 프로덕션 환경으로 이동해야 합니다.  

프로젝트 전체에서 샌드박스에 구성된 엔터티 목록을 명확하게 유지하는 것이 좋습니다. 그런 다음 라이브 전환에 필요한 모든 데이터 패키지의 전환 및 마이그레이션 프로세스를 테스트합니다. 라이브로 전환할 준비가 되면 모든 데이터 패키지를 프로덕션 환경으로 수동으로 이동해야 합니다. 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a>프로덕션 환경이 다운되면 어떻게 해야 합니까? 

프로덕션 중단을 보고하려면 [프로덕션 중단 보고](../fin-ops-core/dev-itpro/lifecycle-services/report-production-outage.md)에 설명된 프로세스를 따릅니다. 

 ## <a name="see-also"></a>참고 항목

 [라이브 전환 준비](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
