---
title: 인스턴스 복사
description: Microsoft Dynamics Lifecycle Services(LCS)를 사용하여 Microsoft Dynamics 365 Human Resources 데이터베이스를 샌드박스 환경으로 복사할 수 있습니다.
author: andreabichsel
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 22aa33135535d543eb8fe437821cab7a4865d6df
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451996"
---
# <a name="copy-an-instance"></a>인스턴스 복사

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Microsoft Dynamics Lifecycle Services(LCS)를 사용하여 Microsoft Dynamics 365 Human Resources 데이터베이스를 샌드박스 환경으로 복사할 수 있습니다. 다른 샌드박스 환경이 있는 경우 해당 환경에서 대상 샌드박스 환경으로 데이터베이스를 복사할 수도 있습니다.

인스턴스를 복사하려면 다음 사항을 염두에 두세요.

- 덮어쓰려는 Human Resources 인스턴스는 샌드박스 환경이어야 합니다.

- 복사하려는 환경과 대상 환경은 동일한 지역에 있어야 합니다. 지역 간에는 복사할 수 없습니다.

- 인스턴스를 복사한 후 로그인하려면 대상 환경의 관리자여야 합니다.

- Human Resources를 복사할 때 Microsoft Power Apps 환경에 포함된 요소(앱 또는 데이터)는 복사하지 않습니다. Power Apps 환경의 요소를 복사하는 방법에 대한 자세한 내용은 [환경 복사](/power-platform/admin/copy-environment)를 참조하세요. 덮어쓰려는 Power Apps 환경은 샌드박스 환경이어야 합니다. Power Apps 프로덕션 환경을 샌드박스 환경으로 변경하려면 전역 테넌트 관리자여야 합니다. Power Apps 환경을 변경하는 데 대한 자세한 내용은 [인스턴스 전환](/dynamics365/admin/switch-instance)을 참조하세요.

- 인스턴스를 샌드박스 환경에 복사하고 샌드박스 환경을 Dataverse와 통합하려면 Dataverse 테이블에 사용자 지정 필드를 다시 적용해야 합니다. [Dataverse에 사용자 지정 필드 적용](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service)을 참조하세요.

## <a name="effects-of-copying-a-human-resources-database"></a>Human Resources 데이터베이스 복사의 효과

Human Resources 데이터베이스를 복사할 때 다음 이벤트가 발생합니다.

- 복사 프로세스는 대상 환경의 기존 데이터베이스를 지웁니다. 복사 프로세스가 완료된 후에는 기존 데이터베이스를 복구할 수 없습니다.

- 복사 프로세스가 완료될 때까지 대상 환경을 사용할 수 없습니다.

- Microsoft Azure Blob Storage의 문서는 한 환경에서 다른 환경으로 복사되지 않습니다. 결과적으로 첨부된 모든 문서와 템플릿은 복사되지 않고 원본 환경에 유지됩니다.

- "시스템 관리자" 보안 역할 및 기타 내부 서비스 사용자 계정을 제외한 모든 사용자는 사용할 수 없습니다. 관리 사용자는 다른 사용자가 시스템에 다시 들어오도록 허용하기 전에 데이터를 삭제하거나 난독 처리할 수 있습니다.

- "시스템 관리자" 보안 역할이 있는 모든 사용자는 통합 엔드포인트를 특정 서비스 또는 URL에 다시 연결하는 등의 필수 구성 변경을 수행해야 합니다.

## <a name="copy-the-human-resources-database"></a>Human Resources 데이터베이스 복사

이 작업을 완료하려면 먼저 인스턴스를 복사한 다음 Microsoft Power Platform 관리 센터에 로그인하여 Power Apps 환경을 복사합니다.

> [!WARNING]
> 인스턴스를 복사하면 대상 인스턴스에서 데이터베이스가 지워집니다. 이 프로세스 중에는 대상 인스턴스를 사용할 수 없습니다.

1. LCS에 로그인하고 복사하려는 인스턴스가 포함된 LCS 프로젝트를 선택합니다.

2. LCS 프로젝트에서 **Human Resources 앱 관리** 타일을 선택합니다.

3. 복사할 인스턴스를 선택하고 **복사** 를 선택합니다.

