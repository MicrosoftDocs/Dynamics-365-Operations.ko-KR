---
title: 수금 설정
description: 이 문서에서는 수금 기능을 설정하는 방법을 설명합니다.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustCollectionsActivitiesListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 14031
ms.assetid: dcc6da2f-9af5-4f1d-abaa-b72967b66979
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f2e06da265271e2148804c51abc7cd9ffc29a3e20e73dda3a1a23966f0e6586e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450748"
---
# <a name="set-up-collections"></a>수금 설정

[!include [banner](../includes/banner.md)]

이 문서에서는 수금 기능을 설정하는 방법을 설명합니다. 수금 기능을 사용하려면 몇 가지 설정 단계를 완료해야 합니다. 고객 풀 및 수금 팀을 비롯한 몇 가지 선택적 기능도 있습니다. 

- 에이징 기간 정의
- 에이징 스냅샷
- 분개장 이름
- 채무 인하 거래의 사유 코드
- 수금 직원
- 채무 인하 계정
- 잔고부족(NSF) 정보
- **수금** 페이지를 사용하는 사용자를 위한 Outlook 설정
- 이메일 주소

이러한 사항은 이 항목의 나머지 부분에서 자세히 설명합니다. 

## <a name="set-up-aging-period-definitions"></a>에이징 기간 정의 설정

에이징 기간 정의를 설정합니다. 에이징 기간 정의는 **에이징 잔액**, **수금 활동** 및 **수금 사례** 목록 페이지에 표시되는 열을 정의합니다. 또한 **수금** 페이지에 나타나는 기간을 정의합니다. 고객 풀이 설정되면 풀에 대한 에이징 기간 정의가 사용됩니다. 설정된 풀이 없으면 **수취 계정 매개 변수** 페이지에 지정된 기본 에이징 기간 정의가 사용됩니다. 기본 에이징 기간 정의가 지정되지 않은 경우 **에이징 기간 정의** 페이지의 첫 번째 에이징 기간 정의가 사용됩니다.

## <a name="create-an-aging-snapshot"></a>에이징 스냅샷 만들기
모든 고객 또는 고객 풀의 고객에 대해 에이징 스냅샷 레코드를 만듭니다. 에이징 스냅샷의 정보는 **에이징 잔액** 목록 페이지와 **수금** 페이지에 표시됩니다. 목록 페이지를 사용하려면 먼저 에이징 스냅샷을 만들어야 합니다. 에이징 스냅샷이 만들어진 고객에 대해서만 목록 페이지가 표시됩니다.

## <a name="optional-set-up-customer-pools"></a>선택 사항: 고객 풀 설정
고객의 그룹을 나타내도록 고객 풀을 설정할 수 있습니다. 고객 풀을 **수금** 목록 페이지, **수금** 페이지에 표시되거나 에이징 스냅샷을 생성할 때 표시되는 고객 정보에 대한 필터로 사용할 수 있습니다.

## <a name="optional-create-a-collections-team"></a>선택 사항: 수금 팀 만들기
조직의 여러 사람이 수금 작업을 수행하는 경우 수금 팀을 설정할 수 있습니다. **수취 계정 매개 변수** 페이지에서 팀을 선택할 수 있습니다. 수금 팀을 만들지 않으면 **수금 직원** 페이지에서 수금 직원을 설정할 때 팀이 자동으로 생성됩니다.

## <a name="set-up-a-collections-case-category"></a>수금 사례 범주 설정
사례를 사용하여 수금 작업을 구성하려면 **수금** 범주 유형이 있는 사례 범주를 설정합니다. **수금** 페이지에서 수금 기능을 사용하려는 경우에만 필요합니다.

## <a name="set-up-journal-names-settlement-writeoff-and-nsf"></a>분개장 이름 설정(정산, 채무 인하 및 NSF)
**수금** 페이지에서 거래가 처리될 때 사용되는 분개장 이름을 설정합니다. 이 처리에는 거래 정산, 거래 채무 인하, 잔고부족(NSF) 지불 처리가 포함됩니다.

| 설명 | 분개장 유형     |
|-------------|------------------|
| 정산  | 고객 지불 |
| 채무 인하   | 매일            |
| NSF         | 고객 지불 |

## <a name="set-up-a-reason-code-for-writeoff-transactions"></a>채무 인하 거래의 사유 코드 설정
**수금** 페이지에서 거래가 채무 인하될 때 사용되는 기본 사유 코드를 설정합니다. 채무 인하 처리에서 코드를 변경할 수 있습니다.

