---
title: 원장 달력 변경 또는 재할당
description: 이 항목에서는 현재 원장에 할당된 일정을 변경하는 방법과 원장에 새 일정을 할당하는 방법에 대해 설명합니다.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 16000243bc8aa76b04ac56dfb8bfbab7cd644eb3120cc68493ff066598f6cf85
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452788"
---
# <a name="change-or-reassign-a-ledger-calendar"></a>원장 달력 변경 또는 재할당

[!include [banner](../includes/banner.md)]

이 항목에서는 현재 원장에 할당된 일정을 변경하는 방법과 원장에 새 일정을 할당하는 방법에 대해 설명합니다.

## <a name="issue"></a>문제

회사에서 원장에 할당된 기존 일정을 변경하거나 새 일정을 할당해야 할 때가 있습니다.

## <a name="resolution"></a>해결책

원장 일정을 변경하거나 재할당하는 방법은 두 가지가 있습니다. 첫 번째 방법은 원장에 할당된 기존 일정을 변경하는 것입니다. 두 번째 방법은 새 일정을 만들고 원장에 할당하는 것입니다. 두 가지 변경 모두 언제든 적용할 수 있습니다. 거래가 원장에 전기된 후에도 가능합니다.

### <a name="change-an-existing-fiscal-calendar"></a>기존 회계 일정 변경

원장에 할당된 기존 일정을 변경하려면 **총계정원장 \> 원장 설정 \> 원장** 으로 이동한 다음 회계 일정 링크를 선택하여 **원장 일정** 페이지를 여세요.

캘린더에 적용할 수 있는 변경에는 제한이 있습니다. 예를 들어 연중 *기간* 의 시작 날짜와 종료 날짜는 변경할 수 있지만, 일정에 있는 *연도* 의 시작 날짜와 종료 날짜는 변경할 수 없습니다.

연도의 기간을 변경하려면 관련 일정과 연도를 선택합니다. 먼저 **기간 삭제** 단추를 사용하여 기존 운영 기간의 일부 또는 전체를 삭제합니다. 첫 번째를 제외한 모든 운영 기간을 삭제할 수 있습니다. 이제 **기간 분할** 단추를 누르고 다음 기간의 적절한 시작 날짜를 입력하여 남은 기간 또는 기간을 새 기간으로 분할합니다.

일정에서 기간을 변경했다면 일정에서 할당한 모든 법인(회사)에서 **원장 기간 재계산** 프로세스를 실행해야 합니다. 이 단계를 완료하라는 경고 메시지는 표시되지 않지만, 총계정원장의 각 전기 거래에 할당된 기간을 업데이트하려면 재계산 프로세스를 실행해야 합니다. 재계산 프로세스를 실행하려면 각 회사의 **원장 설정** 페이지에서 **원장 기간 재계산** 을 선택합니다.

재계산 프로세스가 실행되지 않으면 시산표 또는 재무제표상의 거래 잔액이 기간에 잘못 포함될 수 있습니다. 이 경우 재계산 프로세스를 실행하면 언제든지 잔액을 수정할 수 있습니다.

### <a name="assign-a-new-fiscal-calendar"></a>새 회계 일정 할당

새 회계 일정을 할당하려면 **총계정원장 \> 원장 설정 \> 원장** 으로 이동한 다음 **편집** 을 선택하여 **원장** 페이지를 편집 모드로 변경합니다. 그런 다음 **회계 일정** 필드에서 새 회계 일정을 선택합니다.

원장의 회계 일정을 변경한 후에는 **원장 기간 재계산** 을 실행해야 합니다. 원장에 새 회계 일정을 할당하면 이 단계를 완료하라는 메시지가 표시됩니다. 메시지 때문에 재계산 프로세스가 선택 사항처럼 보일지도 모르지만, 실제로는 그렇지 않습니다. 총계정원장에 있는 각 전사 거래에 할당된 기간을 업데이트해야 합니다. 재계산 프로세스를 실행하려면 **원장 설정** 페이지에서 **원장 기간 재계산** 을 선택합니다.

재계산 프로세스가 실행되지 않으면 시산표 또는 재무제표상의 거래 잔액이 기간에 잘못 포함될 수 있습니다. 이 경우 재계산 프로세스를 실행하면 언제든지 잔액을 수정할 수 있습니다.