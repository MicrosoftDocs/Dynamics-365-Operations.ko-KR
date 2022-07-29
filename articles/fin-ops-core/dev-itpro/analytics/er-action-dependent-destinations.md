---
title: 작업 종속 ER 대상 구성
description: 이번에는 아웃바운드 문서를 생성하도록 구성된 전자 보고(ER) 형식에 대한 작업 종속 대상을 구성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e0c836d4a0be47b753d74dc9d6d40ea7d9197176
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8461013"
---
# <a name="configure-action-dependent-er-destinations"></a>작업 종속 ER 대상 구성

[!include [banner](../includes/banner.md)]

아웃바운드 문서를 생성하는 데 사용되는 [전자 보고(ER)](general-electronic-reporting.md) 형식 [구성](general-electronic-reporting.md#Configuration)의 각 출력 구성 요소(폴더 또는 파일)에 대한 [대상](electronic-reporting-destinations.md)을 구성할 수 있습니다. 이 유형의 ER 형식을 실행하고 적절한 액세스 권한이 있는 사용자는 런타임 시 구성된 대상 설정을 변경할 수도 있습니다.

Microsoft Dynamics 365 Finance **버전 10.0.17 이상** 에서는 사용자가 해당 ER 형식을 실행하여 수행하는 작업 코드를 [프로비저닝하여](er-apis-app10-0-17.md) ER 형식을 실행할 수 있습니다. 예를 들어 **미수금** 모듈의 인쇄 관리 설정에서 무료 텍스트 송장과 같은 특정 비즈니스 문서를 생성하는 ER 형식을 선택할 수 있습니다. 이후 **보기** 를 선택하여 송장을 미리 보거나 **인쇄** 를 선택하여 프린터로 보낼 수 있습니다. 런타임 시 실행 중인 ER 형식에 대해 사용자 작업이 전달되면 다른 사용자 작업에 대해 다른 ER 대상을 구성할 수 있습니다. 이번에는 이러한 유형의 ER 형식에 대해 ER 대상을 구성하는 방법에 대해 설명합니다.

## <a name="make-action-dependent-er-destinations-available"></a>작업 종속 ER 대상을 사용 가능하게 만드십시오.

현재 Finance 인스턴스에서 작업 종속 ER 대상을 구성하고 [새](er-apis-app10-0-17.md) ER API를 활성화하려면 [기능 관리](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) 작업 공간을 열고 **다른 PM 작업에 사용할 특정 ER 대상 구성** 기능을 켭니다. 런타임 시 [특정](#reports-list-wave1) 보고서에 대해 구성된 ER 대상을 사용하려면 **사용자 작업 특정(웨이브 1)인 ER 대상을 기반으로 PM 보고서의 출력 라우팅** 기능을 활성화하십시오.

## <a name="configure-action-dependent-er-destinations"></a>작업 종속 ER 대상 구성

**다른 PM 작업에 사용할 특정 ER 대상 구성** 기능을 켜면 **전자 보고 대상** 페이지의 **파일 대상** FastTab에서 작업 종속 ER 대상을 구성할 수 있습니다. 각 구성 요소에 대해 기록을 추가하고 특정 ER 대상을 활성화할 수 있습니다. 각 기록에 대해 구성된 ER 대상을 적용해야 하는 문서 유형을 지정해야 합니다. **문서 유형** 필드에서 다음 값 중 하나를 선택합니다.

- 런타임 시 사용자 작업 코드가 제공되지 않은 경우 **전자** 를 선택하여 구성된 대상을 적용합니다.
- 런타임 시 사용자 작업 코드가 제공되는 경우 구성된 대상을 적용하려면 **인쇄 관리** 를 선택합니다.
- 런타임 시 사용자 작업이 제공되는지 여부에 관계없이 구성된 대상을 항상 적용하려면 **모두** 를 선택합니다.

**인쇄 관리** 문서 유형을 선택한 경우 구성된 ER 대상이 적용되어야 하는 사용자 작업을 지정해야 합니다. **인쇄 관리 작업** 필드에서 다음 값 중 하나를 선택합니다.

- 사용자 **보기** 작업이 런타임에 제공되는 경우 **보기** 를 선택하여 구성된 대상을 적용합니다.
- 사용자 **인쇄** 작업이 런타임에 제공되는 경우 **인쇄** 를 선택하여 구성된 대상을 적용합니다.
- 런타임 시 사용자 **보내기** 작업이 제공되는 경우 **보내기** 를 선택하여 구성된 대상을 적용합니다.

> [!NOTE]
> 단일 대상 기록에 대해 여러 작업을 선택할 수 있습니다.

**모든** 문서 유형을 선택하면 **인쇄 관리 작업** 필드에서 **자동 감지** 가 사용자 작업으로 자동 선택되고 다음 동작이 발생합니다.

- 런타임 시 사용자 작업 코드가 제공되지 않으면 구성된 모든 ER 대상이 적용됩니다.
- 런타임 시 사용자 작업 코드가 제공되면 **활성화 여부에 관계없이** 특정 작업에 대해 미리 정의된 ER 대상이 적용됩니다.

    - 런타임 시 **View** 액션이 제공되면 **Screen** ER 대상이 적용됩니다.
    - 런타임에 **보내기** 작업이 제공되면 **이메일** ER 대상이 적용됩니다.
    - 런타임에 **인쇄** 작업이 제공되면 **프린터** ER 대상이 적용됩니다.

예를 들어, **무료 텍스트 송장(Excel)** ER 형식을 사용하여 전기할 때 [무료 텍스트 송장](../../../finance/accounts-receivable/create-free-text-invoice-new.md)을 인쇄할 수 있습니다. 생성된 문서를 라우팅하려면 이 ER 형식에 대해 ER 대상을 구성해야 합니다. 예를 들어, 생성된 문서에서 다음을 수행하려면 이러한 ER 대상을 구성해야 할 수 있습니다.

- ER 형식이 실행되었지만 작업 코드가 제공되지 않은 경우(예: 문서가 전자적으로 전송된 경우) 문서를 보관합니다.
- 사용자가 **보기** 작업을 수행할 때 웹 브라우저에서 문서를 미리 봅니다.
- 사용자가 **인쇄** 작업을 수행할 때 문서를 보관 및 인쇄합니다.
- 문서를 보관하고 사용자가 **보내기** 작업을 수행할 때 아웃바운드 전자 메일 메시지의 첨부 파일로 전자 메일로 보냅니다.

다음 그림은 모든 기록이 개별 사용자 작업에 대해 구성될 때 이러한 구성 ER 대상을 개별 대상 기록 세트로 달성할 수 있는 방법을 보여줍니다.

![모든 대상 기록이 단일 사용자 작업에 대해 구성된 경우 ER 형식에 대한 작업 종속 대상 설정이 있는 전자 보고 대상 페이지입니다.](./media/er-destination-action-dependent-01.png)

다음 그림은 모든 기록이 개별 대상에 대해 구성된 경우 개별 대상 기록 세트와 동일한 대안으로 ER 대상을 구성하는 방법을 보여줍니다.

![모든 대상 기록이 단일 대상에 대해 구성된 경우 ER 형식에 대한 작업 종속 대상 설정이 있는 전자 보고 대상 페이지.](./media/er-destination-action-dependent-01a.png)

> [!NOTE]
> 실행 중인 ER 형식에 대해 작업 코드가 제공되었지만 해당 작업 코드에 대해 대상이 구성되지 않은 경우 [기본](electronic-reporting-destinations.md#default-behavior) 대상 동작이 적용됩니다.

## <a name="change-action-dependent-er-destinations-at-runtime"></a>런타임 시 작업 종속 ER 대상 변경

ER 형식이 실행될 때 런타임에 구성된 대상 설정을 변경할 수 있는 적절한 [권한](electronic-reporting-destinations.md#security-considerations)이 있는 사용자가 사용자 작업을 프로비저닝한 경우 구성된 대상 설정을 변경할 수 있는 옵션을 제공하는 대화 상자가 나타납니다. 이 대화 상자는 선택 사항이며, ER 프레임워크가 ER 형식을 실행하기 위해 호출하는 방식에 따라 모양이 달라집니다. 이 대화 상자가 나타나면 제공된 사용자 작업에 따라 대화 상자의 ER 대상이 활성화됩니다.

다음 그림은 **프린터** 작업이 프로비저닝되고 ER 대상이 지정된 경우 자유 텍스트 송장이 [전기](../../../finance/accounts-receivable/create-free-text-invoice-new.md)되고 **자유 텍스트 송장(Excel)** ER 형식이 실행되어 이 문서를 생성할 때 표시되는 **전자 보고 형식 대상** 대화 상자의 예를 보여줍니다. 이 항목의 앞부분에 표시된 대로 이 형식에 대해 구성됩니다.

![실행 중인 ER 형식에 대해 초기에 구성된 ER 대상을 변경하는 옵션을 제공하는 대화 상자입니다.](./media/er-destination-action-dependent-02.gif)

> [!NOTE]
> 실행 중인 ER 형식의 여러 구성 요소에 대해 ER 대상을 구성한 경우 ER 형식의 구성된 모든 구성 요소에 대해 옵션이 별도로 제공됩니다.

## <a name="verify-the-provided-user-action"></a>제공된 사용자 작업 확인

특정 사용자 작업을 수행할 때 실행 중인 ER 형식에 대해 제공되는 사용자 작업(있는 경우)을 확인할 수 있습니다. 이 확인은 작업 종속 ER 대상을 구성해야 하지만 제공되는 사용자 작업 코드(있는 경우)가 확실하지 않은 경우에 중요합니다. 예를 들어 **무료 텍스트 송장 전** 기를 시작하고 **무료 텍스트 송장 게시** 대화 상자에서 **송장 인쇄 옵션** 을 **예** 로 설정하면 인쇄 관리 대상 사용 옵션을 **예** 또는 **아니요** 로 설정할 수 있습니다.

다음 단계에 따라 제공된 사용자 작업 코드를 확인하십시오.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **사용자 매개 변수** 대화 상자에서 **디버그 모드** 에서 실행 옵션을 **예** 로 [설정](er-trace-reports-compare-baseline.md#configure-er-parameters-to-use-the-baseline-feature)합니다.
4. ER 형식을 실행하여 사용자 작업을 수행합니다. ER 사용자 매개 변수는 회사와 사용자에 따라 다릅니다.
5. **조직 관리** \> **전자 보고** \> **구성 디버그 로그** 로 이동합니다.
6. **구성 디버그 로그** 페이지에서 ER 실행 로그를 필터링하여 ER 형식 실행에 대한 로그를 찾습니다.
7. ER 형식 실행에 대해 조치가 제공된 경우 제공된 사용자 조치 코드를 나타내는 기록을 포함해야 하는 로그 항목을 검토하십시오.

    ![ER 형식의 필터링된 실행에 대해 제공된 사용자 작업 코드에 대한 정보가 포함된 전자 보고 실행 로그 페이지입니다.](./media/er-destination-action-dependent-03.png)

## <a name=""></a><a name="reports-list-wave1">비즈니스 문서 목록(웨이브 1)</a>

다음 비즈니스 문서 목록은 **사용자 작업에 따라 달라지는 ER 대상을 기반으로 하는 PM 보고서의 출력 경로 지정** 기능으로 제어됩니다(웨이브 1).

- 고객 송장(무료 텍스트 송장)
- 고객 송장(판매 송장)
- 구매 주문
- 구매 주문 구매 문의
- 판매 주문 확인
- 컬렉션 편지 메모
- 이자 메모
- 공급 업체 지급 조언
- 견적 요청

## <a name="additional-resources"></a>추가 리소스

[전자 보고(ER) 개요](general-electronic-reporting.md)

[전자 보고(ER) 대상](electronic-reporting-destinations.md)

[애플리케이션 업데이트 10.0.17에 대한 전자 보고 프레임워크 API 변경](er-apis-app10-0-17.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
