---
title: 수금 프로세스 자동화
description: 이 토픽에서는 이메일 알림, 수금 활동 또는 고객에게 보낼 수금 편지가 필요한 고객 송장을 자동으로 식별하는 수금 프로세스 전략을 설정하는 프로세스에 대해 설명합니다.
author: JodiChristiansen
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 59db852024faf457db7ac145b67619b31555aaf2
ms.sourcegitcommit: 3f6cbf4fcbe0458b1515c98a1276b5d875c7eda7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2021
ms.locfileid: "8450967"
---
# <a name="collections-process-automation"></a>수금 프로세스 자동화

[!include [banner](../includes/banner.md)]

이 토픽에서는 이메일 알림, 수금 활동(예: 전화 통화) 또는 고객에게 보낼 수금 편지가 필요한 고객 송장을 자동으로 식별하는 수금 프로세스 전략을 설정하는 프로세스에 대해 설명합니다. 

조직은 미결 송장 또는 계정 잔액에 대해 어떤 고객에게 연락해야 하는지 알아보기 위해 오래된 잔액 보고서, 고객 계정 및 미결 송장을 조사하는 데 상당한 시간을 할애하는 경우가 많습니다. 이 연구는 연체 잔액을 수금하거나 송장 분쟁을 해결하기 위해 고객과 통신하는 데 수금 직원이 소비하는 시간을 줄였습니다. 수금 프로세스 자동화를 통해 수금 프로세스에 대한 전략 기반 접근 방식을 설정할 수 있습니다. 이것은 맞춤형 이메일 알림 또는 수금 편지 발송을 위한 프로그래밍된 프로세스를 제공하여 수금 활동을 일관되게 적용하는 데 도움이 됩니다. 

## <a name="collections-process-setup"></a>수금 프로세스 설정
**수금 프로세스 설정** 페이지(**신용 및 수금 > 설정 > 수금 프로세스 설정**)를 사용하여 활동을 예약하고, 이메일 메시지를 보내고, 고객 수금 편지를 작성하고 전기하는 자동화된 수금 프로세스를 만들 수 있습니다. 프로세스 단계는 선행 또는 가장 오래된 미결 송장을 기반으로 합니다. 각 단계에서는 이 송장을 사용하여 특정 고객과 어떤 커뮤니케이션이나 활동을 해야 하는지 결정합니다.  

수금 팀은 일반적으로 미결 송장과 관련된 조기 통지를 보내어 송장이 만기가 되려고 하는 시기를 고객에게 알립니다. **사전 독촉** 선택은 송장 타이밍이 해당 단계에 도달할 때 각 송장에 대해 각 프로세스 계층의 한 단계가 실행되도록 설정할 수 있습니다.

### <a name="process-hierarchy"></a>프로세스 계층
각 고객 풀은 하나의 프로세스 계층에만 할당할 수 있습니다. 이 단계의 계층 순위는 프로세스 계층이 할당된 둘 이상의 풀에 고객이 포함된 경우 어떤 프로세스가 우선 적용되는지 식별합니다. 풀 ID는 프로세스에 할당할 고객을 결정합니다. 설정된 각 계층 구조는 하나의 프로세스 자동화에만 할당할 수 있습니다.

침묵의 날은 자동화된 프로세스로 인해 고객에게 너무 자주 연락하지 않도록 하는 데 사용됩니다. 예를 들어, 침묵의 날을 2일로 설정하면 원본 선행 송장이 완전히 정산된 경우에도 최소 2일 동안은 자동화된 프로세스에서 고객에게 연락하지 않습니다. 

고객 에이징 잔액 또는 송장 금액이 정의된 값보다 작은 경우 프로세스 자동화에서 고객을 제외하려면 **프로세스에서 제외** 필드에서 **고객 에이징 잔액 부족** 또는 **송장 금액 부족** 을 선택하고 금액 값을 입력합니다.

**예측 사용** 을 표시하여 고객 지불 예측을 사용하여 수금 활동을 생성합니다. 생성된 활동은 **수취 계정 매개 변수** 페이지, **수금 프로세스 자동화** 탭에 있는 **지불 예측** 의 활동 템플릿을 사용합니다. 

