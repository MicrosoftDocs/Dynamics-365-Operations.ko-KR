---
title: 작업 주문 수명 주기 상태
description: 이 항목에서는 자산 관리의 작업 주문 수명 주기 상태에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderLifecycleState, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fa0980438ec629ef7ae6bf711d5ae87efca131e6ab86dfcaa1f17d953725147a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447205"
---
# <a name="work-order-lifecycle-states"></a>작업 주문 수명 주기 상태


[!include [banner](../../includes/banner.md)]

 

작업 주문 수명 주기 상태는 작업 주문이 통과할 수 있는 상태를 정의합니다. 예에는 **생성됨**, **예약됨**, **진행 중** 및 **종료됨** 이 포함됩니다. 작업 주문 수명 주기 상태는 작업 주문에서 수동으로 업데이트하거나 자동으로 업데이트할 수 있습니다(예: 작업 주문 예약 중).

작업 주문에 필요한 작업 주문 수명 주기 상태는 **프로젝트 관리 및 회계 매개 변수** 페이지(**프로젝트 관리 및 회계** \> **프로젝트 관리 및 회계 매개 변수**)에서 일치하는 프로젝트 단계에 첨부되어야 합니다. 먼저 프로젝트 관리 및 회계에서 프로젝트 단계를 설정합니다. 그런 다음 자산 관리에서 작업 주문 수명 주기 상태 및 작업 주문 수명 주기 모델을 설정합니다.

다음 표에서는 **작업 주문 수명 주기 상태** 페이지(**자산 관리** \> **설정** \> **작업 주문** \> **수명 주기 상태**)의 **일반** 빠른 탭에 있는 **작업 주문** 및 **일정** 섹션의 옵션에 대해 설명합니다.

![작업 주문 수명 주기 상태 페이지.](media/09-setup-for-work-orders.png)

