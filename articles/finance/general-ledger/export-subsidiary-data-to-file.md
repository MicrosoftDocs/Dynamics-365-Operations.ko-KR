---
title: 파일로 자회사 데이터 내보내기
description: 이 항목에서는 Microsoft Dynamics 365 Finance에서 데이터를 내보낸 다음 이를 통합 법인으로 가져오기 위해 준비하는 방법을 설명합니다.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 02ae9945f7b67fb64be78a024910d7e1151c7446fd54b71034c5ba448c00b081
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450727"
---
# <a name="export-subsidiary-data-to-files"></a>파일로 자회사 데이터 내보내기

[!include [banner](../includes/banner.md)]

자회사 데이터를 통합 법인으로 가져올 수 있는 파일로 내보낼 준비를 하려면 **내보내기** 페이지(**시스템 관리 \> 작업 영역 \> 가져오기/내보내기**)를 사용합니다. 가져오기 및 내보내기 프로세스에 대한 자세한 내용은 [데이터 가져오기 및 내보내기 작업 개요](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)를 참조하세요.

1. 통합 프로세스를 위한 법인을 만듭니다. 법인을 만드는 방법에 대한 자세한 내용은 [법인 만들기](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md)를 참조하세요. 자세한 내용은 [통합 프로세스에 사용할 법인 비교](prepare-company-for-consolidation.md) 및 [통합을 위한 자회사 법인 설정](set-up-subsidiary-company-for-consolidation.md)을 참조하세요. 

2. **통합 \> 회사 잔액 내보내기** 를 선택합니다. **회사 잔액 내보내기** 페이지의 **기준** 탭에서 다음 필드를 설정하여 통합 세부 정보를 지정합니다.

    | 필드                             | 설명 |
    |-----------------------------------|-------|
    | 주 계정                      | 통합할 계정을 지정합니다. 모든 계정을 포함하려면 이 필드를 비워 둡니다. |
    | 통합 계정 사용         | 통합 계정을 지정한 경우 이 옵션을 **예** 로 설정합니다. |
    | 통합 계정 선택 위치 | **주 계정** 또는 **통합 계정 그룹** 을 선택합니다. |
    | 통합 계정 그룹       | 선택한 통합 계정에 대한 통합 계정 그룹을 선택합니다. |
    | 통합 기간              | 통합 "시작" 및 "종료" 날짜를 지정합니다. |
    | 실제 금액 포함            | 실제 금액을 포함하려면 이 옵션을 **예** 로 설정합니다. |
    | 예산 금액 포함            | 통합에 예산 금액을 포함하려면 이 옵션을 **예** 로 설정합니다. |
    | 예산 모델                     | 포함할 예산 모델을 지정합니다. |

3. **재무 차원** 탭에서 통합 세부 정보를 지정합니다.

    - 자회사 계정의 거래에서 통합 법인의 거래로 이전해야 하는 재무 차원 정보를 지정합니다.
    - 목록에서 재무 차원을 선택합니다.
    - 통합된 각 재무 차원의 올바른 사양을 식별합니다. 사용 가능한 옵션에는 **차원**, **그룹 차원**, **회사 계정**, **계정** 이 포함됩니다.

        > [!NOTE]
        > **그룹 차원** 옵션을 사용하면 통합 중인 회사 그룹에 사용되는 차원 값을 정의할 수 있습니다.

    - 통합할 세그먼트 순서를 지정합니다.

4. **법인** 탭에서 다음 단계에 따라 내보낼 법인을 지정합니다.

    1. **새로 만들기** 를 선택합니다.
    2. **소스 법인** 필드에 법인을 입력합니다.

        동일한 데이터베이스의 여러 자회사에 동일한 기준이 적용되는 경우 해당 자회사의 데이터를 한 번의 작업으로 별도의 내보내기 파일로 전송할 수 있습니다.

        1. 계정을 파일로 내보내야 하는 자회사 법인별로 라인을 생성합니다. 이 파일은 나중에 통합 법인으로 가져옵니다.
        2. 자회사별로 자회사 이름과 내보내기 작업 중에 생성될 내보내기 파일의 이름을 입력합니다.

    3. **변환 차액의 계정 유형** 필드에 **손익** 또는 **대차 대조표** 를 선택합니다.
    4. 생성될 내보내기 파일의 파일 이름을 입력합니다.

5. **확인** 을 선택하여 내보내기를 실행합니다.

내보내기가 완료되면 각 파일에 저장된 레코드 수를 보여주는 메시지가 표시됩니다. 이제 이 파일을 통합 법인으로 가져올 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]