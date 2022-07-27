---
title: 조달 및 소싱 워크플로
description: 일부 조직에서는 거래를 입력한 사람이 아닌 다른 사용자가 구매 요청 및 구매 주문을 승인하도록 요구합니다. 승인 프로세스를 설정하기 위해 워크플로를 만들 수 있습니다.
author: Henrikan
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a819093d9ee6f999e637281e54905968fe361566
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448828"
---
# <a name="procurement-and-sourcing-workflows"></a>조달 및 소싱 워크플로

[!include [banner](../includes/banner.md)]

일부 조직에서는 거래를 입력한 사람이 아닌 다른 사용자가 구매 요청 및 구매 주문을 승인하도록 요구합니다. 승인 프로세스를 설정하기 위해 워크플로를 만들 수 있습니다.

워크플로는 비즈니스 프로세스를 나타냅니다. 문서가 시스템을 통해 흐르는 방식을 정의하고 누가 작업을 완료하거나 문서를 승인해야 하는지 나타냅니다. 조직에서 워크플로 시스템을 사용하면 다음과 같은 몇 가지 이점이 있습니다.

- **일관된 프로세스** — 구매 요청 및 경비 보고서와 같은 특정 문서에 대한 승인 프로세스를 정의할 수 있습니다. 워크플로 시스템을 사용하면 문서가 일관되고 효율적인 방식으로 처리되고 승인되도록 하는 데 도움이 됩니다.
- **프로세스 가시성** — 특정 워크플로 인스턴스의 상태, 기록 및 성능 메트릭을 추적할 수 있습니다. 이는 효율성을 개선하기 위해 워크플로를 변경해야 하는지 여부를 결정하는 데 도움이 됩니다.
- **중앙 집중식 작업 목록** — 사용자는 중앙 집중식 작업 목록을 보고 참여하는 모든 워크플로에서 자신에게 할당된 워크플로 작업 및 승인을 볼 수 있습니다. 이는 작업 항목 페이지에서 사용할 수 있습니다.

## <a name="the-types-of-workflows-that-you-can-create"></a>생성할 수 있는 워크플로 유형

조달 및 소싱에 사용할 수 있는 워크플로 유형은 다음과 같습니다.

| 형식 | 이 유형을 사용하여 |
|---|---|
| 구매 요청 검토 | 구매 요청에 대한 검토 및 승인 워크플로를 만듭니다. |
| 구매 요청 라인 검토 | 구매 요청 라인에 대한 검토 및 승인 워크플로를 만듭니다. |
| 구매 주문 워크플로 | 구매 주문에 대한 검토 및 승인 워크플로를 만듭니다. |
| 구매 주문 라인 워크플로 | 구매 주문에 대한 검토 및 승인 워크플로를 만듭니다. |
| 공급업체 추가 애플리케이션 워크플로 | 공급업체 요청을 통해 새 공급업체를 추가하기 위한 검토 및 승인 워크플로를 만듭니다. |

> [!IMPORTANT]
> 새 워크플로를 추가할 때 **워크플로 만들기** 대화 상자에 다음과 같은 사용되지 않는 워크플로가 나열될 수도 있습니다. 이는 [Dynamics AX 2012](/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows)에서 사용할 수 있었지만 현재는 더 이상 사용되지 않는 *영수증 확인* 기능과 관련이 있습니다. 이러한 워크플로는 현재 지원되지 않습니다.
> 
> - 배송 기한 알림 워크플로
> - 송장 수신 알림 워크플로
> - 제품 수령 실패 알림 워크플로
> - 확인하지 않은 제품 입고 거부 알림 워크플로

## <a name="creating-a-workflow"></a>워크플로 생성

워크플로를 생성하려면 조달 및 소싱 &gt; 설정 &gt; 조달 및 소싱 워크플로로 이동하고 생성하려는 워크플로 유형을 선택하여 새 워크플로를 생성합니다. 

워크플로 캔버스에서 워크플로 요소를 디자이너로 끌어오고 요소를 흐름에 연결할 수 있습니다. 워크플로 요소를 구성해야 합니다. 승인 및 작업 워크플로 요소의 경우 조치를 취해야 하는 참가자를 구성할 수 있습니다.

## <a name="types-of-participants"></a>참가자 유형

다음 참가자 그룹에 승인 단계를 할당할 수 있습니다.

| 사용자 그룹 | 설명 |
|---|---|
| 참가자 | 그룹 또는 역할의 구성원에게 승인 단계를 할당합니다. |
| 계층 구조 | 특정 조직 계층의 사용자에게 승인 단계를 할당합니다. |
| 워크플로 사용자 | 이 워크플로의 사용자에게 승인 단계를 할당합니다. |
| 대기열 | 작업 항목 대기열에 승인 단계를 할당합니다. |
| 사용자 | 특정 사용자에게 승인 단계를 할당합니다. |

## <a name="additional-resources"></a>추가 리소스

- [구매 요청에 대한 비즈니스 프로세스 워크플로 정의](https://www.microsoft.com/download/details.aspx?id=101821)
- [구매 요청 워크플로](purchase-requisitions-workflow.md)
- [온보딩 공급업체](vendor-onboarding.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]