---
title: 자유 텍스트 송장 만들기
description: 이 토픽에서는 자유 텍스트 송장을 만드는 방법에 대해 설명합니다.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 6e9578d9b2d61f241ab5e92fc9740b88b80969f6
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2022
ms.locfileid: "8451744"
---
# <a name="create-a-free-text-invoice"></a>자유 텍스트 송장 만들기

[!include [banner](../includes/banner.md)]

이 토픽에서는 자유 텍스트 송장을 만드는 방법에 대해 설명합니다. 절차에서는 **USMF** 데모 회사를 사용합니다.

## <a name="create-a-free-text-invoice"></a>자유 텍스트 송장 만들기

1. **수취 계정(또는 판매 원장) \> 송장 \> 모든 자유 텍스트 송장** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **고객 계정** 필드에서 값을 선택합니다.

    * 기본적으로 고객 계정으로 선택된 계정은 송장 계정으로 사용됩니다.
    * 송장이 전기되지 않은 경우 회계 상태는 **진행 중** 으로 시작됩니다.
    * 송장 번호는 송장이 전기될 때 지정됩니다.
    * 단일 유로 결제 지역(SEPA) 위임장을 사용하는 경우 고객 계정을 선택하면 자동이체 위임장이 자동으로 입력됩니다.

4. **설명** 필드에 값을 입력합니다.
5. **주 계정** 필드에 차원이 없는 계정 번호를 지정합니다. 이 항목의 뒷부분에서 차원을 입력합니다.

    주 계정에 하나 이상의 문자를 입력하고 조회를 사용하여 계정을 찾을 수도 있습니다.

6. **라인 세부 정보** 빠른 탭을 선택하여 주 계정에 차원을 추가합니다.
7. **재무 차원 라인** 탭을 선택합니다.

    * 차원은 선택한 라인에만 해당됩니다.
    * 판매세 그룹은 고객이 입력합니다. 고객에게 판매세 그룹이 없는 경우 주 계정의 판매세 그룹이 사용됩니다.
    * 품목 판매세 그룹은 주 계정에서 작성됩니다. 주 계정에 품목 판매세 그룹이 없는 경우 총계정원장의 판매세 매개 변수에 지정된 품목 판매세 그룹이 사용됩니다.

8. 선택 사항: **수량** 필드에 숫자를 입력합니다.
9. 선택 사항: **단가 필드** 에 숫자를 입력합니다.

    금액은 수량 곱하기 단가로 계산됩니다. 그러나 해당 계산을 무시하고 금액을 입력할 수 있습니다.

10. 송장에 대해 계산된 판매세를 보려면 **판매세** 를 선택합니다.

    이 페이지에서 판매세 금액을 보거나 **조정** 탭에서 금액을 재정의할 수 있습니다.

11. **확인** 을 선택합니다.
12. **요금** 을 선택하여 송장에 요금을 추가합니다.
13. **요금 코드** 필드에 값을 입력합니다.
14. **요금 값** 필드에 숫자를 입력합니다.
15. 페이지를 닫습니다.
16. **합계** 를 선택하여 송장 세부 정보 및 합계의 요약을 확인합니다.
17. **닫기** 를 선택합니다.
18. **전기** 를 선택하여 송장을 전기합니다. 실제로 전기하기 전에 취소할 수 있는 기회가 있습니다.

    * 송장 인쇄 시기를 변경할 수 있습니다. **현재** 를 선택하여 각 송장을 업데이트할 때 인쇄합니다. 모든 송장이 업데이트된 후 인쇄하려면 **이후** 을 선택합니다.
    * 송장이 전기되기 전에 고객의 신용 한도가 확인되는 방법을 변경하려면 **신용 한도 유형** 필드의 값을 변경하십시오.
    * **수취 계정 매개 변수** 페이지(**수취 계정 > 설정 > 수취 계정 매개 변수**)의 **업데이트** 탭에서 오류 발생 시 자유 텍스트 송장 전기를 중지하도록 선택할 수 있습니다. 오류 발생 시 자유 텍스트 송장의 전기를 중지하려면 **첫 번째 오류 시 자유 텍스트 송장 전기 중지** 매개 변수에 대해 **예** 를 선택합니다. 배치로 전기하는 경우 오류로 인해 전기 프로세스가 중지되고 배치 상태가 **오류** 로 설정됩니다. 이 옵션을 선택하지 않으면 전기 프로세스에서 전기 오류가 있는 송장을 건너뛰고 계속해서 추가 송장을 전기합니다. 배치로 전기하는 경우 전기 오류로 인해 다른 송장이 전기되지 않습니다. 배치 상태는 **종료** 입니다. 자세한 전기 프로세스 보고서는 배치 작업 기록에서 검토할 수 있습니다.
    * 송장을 인쇄하려면 옵션을 **예** 로 설정합니다.
    * 송장을 인쇄하려면 옵션을 **예** 로 설정합니다. 송장을 전기하지 않고 인쇄할 수 있습니다.

19. **확인** 을 선택합니다.

## <a name="copy-lines"></a>라인 복사
자유 텍스트 송장의 라인을 복사하려면 하나 이상의 라인을 선택한 다음 **선택한 라인 복사** 를 선택합니다. 복사 매수를 지정할 수 있으며 메모 및 첨부 파일도 복사할 수 있습니다. 배포 사항을 복사하거나 전기할 때 다시 만들 수 있습니다.

라인을 복사한 후 필요에 따라 정보를 편집할 수 있습니다.

## <a name="create-a-free-text-invoice-from-a-template"></a>템플릿에서 자유 텍스트 송장 만들기
템플릿에서 자유 텍스트 송장을 만들 수 있습니다. **송장** 탭에서 **템플릿에서 새로 만들기** 를 선택하면 새 자유 텍스트 송장에 대한 템플릿 이름과 고객 계정을 선택할 수 있습니다. 지불 조건, 지불 방법 등의 기본값은 고객이 자동으로 입력하거나 템플릿에 저장된 값을 사용할 수 있습니다.

새 자유 텍스트 송장이 생성되고 필요에 따라 값을 편집할 수 있습니다.

## <a name="resetting-the-workflow-status-for-free-text-invoices-from-unrecoverable-to-draft"></a>자유 텍스트 송장의 워크플로 상태를 복구 불가능에서 초안으로 재설정
복구할 수 없는 오류로 인해 중지된 워크플로 인스턴스는 **복구 불가능** 상태가 됩니다. 고객 자유 텍스트 송장 워크플로의 상태가 **복구 불가능** 인 경우 워크플로 작업에서 **리콜** 을 선택하여 **초안** 으로 재설정할 수 있습니다. 그런 다음 고객 자유 텍스트 송장을 편집할 수 있습니다. 이 기능은 **기능 관리** 페이지의 **자유 텍스트 송장의 워크플로 상태를 복구 불가능에서 초안으로 재설정** 매개 변수가 켜져 있는 경우 사용할 수 있습니다.

**워크플로 기록** 페이지를 사용하여 워크플로 상태를 **초안** 으로 재설정할 수 있습니다. **자유 텍스트 송장** 또는 **공통 > 문의 > 워크플로** 에서 이 페이지를 열 수 있습니다. 워크플로 상태를 **초안** 으로 재설정하려면 **회수** 를 선택합니다. **자유 텍스트 송장** 페이지 또는 **모든 자유 텍스트 송장** 페이지에서 **리콜** 작업을 선택하여 워크플로 상태를 **초안** 으로 재설정할 수도 있습니다. 워크플로 상태가 **초안** 으로 재설정되면 **자유 텍스트 송장** 페이지에서 편집할 수 있습니다.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
