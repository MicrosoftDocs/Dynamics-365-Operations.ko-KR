---
title: 재무 및 운영 앱에서 이중 쓰기 구성을 확인하고 Dataverse
description: 이번에는 재무 및 운영 앱과 Dataverse에서 이중 쓰기가 구성되어 있는지 여부를 확인하는 방법에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 3fa16a450032464e445ae166f0699fe0dc388071
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460647"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>재무 및 운영 앱에서 이중 쓰기 구성을 확인하고 Dataverse

[!include [banner](../../includes/banner.md)]





이번에는 Finance 및 Operations 앱 Dataverse 간의 이중 쓰기 통합에 대한 문제 해결 정보를 제공하고 . 특히 재무 및 운영 앱과 Dataverse에서 이중 쓰기가 구성되어 있는지 여부를 확인하는 방법을 설명합니다.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>재무 및 운영 앱에서 이중 쓰기가 구성되어 있는지 확인

업데이트를 위해 행을 저장하려고 할 때 표시되는 오류가 이중 쓰기에서 오는지 확인하려면 먼저 이중 쓰기가 구성되어 있는지 확인하십시오.

+ 재무 및 운영 앱에서 관리자 권한이 있는 경우 **작업 영역 \> 데이터 관리** 로 이동하고 **이중 쓰기** 타일을 선택합니다. 연결된 환경의 세부 정보와 실행 중인 테이블 맵 목록이 표시되면 이중 쓰기가 구성된 것입니다.

    ![관리자 권한이 있을 때 재무 및 운영 앱 연결을 확인합니다.](media/verify_fin_ops_1.png)

+ 관리자 권한이 없으면 *엔터티에 데이터를 쓸 수 없음 \<entity name\>* 오류 메시지가 표시됩니다. 다음 그림의 예시에서는 Dataverse 이중 쓰기가 구성되어 있지만 고객 그룹 및 결제 조건 참조 데이터가 에 존재하지 않기 때문에 Finance and Operations 앱에서 고객 행을 생성할 수 없습니다.

    ![관리자 권한이 없을 때 재무 및 운영 앱 연결을 확인합니다.](media/verify_fin_ops_2.png)

Finance 및 Operations 앱에서 데이터를 생성할 때 문제를 해결하는 방법에 대한 자세한 내용은 [라이브 동기화 문제 해결](dual-write-troubleshooting-live-sync.md)을 참조하십시오.

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>이중 쓰기가 구성되어 있는지 확인하십시오. Dataverse

데이터를 생성할 때 Dataverse의 페이지에 **회사** 열이 표시되면 이중 쓰기가 구성된 것입니다.

![Dataverse 연결 확인 중.](media/verify_cds.png)

Dataverse에서 데이터를 생성할 때 문제를 해결하는 방법에 대한 자세한 내용은 [라이브 동기화 문제 해결](dual-write-troubleshooting-live-sync.md)을 참조하십시오.

Dataverse에서 데이터를 생성하는 동안 오류가 발생한 경우 오류 세부 정보를 보는 방법에 대한 자세한 내용은 [Dataverse 플러그인 추적 로그인 활성화 및 보기](dual-write-troubleshooting.md#enable-view-trace)를 참조하여 오류 세부 정보를 보십시오.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]