---
title: 재무 및 운영 앱 업그레이드 문제 해결
description: 이번에는 Finance 및 Operations 앱의 업그레이드와 관련된 문제를 해결하는 데 도움이 되는 문제 해결 정보를 제공합니다.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c7c036ef44b0470c9b3f8087e7b5b1e16dde1b34
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460653"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>재무 및 운영 앱 업그레이드 문제 해결

[!include [banner](../../includes/banner.md)]





이번에는 Finance 및 Operations 앱 Dataverse 간의 이중 쓰기 통합에 대한 문제 해결 정보를 제공하고 . 특히 재무 및 운영 앱의 업그레이드와 관련된 문제를 해결하는 데 도움이 되는 정보를 제공합니다.

> [!IMPORTANT]
> 이 항목에서 해결하는 일부 문제에는 시스템 관리자 역할 또는 Microsoft Azure Active Directory(Azure AD) 테넌트 관리자 자격 증명이 필요할 수 있습니다. 각 문제에 대한 섹션에서는 특정 역할 또는 자격 증명이 필요한지 여부를 설명합니다.

## <a name="database-synchronization-errors"></a>데이터베이스 동기화 오류

**문제를 해결하는 데 필요한 역할:** 시스템 관리자

**DualWriteProjectConfiguration** 테이블을 사용하여 Finance and Operations 앱을 플랫폼 업데이트 30으로 업데이트하려고 하면 다음 예와 유사한 오류 메시지가 나타날 수 있습니다.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

문제를 해결하려면 다음 단계를 따르십시오.

1. 재무 및 운영 앱용 가상 머신(VM)에 로그인합니다.
2. Visual Studio 관리자로 열고 AOT(애플리케이션 개체 트리)를 엽니다.
3. **DualWriteProjectConfiguration** 을 검색합니다.
4. AOT에서 **DualWriteProjectConfiguration** 을 마우스 오른쪽 버튼으로 클릭하고 **새 프로젝트에 추가** 를 선택합니다. **확인** 을 선택하여 기본 옵션을 사용하는 새 프로젝트를 만듭니다.
5. 솔루션 탐색기에서 **프로젝트 속성** 을 마우스 오른쪽 버튼으로 클릭하고 **빌드 시 데이터베이스 동기화** 를 **True** 로 설정합니다.
6. 프로젝트를 빌드하고 빌드가 성공했는지 확인합니다.
7. **Dynamics 365** 메뉴에서 **데이터베이스 동기화** 를 선택합니다.
8. 전체 데이터베이스 **동기화** 를 수행하려면 동기화를 선택합니다.
9. 전체 데이터베이스 동기화가 성공한 후 Microsoft Dynamics LCS(Lifecycle Services)에서 데이터베이스 동기화 단계를 다시 실행하고 해당되는 경우 수동 업그레이드 스크립트를 사용하여 업데이트를 계속 진행할 수 있습니다.

## <a name="missing-table-columns-issue-on-maps"></a>지도에서 누락된 테이블 열 문제

**문제를 해결하는 데 필요한 역할:** 시스템 관리자

**이중 쓰기** 페이지에서 다음 예시와 유사한 오류 메시지가 나타날 수 있습니다.

*스키마에 소스 필드 \<field name\>가 없습니다.*

![누락된 소스 열 오류 메시지의 예입니다.](media/error_missing_field.png)

문제를 해결하려면 먼저 다음 단계에 따라 열이 테이블에 있는지 확인하십시오.

1. 재무 및 운영 앱용 VM에 로그인합니다.
2. **작업 영역 \> 데이터 관리** 로 이동하여 **프레임워크 매개 변수** 타일을 선택한 다음, **테이블 설정** 탭에서 **테이블 목록 새로 고침** 을 선택하여 테이블을 새로 고칩니다.
3. **작업 공간 \> 데이터 관리** 로 이동하여 **데이터 테이블** 탭을 선택하고 테이블이 나열되는지 확인합니다. 테이블이 나열되지 않으면 재무 및 운영 앱용 VM에 로그인하고 테이블을 사용할 수 있는지 확인합니다.
4. 재무 및 운영 앱의 **이중 쓰기** 페이지에서 **테이블 매핑** 페이지를 엽니다.
5. 테이블 매핑의 열을 자동으로 채우려면 **테이블 목록 새로 고침** 을 선택합니다.

문제가 여전히 해결되지 않으면 다음 단계를 따르십시오.

> [!IMPORTANT]
> 이 단계는 테이블을 삭제한 다음 다시 추가하는 프로세스를 안내합니다. 문제를 방지하려면 단계를 정확히 따르십시오.

1. 재무 및 운영 앱에서 **작업 공간 \> 데이터 관리** 로 이동하고 **데이터 테이블** 타일을 선택합니다.
2. 속성이 누락된 테이블을 찾으십시오. 도구 모음에서 **대상 매핑 수정** 을 클릭합니다.
3. **대상에 스테이징 매핑** 창에서 **매핑 생성** 을 클릭합니다.
4. 재무 및 운영 앱의 **이중 쓰기** 페이지에서 **테이블 매핑** 페이지를 엽니다.
5. 속성이 맵에 자동으로 채워지지 않으면 **속성 추가** 버튼을 클릭한 다음 **저장** 을 클릭하여 수동으로 추가합니다. 
6. 맵을 선택하고 **실행** 을 클릭합니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]