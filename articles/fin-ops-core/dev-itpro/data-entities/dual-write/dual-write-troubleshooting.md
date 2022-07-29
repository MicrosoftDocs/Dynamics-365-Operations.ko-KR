---
title: 일반적인 문제 해결
description: 이번에는 Finance 및 Operations 앱 Dataverse 간의 이중 쓰기 통합에 대한 일반적인 문제 해결 정보를 제공합니다.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: f6f5b9f26990e2f4db9bf69040a6c4be31400b40
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460649"
---
# <a name="general-troubleshooting"></a>일반적인 문제 해결

[!include [banner](../../includes/banner.md)]



이번에는 Finance 및 Operations 앱 Dataverse 간의 이중 쓰기 통합에 대한 일반적인 문제 해결 정보를 제공합니다.

> [!IMPORTANT]
> 이 항목에서 해결하는 일부 문제에는 시스템 관리자 역할 또는 Microsoft Azure Active Directory(Azure AD) 테넌트 관리자 자격 증명이 필요할 수 있습니다. 각 문제에 대한 섹션에서는 특정 역할 또는 자격 증명이 필요한지 여부를 설명합니다.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>오류 세부 정보를 보려면 Dataverse 플러그인 추적 로그인을 활성화하고 봅니다.

**추적 로그를 켜고 오류를 보는 데 필요한 역할:** 시스템 관리자

추적 로그를 켜려면 다음 단계를 따르십시오.

1. 고객 참여 앱에 로그인하고 **설정** 페이지를 연 다음 **시스템** 에서 **관리** 를 선택합니다.
2. **관리** 페이지에서 **시스템 설정** 을 선택합니다.
3. **사용자 지정** 탭의 **플러그인 및 사용자 지정 워크플로 활동 추적** 열에서 **모두** 를 선택하여 플러그인 추적 로그를 활성화합니다. 예외가 발생한 경우에만 추적 로그를 기록하려면 대신 **예외** 를 선택할 수 있습니다.


추적 로그를 보려면 다음 단계를 따르십시오.

1. 고객 참여 앱에 로그인하고 **설정** 페이지를 연 다음 **사용자 지정** 에서 **플러그인 추적 로그** 를 선택합니다.
2. **유형 이름** 열이 **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin** 으로 설정된 추적 로그를 찾습니다.
3. 전체 로그를 보려면 항목을 두 번 클릭한 다음 **실행** FastTab에서 **메시지 블록** 텍스트를 검토합니다.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>재무 및 운영 앱의 실시간 동기화 문제를 해결하기 위해 디버그 모드 활성화

**오류를 보기 위한 필수 역할:** 시스템 관리자

Dataverse에서 발생하는 이중 쓰기 오류는 재무 및 운영 앱에 나타날 수 있습니다. 오류에 대한 자세한 로깅을 활성화하려면 다음 단계를 따르십시오.

1. 재무 및 운영 앱의 모든 프로젝트 구성에는 **DualWriteProjectConfiguration** 테이블에 **IsDebugMode** 플래그가 있습니다.
2. Excel 추가 기능을 사용하여 **DualWriteProjectConfiguration** 을 엽니다. 추가 기능을 사용하려면 재무 및 운영 Excel 추가 기능에서 디자인 모드를 활성화하고 **DualWriteProjectConfiguration** 을 시트에 추가합니다. 자세한 내용은 [Excel로 엔터티 데이터 보기 및 업데이트](../../office-integration/use-excel-add-in.md)를 참조하십시오.
3. 프로젝트에서 **IsDebugMode** 를 **예** 로 설정합니다.
4. 오류를 생성하는 시나리오를 실행하십시오.
5. 자세한 로그는 **DualWriteErrorLog** 테이블에 저장됩니다.
6. 테이블 브라우저에서 데이터를 조회하려면 다음 링크를 사용하십시오. `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`, 필요에 따라 `999` 교체합니다.
7. 플랫폼 업데이트 37 이상에서 사용할 수 있는 [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe) 이후에 다시 업데이트하십시오. 이 수정 사항이 설치되어 있으면 디버그 모드에서 더 많은 로그를 캡처합니다.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>재무 및 운영 앱용 가상 머신에서 동기화 오류 확인

