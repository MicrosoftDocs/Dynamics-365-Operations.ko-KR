---
title: 초기 설정 중 문제 해결
description: 이번에는 이중 쓰기 통합의 초기 설정 중에 발생하는 문제를 해결하는 데 도움이 되는 정보를 제공합니다.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 9a70de253eff2a3273be4a31ab32757bb014328f
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460652"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>초기 설정 중 문제 해결

[!include [banner](../../includes/banner.md)]



이번에는 Finance 및 Operations 앱 Dataverse 간의 이중 쓰기 통합에 대한 문제 해결 정보를 제공하고 . 특히 이중 쓰기 통합의 초기 설정 중에 발생할 수 있는 문제를 해결하는 데 도움이 되는 정보를 제공합니다.

> [!IMPORTANT]
> 이 항목에서 해결하는 일부 문제에는 시스템 관리자 역할 또는 Microsoft Azure Active Directory(Azure AD) 테넌트 관리자 자격 증명이 필요할 수 있습니다. 각 문제에 대한 섹션에서는 특정 역할 또는 자격 증명이 필요한지 여부를 설명합니다.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>재무 및 운영 앱을 연결할 수 없습니다. Dataverse

**이중 쓰기를 설정하는 데 필요한 역할:** 재무 및 운영 앱의 시스템 관리자 및 Dataverse.

페이지에 대한 **Dataverse 설정 링크** 의 오류는 일반적으로 불완전한 설정 또는 권한 문제로 인해 발생합니다. 다음 그림과 같이 전체 상태 확인이 페이지에 대한 **Dataverse 설정 링크** 를 통과하는지 확인합니다. 전체 상태 확인을 통과하지 않으면 이중 쓰기를 연결할 수 없습니다.

![상태 확인에 성공했습니다.](media/health_check.png)

재무 및 운영 및 Dataverse 환경을 연결하려면 Azure AD 테넌트 관리자 자격 증명이 있어야 합니다. 환경을 연결한 후 사용자는 계정 자격 증명을 사용하여 로그인하고 기존 테이블 맵을 업데이트할 수 있습니다.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>이중 쓰기를 위해 연결할 수 있는 법적 테이블 또는 회사의 수에 대한 제한 찾기

맵을 활성화하려고 할 때 다음 오류 메시지가 나타날 수 있습니다.

*이중 쓰기 실패 - 플러그인 등록 실패: [(프로젝트 DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea에 대한 파티션 맵을 가져올 수 없습니다. 오류 DWM 1ae35e60-4bc2-4905-88ea-69efd3b29260 7f12cb89-1550-42e2-858e-4761fc1443ea매핑에 허용된 최대 파티션 초과--)], 하나 이상의 오류가 발생했습니다.*

환경을 연결할 때 현재 제한은 약 40개의 법적 테이블입니다. 이 오류는 맵을 활성화하려고 하고 환경 간에 40개 이상의 법적 테이블이 연결된 경우 발생합니다.

## <a name="connection-set-failed-while-linking-environment"></a>환경을 연결하는 동안 연결 설정에 실패했습니다.

이중 쓰기 환경을 연결하는 동안 오류 메시지와 함께 작업이 실패합니다.

*연결 집합을 저장하지 못했습니다! 동일한 키를 가진 항목이 이미 추가되었습니다.*

이중 쓰기는 동일한 이름을 가진 여러 법인/회사를 지원하지 않습니다. 예를 들어, 'DAT' 이름을 가진 두 개의 회사가 있는 경우 Dataverse 이 오류 메시지가 표시됩니다.

고객 차단을 해제하려면 Dataverse의 **cdm_company** 테이블에서 중복 기록을 제거하십시오. 또한 **cdm_company** 테이블에 빈 이름의 기록이 있는 경우 해당 기록을 제거하거나 수정하십시오.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>재무 및 운영 앱에서 이중 쓰기 페이지를 열 때 오류 발생

이중 쓰기 Dataverse 환경을 연결하려고 하면 다음 오류 메시지가 나타날 수 있습니다.

*응답 상태 코드는 성공을 나타내지 않습니다. 404 (찾을 수 없음).*

이 오류는 앱 동의 단계가 완료되지 않은 경우 발생합니다. 테넌트 관리자 계정을 사용하여 로그온하여 `portal.azure.com` 동의가 제공되었는지 확인할 수 있으며 `33976c19-1db5-4c02-810e-c243db79efde` ID가 있는 타사 앱이 AAD의 엔터프라이즈 애플리케이션 목록에 표시되는지 확인할 수 있습니다. 그렇지 않은 경우 다음 섹션에 설명된 대로 동의 단계를 다시 실행합니다.

### <a name="providing-app-consent"></a>앱 동의 제공

+ 관리자 자격 증명으로 다음 URL을 시작합니다.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ 동의하려면 **수락** 을 선택합니다. 테넌트에 앱(`id=33976c19-1db5-4c02-810e-c243db79efde` 와 함께)을 설치하는 데 동의합니다.
+ 이 앱은 재무 및 운영 앱과 Dataverse 통신하는 데 필요합니다.

    ![초기 동기화 설정 문제 해결.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> 그래도 작동하지 않으면 Chrome의 비공개 모드 또는 Microsoft Edge 시크릿 모드에서 URL을 실행하십시오.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>재무 및 운영 환경을 검색할 수 없음

다음과 같은 오류 메시지가 나타날 수 있습니다.

*재무 및 운영 앱 환경 \*\*\*.cloudax.dynamics.com을 검색할 수 없습니다.*

환경을 검색할 수 없는 문제를 일으킬 수 있는 두 가지가 있습니다.

+ 로그인에 사용된 사용자는 Finance and Operations 인스턴스와 동일한 테넌트에 있지 않습니다.
+ 검색에 문제가 있는 Microsoft에서 호스팅하는 일부 레거시 재무 및 운영 인스턴스가 있습니다. 이 문제를 해결하려면 Finance and Operations 인스턴스를 업데이트하십시오. 업데이트로 환경을 검색할 수 있게 됩니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