## <a name="set-up-a-folder-for-email-attachments-and-create-email-templates"></a>이메일 첨부 파일을 위한 폴더 설정 및 이메일 템플릿 만들기
**수금** 페이지에서 Microsoft Excel 첨부 파일이 있는 이메일 메시지를 보내려는 경우 해당 메시지에 대한 선택적 이메일 템플릿을 만들 수 있습니다.

## <a name="set-up-accounts-receivable-parameters-for-collections"></a>수금을 위한 수취 계정 매개 변수 설정
**수금** 탭에 표시되는 수취 계정 매개 변수를 설정합니다.

## <a name="optional-set-up-collections-agents"></a>선택 사항: 수금 직원 설정
조직의 여러 사람이 수금 작업을 수행하는 경우 수금 직원을 설정할 수 있습니다. 수금 직원은 **사용자 관계** 페이지에서 사용자로 설정된 작업자입니다. 고객 풀(고객 쿼리)을 수금 직원에게 할당하여 직원이 작업을 구성하는 데 도움을 줄 수 있습니다. 수금 직원은 **수취 계정 매개 변수** 페이지에서 선택한 팀에 추가됩니다. 해당 페이지에 팀을 선택하지 않은 경우 **수금** 이라는 새 팀이 자동으로 생성되고 수금 직원이 해당 팀에 추가됩니다.

## <a name="set-up-a-writeoff-account"></a>채무 인하 계정 설정
거래가 채무 인하될 때 총계정원장 채무 인하 입력에 사용되는 채무 인하 계정을 설정합니다. 이 계정은 고객 게시 프로필에 저장됩니다.

## <a name="set-up-nsf-information-for-bank-accounts"></a>은행 계좌에 대한 NSF 정보 설정
**수금** 페이지에서 NSF 지불이 식별될 때 정확한 분개장이 있도록 은행 계좌를 업데이트합니다. **통화 관리** 탭의 **NSF 지불 분개장** 필드에 지불 분개장을 선택합니다.

## <a name="set-up-outlook-settings-for-users-of-the-collections-page"></a>수금 페이지 사용자를 위한 Outlook 설정 지정
작업자가 **수금** 페이지를 사용하여 활동을 생성하거나 이메일 메시지를 보낼 수 있게 하려면 **Microsoft Outlook 동기화** 구성 키를 선택하고 해당 작업자에 대해 Outlook 동기화를 설정해야 합니다.

## <a name="set-up-email-and-addresses"></a>이메일 및 주소 설정
이메일을 사용하여 고객 및 영업 사원 모두와 수금 문제에 관해 소통하고 **수금** 페이지에서 이메일 메시지를 보낼 수 있습니다. 

### <a name="set-up-email-and-address-settings-for-collections-customer-contacts"></a>수금 고객 연락처에 대한 이메일 및 주소 설정 지정
**수금** 페이지에서 해당 연락처에 이메일 메시지를 보낼 고객 연락처의 이메일 주소를 설정합니다. 수금 연락처는 **수금** 페이지에서 기본 연락처로 사용됩니다. 내역서에 기본 주소가 아닌 다른 주소를 사용해야 하는 경우 고객의 내역서 주소를 설정할 수 있습니다. 

고객에 대한 **신용 및 수금** 빠른 탭의 **수금 담당자** 필드에서 수금 직원과 협력하는 고객 조직의 사람을 선택합니다. 이 사람은 **수금** 페이지에서 기본 연락처로 사용되며 이메일 메시지가 전송됩니다. 

> [!NOTE] 
> 고객에 대한 수금 연락처가 지정되지 않은 경우 고객의 기본 연락처가 사용됩니다. 기본 연락처가 지정되지 않은 경우 **연락처** 페이지에 나열된 첫 번째 주소로 이메일 메시지가 전송됩니다.

### <a name="set-up-email-settings-for-salespeople"></a>영업 사원을 위한 이메일 설정 지정
**수금** 페이지에서 영업 사원에 이메일 메시지를 보낼 영업 사원의 이메일 주소를 설정합니다. 각 수수료 판매 그룹의 각 판매 담당자에 대한 이메일 주소를 설정합니다. **연락처** 옵션이 선택된 영업 담당자는 이메일 메시지가 전송되는 기본 영업 사원입니다. 

영업 담당자를 지정하지 않으면 고객 조직의 기본 영업 사원이 사용됩니다. 기본 영업 사원이 지정되지 않은 경우 연락처 페이지에 나열된 첫 번째 영업 사원에게 이메일 메시지가 전송됩니다.


자세한 내용은 다음 항목을 참조하세요.

 - [추심서 시퀀스 만들기](tasks/create-collection-letter-sequence.md)

 - [추심서 처리](tasks/process-collection-letters.md)

 - [수금 정보 검토](tasks/review-collections-information.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]