**오류를 보기 위한 필수 역할:** 시스템 관리자

1. Microsoft Dynamics Lifecycle Services(LCS)에 로그인합니다.
2. 이중 쓰기 테스트를 수행하도록 선택한 LCS 프로젝트를 엽니다.
3. **클라우드 호스팅 환경** 타일을 선택합니다.
4. 원격 데스크톱을 사용하여 재무 및 운영 앱용 가상 머신(VM)에 로그인합니다. LCS에 표시된 로컬 계정을 사용하십시오.
5. 이벤트 뷰어를 엽니다.
6. **애플리케이션 및 서비스 로그 \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational** 을 선택합니다.
7. 최근 오류 목록을 검토합니다.

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>재무 및 운영 앱에서 다른 Dataverse 환경 연결 해제 및 연결

**환경 연결을 해제하는 데 필요한 역할:** 재무 및 운영 앱 또는 Dataverse.

1. 재무 및 운영 앱에 로그인합니다.
2. **작업 공간 \> 데이터 관리** 로 이동하고 **이중 쓰기** 타일을 선택합니다.
3. 실행 중인 매핑을 모두 선택한 다음 **중지** 를 선택합니다.
4. **환경 연결 해제** 를 선택합니다.
5. **예** 를 선택하여 작업을 확인합니다.

이제 새 환경을 연결할 수 있습니다.

## <a name="unable-to-view-the-sales-order-line-information-form"></a>판매 주문 라인 정보 양식을 볼 수 없습니다. 

Dynamics 365 Sales에서 판매 주문을 생성할 때 **+ 제품 추가** 를 클릭하면 Dynamics 365 Project Operations 주문 라인 양식으로 리디렉션될 수 있습니다. 해당 양식에서 판매 주문 라인 **정보** 양식을 볼 수 있는 방법은 없습니다. **정보** 옵션은 **새 주문 라인** 아래의 드롭다운에 표시되지 않습니다. 이는 Project Operations이 사용자 환경에 설치되었기 때문에 발생합니다.

**정보** 양식 옵션을 다시 활성화하려면 다음 단계를 따르십시오.

1. **주문 라인** 테이블로 이동합니다.
2. 양식 노드에서 **정보** 양식을 찾으십시오.
3. **정보** 양식을 선택하고 **보안 역할 사용** 을 클릭하십시오.
4. 보안 설정을 **모든 사람에게 표시** 로 변경합니다.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>추적을 지원 티켓에 첨부할 수 있도록 네트워크 추적을 활성화하고 저장하는 방법

지원 팀은 일부 문제를 해결하기 위해 네트워크 추적을 검토해야 할 수 있습니다. 테스트 그룹을 만들려면 다음 단계를 따르십시오.

### <a name="chrome"></a>Chrome

1. 열린 탭에서 **F12** 키를 누르거나 **개발자 도구** 를 선택하여 개발자 도구를 엽니다.
2. **네트워크** 탭을 열고 필터 텍스트 상자에 **integ** 를 입력합니다.
3. 시나리오를 실행하고 기록되는 요청을 관찰하십시오.
4. 항목을 마우스 오른쪽 버튼으로 클릭하고 **모두 콘텐츠가 있는 HAR로 저장** 을 선택합니다.

### <a name="microsoft-edge"></a>Microsoft Edge

1. 열린 탭에서 **F12** 키를 누르거나 **개발자 도구** 를 선택하여 개발자 도구를 엽니다.
2. **네트워크** 탭을 엽니다.
3. 시나리오를 실행합니다.
4. **저장** 을 선택하여 결과를 HAR로 내보냅니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