| 옵션 이름                   | 설명 |
|-------------------------------|-------------|
| 활성                        | 이 수명 주기 상태에 있는 동안 작업 주문을 활성화해야 하는 경우 이 옵션을 **예** 로 설정합니다. |
| 라인 추가                      | 이 수명 주기 상태에 있는 작업 주문에 작업 주문 작업을 추가할 수 있는 경우 이 옵션을 **예** 로 설정합니다. |
| 삭제                        | 이 수명 주기 상태에 있는 동안 작업 주문을 삭제할 수 있는 경우 이 옵션을 **예** 로 설정합니다. |
| 라인 삭제                   | 이 수명 주기 상태에 있는 작업 주문에 작업 주문 작업을 삭제할 수 있는 경우 이 옵션을 **예** 로 설정합니다. |
| 일정 예약 허용              | 이 수명 주기 상태에 있는 동안 작업 주문을 예약할 수 있는 경우 이 옵션을 **예** 로 설정합니다. |
| 실제 시작 설정              | 이 수명 주기 상태로 업데이트될 때 작업 주문의 실제 시작 날짜 및 시간을 선택하라는 메시지가 사용자에게 표시되어야 하는 경우 이 옵션을 **예** 로 설정합니다. |
| 실제 종료 설정                | 이 수명 주기 상태로 업데이트될 때 작업 주문의 실제 종료 날짜 및 시간을 선택하라는 메시지가 사용자에게 표시되어야 하는 경우 이 옵션을 **예** 로 설정합니다. |
| 분개장 기장                 | 작업 주문이 이 수명 주기 상태로 업데이트될 때 작업 주문 분개장이 자동으로 전기되어야 하는 경우 이 옵션을 **예** 로 설정합니다. 분개장 게시 중 오류가 발생하면 메시지가 표시되고 작업 주문 수명 주기 상태의 업데이트가 취소됩니다. 작업 주문에 대한 분개장 라인을 보려면 **자산 관리** \> **공통** \> **작업 주문** \> **모든 작업 주문**, **활성 작업 주문** 또는 **내 활성 작업 주문** 을 선택하고 목록에서 작업 주문을 선택한 다음 **분개장** 을 선택합니다. 특정 수명 주기 상태에서 자동 작업 주문 분개장 게시 설정은 **작업 주문 분개장** 페이지에서 **분개장 게시** 를 선택할 때와 동일합니다.<p>**참고:** 이 옵션을 **예** 로 설정하면 승인 워크플로가 설정되지 않은 경우 분개장이 자동으로 전기됩니다. 회사에서 **분개장 승인** 페이지(**프로젝트 관리 및 회계** \> **설정** \> **분개장** \> **분개장 승인**)에 구성된 분개장 승인 설정을 사용하는 경우 관리자 또는 사무원이 소비 등록을 확인하고 게시해야 합니다.</p> |
| 프로세스 유지 관리 체크리스트 | 작업 주문이 이 수명 주기 상태로 업데이트될 때 첨부된 모든 유지 관리 체크리스트를 처리해야 하는 경우 이 옵션을 **예** 로 설정합니다. 이 처리의 일부로 유지 관리 체크리스트에 작성된 카운터 등록이 게시되고 전체 유지 관리 체크리스트의 결과가 평가됩니다. **통과** 및 **실패** 결과가 있는 유지보수 체크리스트 라인이 평가되며, 하나 이상의 라인이 실패하면 전체 유지보수 체크리스트가 자산 관리에서 **실패함** 으로 표시됩니다. |
| 준비                         | 작업 주문이 이 수명 주기 상태로 업데이트될 때 작업 주문에서 생성된 모든 작업 주문 작업에 대한 작업 주문 작업 일정 상태가 자동으로 **준비됨** 으로 업데이트되어야 하는 경우 이 옵션을 **예** 로 설정합니다. |
| 시작                         | 작업 주문이 이 수명 주기 상태로 업데이트될 때 작업 주문에서 생성된 모든 작업 주문 작업에 대한 작업 주문 작업 일정 상태가 자동으로 **시작됨** 으로 업데이트되어야 하는 경우 이 옵션을 **예** 로 설정합니다. |
| 종료                           | 작업 주문이 이 수명 주기 상태로 업데이트될 때 작업 주문에서 생성된 모든 작업 주문 작업에 대한 작업 주문 작업 일정 상태가 자동으로 **종료됨** 으로 업데이트되어야 하는 경우 이 옵션을 **예** 로 설정합니다. |
| 일정 라인 삭제         | 작업 주문이 이 수명 주기 상태로 업데이트될 때 이미 예약된 작업 주문에서 생성된 모든 작업 주문 작업에 대한 예약을 삭제해야 하는 경우 이 옵션을 **예** 로 설정합니다. 다시 말해 자산, 관련 유지 관리 작업자 및 관련 도구에 대한 용량 예약이 삭제됩니다. 예를 들어 **예상됨** 이라는 작업 주문 수명 주기 상태에서 이 옵션을 **예** 로 설정합니다. 그런 다음 일정 조정이 필요하여 작업 주문이 이 수명 주기 상태로 롤백되면 해당 작업 주문에서 일정이 삭제될 수 있습니다. |

## <a name="set-up-project-stages-and-work-order-lifecycle-states"></a>프로젝트 단계 및 작업 주문 수명 주기 상태 설정

1. **프로젝트 관리 및 회계** \> **설정** \> **프로젝트 관리 및 회계 매개 변수** 를 선택합니다.
2. **프로젝트 단계** 탭에서 사용하려는 각 단계에 대해 작업 주문에 필요한 모든 프로젝트 유형에 대한 확인란을 선택합니다. 프로젝트 유형은 허용되는 재무 작업에 대한 규칙을 정의합니다. 재무 작업의 예에는 예측 생성, 추정 생성 및 기초 잔액 생성이 포함됩니다.

    > [!IMPORTANT]
    > 프로젝트 유형에 대해 프로젝트 단계가 선택되지 않았지만 프로젝트 단계가 작업 주문 수명 주기 상태에 사용되는 경우 작업 주문 프로젝트가 적절한 방식으로 업데이트되지 않습니다.

3. **프로젝트 관리 및 회계 매개 변수** 페이지를 닫습니다.
4. **자산 관리** \> **설정** \> **작업 주문** \> **수명 주기 상태** 를 선택합니다.
5. **새로 만들기** 를 선택하여 작업 주문 수명 주기 상태를 만듭니다.
6. **수명 주기 상태** 필드에 수명 주기 상태의 ID를 입력합니다.
7. **이름** 필드에 이름을 입력합니다.

    **세부 정보** 빠른 탭에서 **수명 주기 모델** 필드는 이 수명 주기 상태를 사용하는 작업 주문 수명 주기 모델의 수를 표시합니다.