### <a name="process-details"></a>프로세스 세부 정보
**새로 만들기** 를 클릭하여 계층에 새 프로세스 세부 정보를 추가합니다. **설명** 은 계층 구조에서 단계의 목적 또는 이름을 식별하는 데 사용됩니다. **작업 유형** 을 선택하여 활동을 생성하거나, 이메일을 보내거나, 수금 편지를 작성하는 단계를 정의합니다. 

- **비즈니스 문서** 는 작업 유형을 생성하는 데 사용되는 템플릿을 정의합니다. 이 문서는 활동 템플릿, 이메일 템플릿 또는 각 고객에게 발송되는 수금 편지일 수 있습니다. 수금 프로세스 자동화는 다른 수금 매개 변수가 설정되는 방식에 관계없이 고객당 수금 편지만 생성합니다.
- **언제** 은 선행(가장 오래된) 송장 만기일 이전 또는 이후에 발생할 프로세스 단계를 정의하며 **송장 만기일과 관련된 일 수** 열에 표시된 숫자와 함께 사용됩니다. 
- 프로세스 계층의 한 단계에서 모든 송장에 대한 작업을 생성하려면 **사전 독촉** 옵션을 선택하십시오. 사전 독촉 조치는 일반적으로 미결 송장과 관련된 조기 통지이므로 송장이 만기가 되려고 하는 시기를 고객에게 알립니다. 사전 독촉은 계층당 하나의 활동에 대해서만 표시할 수 있습니다. 이메일 작업 유형을 선택하면 수신자는 이메일 메시지를 고객, 영업 그룹 또는 수금 직원 연락처로 보낼지 여부를 정의하는 데 사용됩니다. 
- **비즈니스 목적 연락처** 필드의 값에 따라 해당 고객 계정의 어떤 연락처가 커뮤니케이션을 받을지 결정됩니다.

### <a name="business-document-details"></a>비즈니스 문서 세부 정보
비즈니스 문서 세부 정보는 프로세스 세부 정보에서 선택한 작업 유형에 따라 달라집니다. 작업 유형이 활동인 경우 활동 템플릿 세부 정보가 표시됩니다. 이러한 세부 정보에는 활동 템플릿 이름, 생성될 활동 유형, 활동 목적, 활동을 완료하도록 예약된 일 수 및 활동 세부 정보가 포함됩니다. 그런 다음 이 활동은 활동을 완료하는 데 필요한 작업을 수신자에게 알리는 선행 송장에 연결됩니다.

작업 유형이 프로세스 세부 정보의 이메일인 경우 이 섹션에는 두 개의 빠른 탭이 포함됩니다. 첫 번째는 템플릿 ID, 이메일 설명, 기본 언어, 자동으로 전송되는 이메일 메시지에 할당될 사용자 이름 및 연결된 발신자 이메일 주소를 정의하는 데 사용됩니다. 두 번째는 **편집** 을 선택하여 **언어** 및 **주제** 필드의 값을 저장한 후 이메일 본문을 작성하도록 허용합니다. 그러면 HTML 콘텐츠를 업로드할 수 있는 창이 열립니다. 

> [!Note]
> 커뮤니케이션의 본문 텍스트가 포함된 Outlook 이메일 메시지를 HTML 형식으로 저장할 수 있습니다. 그런 다음 메시지 콘텐츠를 업로드하여 템플릿을 구현할 수 있습니다. <br> <br> 수금 편지의 작업 유형을 선택한 경우 설정 페이지에 비즈니스 문서 세부 정보 섹션이 없습니다.

**수금 프로세스 기록** 버튼을 사용하여 선택한 프로세스 계층에 대한 최근 기록을 봅니다. 

**수금 프로세스 할당** 작업을 클릭하여 수금 프로세스에 할당된 고객을 봅니다. **고객 할당 미리 보기** 를 사용하여 특정 고객이 할당된 계층을 봅니다. **프로세스 할당 미리 보기** 를 사용하여 계층이 실행될 때 계층에 할당될 고객을 미리 봅니다. **수동 할당** 을 클릭하여 프로세스에 수동으로 할당된 고객을 보거나 프로세스를 할당할 고객을 선택합니다.

**프로세스 시뮬레이션** 작업을 클릭하여 현재 선택한 프로세스 자동화가 실행되는 경우 생성될 작업을 미리 봅니다. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]