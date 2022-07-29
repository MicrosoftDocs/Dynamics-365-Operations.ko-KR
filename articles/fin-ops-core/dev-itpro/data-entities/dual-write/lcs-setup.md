---
title: Lifecycle Services의 이중 쓰기 설정
description: 이 항목에서는 Microsoft Dynamics Lifecycle Services(LCS)에서 이중 쓰기 연결을 설정하는 방법에 대해 설명합니다.
author: laneswenka
ms.date: 08/03/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 825d6a4b3462077d0f4b3f4275792ea0fe5152df
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460683"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Lifecycle Services의 이중 쓰기 설정

[!include [banner](../../includes/banner.md)]



이 항목에서는 Microsoft Dynamics Lifecycle Services(LCS)에서 이중 쓰기를 사용하는 방법에 대해 설명합니다.

## <a name="prerequisites"></a>전제 조건

다음 주제에 설명된 대로 Power Platform 통합을 완료해야 합니다.

+ [Power Platform 통합 - 환경 배포 중 활성화](../../power-platform/enable-power-platform-integration.md#enable-during-deploy)
+ [Power Platform 통합 - 환경 배포 후 활성화](../../power-platform/enable-power-platform-integration.md#enable-after-deploy)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>새 Dataverse 환경에 대해 이중 쓰기 설정

LCS **환경 세부 정보** 페이지에서 이중 쓰기를 설정하려면 다음 단계를 따르세요.

1. **환경 세부 정보** 페이지에서 **Power Platform 통합** 섹션을 확장합니다.

2. **이중 쓰기 응용 프로그램** 단추를 선택합니다.

    ![Power Platform 통합.](media/powerplat_integration_step2.png)

3. 계약조건을 검토한 다음 **구성** 을 선택합니다.

4. 계속하려면 **확인** 을 선택합니다.

5. 환경 세부 정보 페이지를 주기적으로 새로 고쳐 진행 상황을 모니터링할 수 있습니다. 설치에는 일반적으로 30분 미만이 소요됩니다.  

6. 설정이 완료되면 프로세스가 성공했는지 또는 실패했는지 알려주는 메시지가 표시됩니다. 설정에 실패한 경우 관련 오류 메시지가 표시됩니다. 다음 단계로 이동하기 전에 오류를 수정해야 합니다.

7. **Power Platform 환경에 연결** 을 선택하여 Dataverse와 현재 환경의 데이터베이스 사이의 링크를 만듭니다. 일반적으로 5분 미만이 소요됩니다.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Power Platform 환경에 연결.":::

8. 연결이 완료되면 하이퍼링크가 표시됩니다. 링크를 사용하여 재무 및 운영 환경의 이중 쓰기 관리 영역에 로그인합니다. 여기에서 엔터티 매핑을 설정할 수 있습니다.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>기존 Dataverse 환경에 대해 이중 쓰기 설정

기존 Dataverse 환경에 이중 쓰기를 설정하려면 Microsoft [지원 티켓](../../lifecycle-services/lcs-support.md)을 만들어야 합니다. 티켓에는 다음이 포함되어야 합니다.

+ 재무 및 운영 환경 ID입니다.
+ Lifecycle Services의 환경 이름입니다.
+ Power Platform 관리 센터의 Dataverse 조직 ID 또는 Power Platform 환경 ID. 티켓에서 ID가 Power Platform 통합에 사용되도록 요청합니다.

> [!NOTE]
> LCS를 사용하여 환경을 연결 해제할 수 없습니다. 환경 연결을 해제하려면 재무 및 운영 환경에서 **데이터 통합** 작업 공간을 선택한 다음 **연결 해제** 를 선택합니다.

## <a name="linking-mismatch"></a>연결 불일치

LCS 환경이 Dataverse 인스턴스에 연결되고, 이중 쓰기 환경이 다른 Dataverse 인스턴스에 연결될 수 있습니다. 이 연결 불일치로 인해 예기치 않은 동작이 발생할 수 있으며 결국 잘못된 환경으로 데이터를 보낼 수 있습니다. 이중 쓰기에 권장되는 환경은 Power Platform 통합의 일부로 생성되는 환경이며 장기적으로 이것이 환경 간의 연결을 설정하는 유일한 방법이 될 것입니다.

환경에 연결 불일치가 있는 경우 LCS는 환경 세부 정보 페이지에 "Microsoft에서 사용자 환경이 이중 쓰기를 통해 지정된 Power Platform 통합과 다른 대상에 연결되어 있음을 감지했으며, 이는 권장되지 않습니다."

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Power Platform통합 링크가 일치하지 않습니다.":::

이 오류가 발생하면 필요에 따라 두 가지 옵션이 있습니다.

+ LCS 환경 세부 정보 페이지에 지정된 대로 [이중 쓰기 환경 연결 해제 및 다시 연결(연결 재설정 또는 변경)](relink-environments.md#scenario-reset-or-change-linking). 이것은 Microsoft 지원 없이 실행할 수 있기 때문에 이상적인 옵션입니다.  
+ 링크를 이중 쓰기로 유지하려면 이전 섹션에 설명된 대로 Microsoft 지원에 도움을 요청하여 Power Platform 통합이 기존 Dataverse 환경을 사용하도록 변경하세요.  

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