8. **일반** 빠른 탭의 **작업 주문** 섹션에서 관련 옵션을 **예** 로 설정하여 이 수명 주기 상태에 사용할 수 있는 기능을 선택합니다. 옵션에 대한 설명은 이 토픽 앞부분의 표를 참조하세요.
9. **프로젝트** 섹션의 **단계** 필드에서 이 수명 주기 상태와 관련되어야 하는 프로젝트 단계를 선택합니다.
10. **프로젝트** 섹션에서 각 작업 주문 작업과 관련된 프로젝트 활동이 작업 주문이 이 수명 주기 상태일 때 자동으로 마감되어야 하는 경우 **활동 닫기** 옵션을 **예** 로 설정합니다.

    > [!NOTE]
    > 작업 주문 작업과 관련된 프로젝트 활동의 수를 찾으려면 **자산 관리** \> **공통** \> **작업 주문** \> **모든 작업 주문**, **활성 작업 주문** 또는 **내 활성 작업 주문** 을 선택합니다. 작업 주문을 연 다음 작업 주문 작업을 선택합니다. 활동 번호는 **라인 세부 정보** 빠른 탭의 **일반** 탭에 있는 **프로젝트** 섹션의 **활동 번호** 필드에 표시됩니다.

11. 작업 주문이 이 수명 주기 상태일 때 작업 주문 프로젝트 예측이 작업 주문 저널에 자동으로 복사되어야 하는 경우 **예측** 섹션에서 **시간 예측 복사**, **품목 예측 복사** 및/또는 **비용 예측 복사** 옵션을 **예** 로 설정합니다.
12. **일정** 섹션에서 작업 주문이 이 수명 주기 상태일 때 작업 주문 작업의 일정 상태를 업데이트해야 하는 경우 옵션 중 하나를 **예** 로 설정합니다. **준비**, **시작**, **종료** 및 **일정 라인 삭제** 옵션에 대한 설명은 이 토픽 앞부분의 표를 참조하세요.

    > [!NOTE]
    > 작업 주문 작업과 관련된 일정 라인을 보려면 **자산 관리** \> **공통** \> **작업 주문** \> **모든 작업 주문**, **활성 작업 주문** 또는 **내 활성 작업 주문** 을 선택합니다. 작업 주문을 열고 **작업 주문 작업** 빠른 탭에서 작업 주문 작업을 선택하고 **라인 세부 정보** 빠른 탭에서 관련 정보를 봅니다. **일정** 탭의 **상태** 필드에는 작업 주문 작업의 상태가 표시됩니다. **상태** 필드는 **예약됨**, **준비됨**, **시작됨**, **중지됨** 및 **종료됨** 값으로 설정할 수 있습니다.

