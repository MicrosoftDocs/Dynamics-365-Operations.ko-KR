---
title: 재무 및 운영 앱의 이중 쓰기 문제 해결
description: 이번에는 재무 및 운영 앱의 이중 쓰기 모듈 문제를 해결하는 데 도움이 되는 문제 해결 정보를 제공합니다.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: db49c6a4555f39800362a5b248f9757b07ee5481
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460654"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>재무 및 운영 앱의 이중 쓰기 문제 해결

[!include [banner](../../includes/banner.md)]



이번에는 Finance 및 Operations 앱 Dataverse 간의 이중 쓰기 통합에 대한 문제 해결 정보를 제공하고 . 특히 재무 및 운영 앱의 **이중 쓰기** 모듈 문제를 해결하는 데 도움이 되는 정보를 제공합니다.

> [!IMPORTANT]
> 이 항목에서 해결하는 일부 문제에는 시스템 관리자 역할 또는 Microsoft Azure Active Directory(Azure AD) 테넌트 관리자 자격 증명이 필요할 수 있습니다. 각 문제에 대한 섹션에서는 특정 역할 또는 자격 증명이 필요한지 여부를 설명합니다.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>재무 및 운영 앱에서 이중 쓰기 모듈을 로드할 수 없습니다.

데이터 관리 작업 영역에서 **이중 쓰기** 타일을 선택하여 **이중 쓰기** 페이지를 열 수 없으면 **데이터 통합** 서비스가 다운되었을 수 있습니다. 데이터 통합 서비스의 다시 시작을 요청하려면 지원 티켓을 만드십시오.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>새 테이블 맵을 만들려고 할 때 오류가 발생했습니다.

**문제를 해결하는 데 필요한 자격 증명:** 이중 쓰기를 설정한 동일한 사용자입니다.

이중 쓰기를 위해 새 테이블을 구성하려고 하면 다음 오류 메시지가 나타날 수 있습니다. 맵을 생성할 수 있는 유일한 사용자는 이중 쓰기 연결을 설정한 사용자입니다.

*응답 상태 코드는 성공을 나타내지 않습니다. 401(무단).*

## <a name="error-when-you-open-the-dual-write-user-interface"></a>이중 쓰기 사용자 인터페이스를 열 때 오류 발생

**데이터 관리** 작업 영역에서 이중 쓰기에 액세스하려고 하면 다음 오류 메시지가 나타날 수 있습니다.

*login.microsoftonline.com이 연결을 거부했습니다.*

이 문제를 해결하려면 Microsoft Edge, Chromium의 시크릿 창 또는 Google Chrome의 시크릿 창에서 InPrivate 창을 사용하여 로그인하십시오. 또한 타사 쿠키의 차단을 해제하거나 지워야 합니다.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>이중 쓰기를 위해 환경을 연결하거나 새 테이블 매핑을 추가할 때 오류 발생

**문제를 해결하는 데 필요한 역할:** 재무 및 운영 앱 및 Dataverse.

지도를 연결하거나 생성할 때 다음 오류가 발생할 수 있습니다.

```dos
Response status code does not indicate success: 403 (tokenexchange).
Session ID: \<your session id\>
Root activity ID: \<your root activity\> id
```

이 오류는 이중 쓰기를 연결하거나 맵을 생성할 수 있는 충분한 권한이 없는 경우에 발생할 수 있습니다. 이 오류는 이중 쓰기 연결을 해제하지 않고 Dataverse 환경을 재설정한 경우에도 발생할 수 있습니다. 재무 및 운영 앱 Dataverse 모두에서 시스템 관리자 역할이 있는 모든 사용자는 환경을 연결할 수 있습니다. 이중 쓰기 연결을 설정한 사용자만 새 테이블 맵을 추가할 수 있습니다. 설정 후 시스템 관리자 역할을 가진 모든 사용자는 상태를 모니터링하고 매핑을 편집할 수 있습니다.

## <a name="error-when-you-stop-the-table-mapping"></a>테이블 매핑을 중지할 때 오류가 발생했습니다.

테이블 매핑을 중지하려고 하면 다음 오류 메시지가 나타날 수 있습니다.

*\[금지됨\], \[{"status":403,"source":"","message":'토큰 교환 오류: 사용자는 연결 dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx에 액세스할 수 없습니다"}\], 원격 서버에서 오류를 반환했습니다. (403) 금지.*

이 오류는 연결된 Dataverse 환경을 사용할 수 없을 때 발생합니다.

문제를 해결하려면 데이터 통합 팀을 위한 티켓을 만드십시오. 데이터 통합 팀이 맵을 백엔드에서 **실행 중이 아님** 으로 표시할 수 있도록 네트워크 추적을 연결하십시오.

## <a name="errors-while-trying-to-start-a-table-mapping"></a>테이블 매핑을 시작하는 동안 오류가 발생했습니다.

### <a name="unable-to-complete-initial-data-sync"></a>초기 데이터 동기화를 완료할 수 없음

초기 데이터 동기화를 실행하려고 하면 다음과 같은 오류가 표시될 수 있습니다.

*초기 데이터 동기화를 완료할 수 없습니다. 오류: 이중 쓰기 실패 - 플러그인 등록 실패: 이중 쓰기 조회 메타데이터를 작성할 수 없습니다. 오류 개체 참조가 개체의 인스턴스로 설정되지 않았습니다.*

매핑의 해당 상태를 **Running** 으로 설정하려고 하면 이 오류가 나타날 수 있습니다. 수정 사항은 오류의 원인에 따라 다릅니다.

+ 매핑에 종속 매핑이 있는 경우 이 테이블 매핑의 종속 매핑을 활성화해야 합니다.
+ 매핑에 원본 또는 대상 열이 누락되었을 수 있습니다. 재무 및 운영 앱의 열이 누락된 경우 지도에서 [누락된 테이블 열 문제](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps) 섹션의 단계를 따르십시오. Dataverse의 열이 누락된 경우 매핑에서 **테이블 새로 고침** 버튼을 클릭하여 열이 매핑에 자동으로 다시 채워지도록 합니다.

### <a name="version-mismatch-error-and-upgrading-dual-write-solutions"></a>버전 불일치 오류 및 이중 쓰기 솔루션 업그레이드

테이블 매핑을 실행하려고 하면 다음 오류 메시지가 나타날 수 있습니다.

+ *고객 그룹(msdyn_customergroups): 이중 쓰기 실패 - Dynamics 365 for Sales 솔루션 'Dynamics365Company'에 버전이 일치하지 않습니다. Version: '2.0.2.10' 필수 버전: '2.0.133'*
+ *Dynamics 365 for Sales 솔루션 'Dynamics365FinanceExtended'에 버전이 일치하지 않습니다. Version: '1.0.0.0' 필수 버전: '2.0.227'*
+ *Dynamics 365 for Sales 솔루션 'Dynamics365FinanceAndOperationsCommon'에 버전이 일치하지 않습니다. Version: '1.0.0.0' 필수 버전: '2.0.133'*
+ *Dynamics 365 for Sales 솔루션 'CurrencyExchangeRates'에 버전이 일치하지 않습니다. Version: '1.0.0.0' 필수 버전: '2.0.133'*
+ *Dynamics 365 for Sales 솔루션 'Dynamics365SupplyChainExtended'에 버전이 일치하지 않습니다. Version: '1.0.0.0' 필수 버전: '2.0.227'*

문제를 해결하려면 Dataverse에서 이중 쓰기 솔루션을 업데이트하십시오. 필요한 솔루션 버전과 일치하는 최신 솔루션으로 업그레이드해야 합니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