4. **인스턴스 복사** 작업 창에서 덮어쓸 인스턴스를 선택한 다음 **복사** 를 선택합니다. **복사 상태** 필드의 값이 **복사됨** 으로 업데이트될 때까지 기다립니다.

   ![[덮어쓸 인스턴스를 선택합니다.](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. **Power Platform** 을 선택하고 Microsoft Power Platform 관리 센터에 로그인합니다.

   ![[Power Platform을 선택합니다.](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. 복사할 Power Apps 환경을 선택한 다음 **복사** 를 선택합니다.

7. 복사 프로세스가 완료되면 대상 인스턴스에 로그인하고 Dataverse 통합을 활성화합니다. 자세한 내용과 통합에 대해서는 [Dataverse 통합 구성](./hr-admin-integration-common-data-service.md)을 참조하세요.

## <a name="data-elements-and-statuses"></a>데이터 요소 및 상태

Human Resources 인스턴스를 복사할 때 다음 데이터 요소는 복사되지 않습니다.

- **LogisticsElectronicAddress** 테이블의 이메일 주소

- **BatchJobHistory**, **BatchHistory**, **BatchConstraintHistory** 테이블의 일괄 작업 기록

- **SysEmailSMTPPassword** 테이블의 SMTP(Simple Mail Transfer Protocol) 암호

- **SysEmailParameters** 테이블의 SMTP 릴레이 서버

- **PrintMgmtSettings** 및 **PrintMgmtDocInstance** 테이블의 인쇄 관리 설정

- **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, **BatchServerGroup** 테이블의 환경별 레코드

- DocuValue 테이블의 문서 첨부 파일. 이러한 첨부 파일에는 원본 환경에서 덮어쓴 모든 Microsoft Office 템플릿이 포함됩니다.

- **PersonnelIntegrationConfiguration** 테이블의 연결 문자열

이러한 요소 중 일부는 환경별로 다르므로 복사되지 않습니다. 예로는 **BatchServerConfig** 및 **SysCorpNetPrinters** 레코드가 있습니다. 다른 요소는 지원 티켓의 양으로 인해 복사되지 않습니다. 예:

- 사용자 수용 테스트(샌드박스) 환경에서 SMTP가 계속 활성화되어 있으므로 중복 이메일이 전송될 수 있습니다.

- 일괄 작업이 여전히 활성화되므로 잘못된 통합 메시지가 전송될 수 있습니다.

- 관리자가 새로 고침 후 정리 작업을 수행하기 전에 사용자가 활성화될 수 있습니다.

또한 인스턴스를 복사하면 다음 상태가 변경됩니다.

- "시스템 관리자" 보안 역할을 가진 사용자를 제외한 모든 사용자가 **비활성화됨** 으로 설정됩니다.

- 일부 시스템 작업을 제외한 모든 일괄 작업이 **보류** 로 설정됩니다.

## <a name="environment-admin"></a>환경 관리자

관리자를 포함한 대상 샌드박스 환경의 모든 사용자가 원본 환경의 사용자로 대체됩니다. 인스턴스를 복사하기 전에 자신이 원본 환경의 관리자인지 확인하세요. 그렇지 않으면 복사가 완료된 후 대상 샌드박스 환경에 로그인할 수 없습니다.

대상 샌드박스 환경의 모든 비관리자 사용자는 샌드박스 환경에서 원치 않는 로그인을 방지하기 위해 비활성화됩니다. 관리자는 필요한 경우 사용자를 다시 활성화할 수 있습니다.

## <a name="apply-custom-fields-to-dataverse"></a>Dataverse에 사용자 지정 필드 적용

인스턴스를 샌드박스 환경에 복사하고 샌드박스 환경을 Dataverse와 통합하려면 Dataverse 테이블에 사용자 지정 필드를 다시 적용해야 합니다.

Dataverse 테이블에 노출된 각 사용자 지정 필드에 대해 다음 단계를 수행합니다.

1. 사용자 지정 필드로 이동하고 **편집** 을 선택합니다.

2. 사용자 지정 필드가 활성화된 각 cdm_* 엔터티의 **활성화됨** 필드를 선택 취소합니다.

3. **변경 내용 적용** 을 선택합니다.

4. **편집** 을 다시 선택합니다.

5. 사용자 지정 필드가 활성화된 각 cdm_* 엔터티의 **활성화됨** 필드를 선택합니다.

6. **변경 내용 적용** 을 다시 선택합니다.

선택 취소, 변경 내용 적용, 다시 선택 및 다시 적용 과정에서 스키마가 사용자 지정 필드를 포함하도록 Dataverse에서 업데이트하라는 메시지가 표시됩니다.

사용자 지정 필드에 대한 자세한 내용은 [사용자 지정 필드 만들기 및 사용](../fin-ops-core/fin-ops/get-started/user-defined-fields.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources 프로비전](hr-admin-setup-provision.md)</br>
[인스턴스 제거](hr-admin-setup-remove-instance.md)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