13. **유지 관리 요청** 섹션의 **수명 주기 상태** 필드에서 관련 유지 관리 요청을 업데이트해야 하는 유지 관리 요청 수명 주기 상태를 선택합니다. 이 업데이트는 자동으로 발생합니다. 유지보수 요청에 사용되는 유지보수 요청 라이프사이클 모델에서 유지보수 요청 라이프사이클 상태를 선택한 경우에만 수행할 수 있습니다.
14. 작업 주문이 이 수명 주기 상태로 업데이트될 때 작업 주문에 사용되는 모든 항목이 **자산 BOM** 페이지에서 자동으로 업데이트되어야 하는 경우 **자산** 섹션에서 **자산 BOM 업데이트** 옵션을 **예** 로 설정합니다. 이 설정은 예를 들어 작업 주문 수명 주기 상태가 작업 주문을 완료됨 또는 종료됨으로 정의하는 경우 관련될 수 있습니다.
15. 이 수명 주기 상태에 있는 작업 주문이 작업 주문 풀에서 자동으로 삭제되어야 하는 경우 **작업 주문 풀** 섹션에서 **풀 참조 삭제** 옵션을 **예** 로 설정합니다.
16. **유효성 검사** 빠른 탭에서 관련 옵션을 **예** 로 설정하여 이 수명 주기 상태에서 활성화해야 하는 유효성 검사 유형을 선택합니다. 그런 다음 선택한 각 유효성 검사 유형의 **유형** 필드에서 유효성 검사 유형과 관련된 필수 필드의 유효성이 검사되지 않은 경우 표시되어야 하는 메시지 유형을 선택합니다. **오류** 를 선택하면 관련 필수 필드가 작업 주문에서 업데이트될 때까지 작업 주문 수명 주기 상태 업데이트가 취소됩니다.

    - **유지 관리 가동 중지 시간**, **유지 관리 체크리스트**, **결함 증상**, **결함 원인** 및 **결함 해결** 옵션은 **작업 주문 유형** 페이지(**자산 관리** \> **설정** \> **작업 주문** \> **작업 주문 유형**)의 **필수** 섹션에 있는 옵션과 관련이 있습니다. 이러한 유효성 검사를 활성화하려면 작업 주문에 사용되는 작업 주문 유형에서 관련 옵션도 **예** 로 설정해야 합니다.
    - 작업 주문이 업데이트되는 수명 주기 상태에 대해 **유지 관리 체크리스트** 옵션이 **예** 로 설정된 경우 **필수** 로 표시된 유지 관리 체크리스트 행이 **선택됨** 또는 **적용 불가** 로 등록되었는지 확인하기 위한 유효성 검사가 수행됩니다. 필수 라인에 이러한 등록이 모두 수행되지 않은 경우 작업 주문이 이 수명 주기 상태로 업데이트될 때 정보, 오류 또는 경고 메시지가 표시됩니다.
    - 작업 주문이 업데이트된 수명 주기 상태에 대해 **확정된 비용** 옵션이 **예** 로 설정된 경우 각 작업 주문 작업에 대해 확정된 비용 총액(즉, 법인이 지불하기로 약정한 비용 총액)이 계산됩니다. 확정된 비용 금액이 0(영)보다 크면 메시지가 표시됩니다. **프로젝트 관리 및 회계 매개 변수** 페이지(**프로젝트 관리 및 회계** \> **설정** \> **프로젝트 관리 및 회계 매개 변수**)의 **비용 관리** 탭에서 **비용 약정** 빠른 탭에 포함된 비용 약정 유형을 선택합니다.
    - 작업 주문이 업데이트되는 수명 주기 상태에 대해 **유지 관리 가동 중지 시간** 옵션이 **예** 로 설정된 경우 작업 주문과 관련된 자산에 대해 유지 관리 가동 중지 시간 유효성 검사가 수행됩니다. 유지 관리 가동 중지 시간 등록이 이루어졌지만 **종료됨** 등록이 없는 경우 작업 주문이 이 수명 주기 상태로 업데이트될 때 메시지가 표시됩니다.
    - 표준 프로젝트 설정에 자산 관리 설정에 필요한 모든 단계가 포함되어 있지 않은 경우 **프로젝트 관리 및 회계 매개 변수** 페이지의 **프로젝트 단계** 탭에서 사용자 정의 프로젝트 단계를 설정할 수 있습니다. 다음 그림은 **프로젝트 관리 및 회계 매개 변수** 페이지의 **프로젝트 단계** 탭을 보여줍니다.

    ![다양한 프로젝트 유형 페이지에 대한 프로젝트 단계 설정.](media/10-setup-for-work-orders.png)

> [!NOTE]
> 작업 주문을 업데이트하는 수명 주기 상태가 비활성화된 경우 작업 주문과 관련되어 있지만 아직 게시되지 않은 분개장은 자동으로 삭제됩니다. 이 동작은 사용하지 않는 데이터의 자동 정리를 보장하는 데 도움이 됩니다. (**작업 주문 수명 주기 상태** 페이지의 **일반** 빠른 탭에서 **활성** 옵션이 **아니요** 로 설정된 경우 수명 주기 상태는 비활성 상태입니다.)
>
> 그러나 수동으로 작업 주문을 비활성화하여 작업 주문을 설정한 경우 작업 주문과 관련되어 있지만 아직 게시되지 않은 분개장은 자동으로 삭제되지 **않습니다**. (작업 주문을 수동으로 비활성화하려면 **자산 관리** \> **공통** \> **작업 주문** \> **모든 작업 주문** 또는 **활성 작업 주문** 을 선택합니다. 작업 주문을 열고 **헤더** 보기로 전환합니다. **일반** 빠른 탭에서 **편집** 을 선택한 다음 **활성** 옵션을 **아니요** 로 설정합니다.)

## <a name="relations-among-work-order-lifecycle-models-work-order-types-and-work-order-lifecycle-states"></a>작업 주문 수명 주기 모델, 작업 주문 유형 및 작업 주문 수명 주기 상태 간의 관계

