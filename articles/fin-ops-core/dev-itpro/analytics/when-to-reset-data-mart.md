---
title: 데이터 마트 재설정 FAQ
description: 이 항목에서는 데이터 마트 재설정에 관해 자주 묻는 질문에 대한 답변을 제공합니다.
author: jinniew
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 53f45f469c39f9e389763aa0daed658e5a62d377
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2022
ms.locfileid: "8461005"
---
# <a name="data-mart-resets-faq"></a>데이터 마트 재설정 FAQ

이 항목에서는 데이터 마트 재설정에 관해 자주 묻는 질문에 대한 답변을 제공합니다. 데이터 마트 재설정은 시간이 많이 소요되는 프로세스일 수 있으며 상황에 따라 필요한 솔루션이 아닐 수도 있습니다. 따라서 이 주제에는 데이터 마트 재설정이 도움이 될 수 있는 상황과 도움이 되지 않을 것 같은 상황에 대한 정보가 포함됩니다.

## <a name="what-is-a-data-mart-reset"></a>데이터 마트 재설정이란 무엇입니까?

데이터 마트 재설정은 통합 작업을 비활성화하고 모든 데이터 마트 데이터를 삭제한 다음 통합을 다시 활성화합니다.

오래된 데이터가 삽입되지 않도록 하려면 기존 작업이 완료된 후에만 데이터 마트 재설정을 시작할 수 있습니다. 모든 작업이 완료되기 전에 데이터 마트를 재설정하려고 하면 "활성 작업으로 인해 데이터 마트 재설정을 처리할 수 없습니다. 나중에 다시 시도하세요."

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>데이터 마트 재설정은 언제 해야 합니까?

다음 진술 중 하나 이상이 귀하의 상황에 적용되는 경우 귀하의 조직은 데이터 마트 재설정의 이점을 누릴 수 있습니다.

- **애플리케이션 데이터베이스가 복원되었습니다**
- **지원 티켓을 열었습니다** - 지원 엔지니어가 문제 해결 단계의 일부로 데이터 마트를 재설정하도록 지시했습니다.
- **오래된 기록의 큰 비율** - 오래된 레코드 자체가 데이터 마트 재설정을 반드시 정당화하지는 않습니다. 오래된 데이터의 비율이 높으면 전체 보고서 생성 및 통합 성능이 저하되고 추가 데이터베이스 공간 사용량이 발생할 수 있습니다. 데이터 마트에 80% 이상의 오래된 데이터가 있는 경우 데이터 마트 재설정을 완료하여 오래된 데이터를 제거하는 것이 좋습니다.
 
> [!NOTE]
> 데이터 마트 재설정 프로세스는 데이터베이스의 총계정원장 및 예산 거래 수의 영향을 받습니다. 시스템의 트랜잭션 수에 따라 데이터 마트 재설정은 15분 이내에 완료되거나 최대 4시간이 소요될 수 있습니다. 그러나 재설정하는 데 4시간 이상 걸리면 지원팀에 문의하는 것이 좋습니다.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>데이터 마트 재설정이 부적절한 경우는 언제입니까?

다음은 데이터 마트를 재설정하지 않는 것이 좋습니다.

- 데이터 통합 성능 문제가 발생했습니다.
- 다음과 같은 이유로 반복적인 재설정 패턴이 있습니다.

    - **보고서에 누락되거나 예상치 못한 데이터가 있음** – 데이터가 누락된 경우 Microsoft에 지원 티켓을 열어 보고서 형식 및 가능한 데이터 동기화 문제를 검토하세요.
    - **멈춘 통합 상태**
   
## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>데이터 마트를 재설정하면 이미 디자인한 보고서가 손실됩니까?

아니요. 보고서는 데이터 마트 재설정의 영향을 받지 않는 SQL 테이블에 저장됩니다. 디자인한 보고서가 손실될까 염려되는 경우 손실하고 싶지 않은 디자인을 백업할 수 있습니다. 디자인을 백업하려면 Report Designer를 열고 **회사 \> 회사 \> 빌딩 블록 \> 내보내기** 로 이동합니다.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>데이터 마트를 재설정하려면 모든 사용자가 시스템을 종료해야 합니까?

아니요. 사용자는 데이터 마트 재설정 중에 시스템에서 계속 작업할 수 있습니다. 그러나 재설정이 완료될 때까지 사용자는 Financial Reporter를 사용하여 만든 보고서에 액세스할 수 없습니다.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