수명 주기 모델은 워크플로우를 말하며, 수명 주기 상태는 수명 주기 모델에서 순차적으로 선택됩니다. 수명 주기 모델은 작업 주문 유형에 설정됩니다. 작업 주문 유형은 워크플로 및 작업 프로세스의 크기 또는 범위를 결정합니다. 예를 들어 표준 작업 주문 유형인 **유지 관리** 는 수명 주기 상태가 많은 작업 주문 수명 주기 모델과 관련될 수 있습니다. 반대로, 예약되지 않은 작업 주문이나 긴급 상황으로 인해 작업 주문이 완료되기 전에 작업이 완료된 작업 주문에 사용되는 **수정** 작업 주문 유형이 있을 수 있습니다. 이 작업 주문 유형은 몇 가지 수명 주기 상태만 있는 작업 주문 수명 주기 모델과 관련될 수 있습니다.

유형을 사용하는 이유는 예를 들어 작업 주문이나 자산에 유형을 정의할 때 관련 작업 프로세스(수명 주기 상태)가 자동으로 정의되기 때문이다. 작업 주문 유형을 설정하는 방법에 대한 자세한 내용은 [작업 주문 유형](../setup-for-work-orders/work-order-types.md)을 참조하세요.

> [!NOTE]
> 수명 주기 상태, 수명 주기 모델 및 유형은 작업 주문 외에도 기능 위치, 자산 및 유지 관리 요청에 적용됩니다.

다음 그림은 작업 주문 유형, 수명 주기 모델 및 수명 주기 상태 간의 관계를 보여줍니다.

![작업 주문 수명 모델 페이지와 비교한 작업 주문 유형 페이지.](media/11-setup-for-work-orders.png)

## <a name="work-order-lifecycle-models"></a>작업 주문 수명 주기 모델

작업 주문에 필요한 작업 주문 수명 주기 상태를 만든 후에는 작업 주문 수명 주기 모델로 나눌 수 있습니다. 최소한 하나의 표준 수명 주기 모델을 만들어야 합니다.

1. **자산 관리** \> **설정** \> **작업 주문** \> **수명 주기 모델** 을 선택합니다.
2. **새로 만들기** 를 선택하여 작업 주문 수명 주기 모델을 만듭니다.
3. **수명 주기 모델** 필드에 수명 주기 모델의 ID를 입력합니다.
4. **이름** 필드에 이름을 입력합니다.

    **세부 정보** 빠른 탭에서 **수명 주기 상태** 필드는 이 수명 주기 모델에서 선택된 수명 주기 상태의 수를 표시합니다. **작업 주문 유형** 필드에는 이 수명 주기 모델을 사용하는 작업 주문 유형의 수가 표시됩니다.

5. **수명 주기 상태** 빠른 탭에서 수명 주기 모델에 포함되어야 하는 수명 주기 상태를 선택합니다.

    - 수명 주기 모델에 수명 주기 상태를 포함하려면 **남은 수명 주기 상태** 섹션에서 선택한 다음 오른쪽 화살표 단추 ![오른쪽 화살표](media/12-setup-for-work-orders.png)를 선택합니다. **수명 주기 상태 선택** 섹션으로 이동합니다.
    - 사용 가능한 모든 수명 주기 상태를 수명 주기 모델에 포함하려면 **사용 가능한 모든 단계 선택** 단추를 선택합니다. ![사용 가능한 모든 단계 선택.](media/13-setup-for-work-orders.png) 모든 수명 주기 상태가 **선택한 수명 주기 상태** 섹션으로 이동됩니다.
    - 수명 주기 모델에서 수명 주기 상태를 제거하려면 **선택한 수명 주기 상태** 섹션에서 선택한 다음 왼쪽 화살표 단추를 선택합니다. ![왼쪽 화살표.](media/14-setup-for-work-orders.png) **남은 수명 주기 상태** 섹션으로 이동합니다.

6. **수명 주기 상태 업데이트** 를 선택하여 선택한 수명 주기 상태를 따를 수 있는 수명 주기 상태를 정의합니다.
7. **업데이트** 빠른 탭의 **예약된 상태** 필드에서 작업 주문의 이전 수명 주기 상태에 관계없이 작업 주문 예약을 완료한 작업 주문에 대해 항상 선택해야 하는 수명 주기 상태를 선택합니다.
8. **예약되지 않은 수명 주기 상태** 필드에서 작업 주문 일정이 삭제된 경우 작업 주문에 대해 항상 선택해야 하는 수명 주기 상태를 선택합니다.
9. 작업 주문 수명 주기 모델을 저장합니다.

![작업 주문 수명 주기 모델 페이지.](media/15-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]