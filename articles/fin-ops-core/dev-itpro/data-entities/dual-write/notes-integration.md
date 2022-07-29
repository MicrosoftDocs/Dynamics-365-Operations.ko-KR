---
title: 노트 통합
description: 이 항목에서는 이중 쓰기로 노트 데이터의 통합에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c73da804d724ea75ae6ccd479d1b7f3cf02d48c4
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8461019"
---
# <a name="note-integration"></a>노트 통합

[!include [banner](../../includes/banner.md)]



비즈니스 프로세스 중 Microsoft Dynamics 365 사용자는 종종 고객에 대한 정보를 수집합니다. 이 정보는 활동 및 메모로 기록됩니다. 이 항목에서는 이중 쓰기로 노트 데이터의 통합에 대해 설명합니다.

고객 정보는 다음과 같이 분류할 수 있습니다.

+ **Dynamics 365 사용자가 고객을 대신하여 처리하는 실행 가능한 정보** – 예를 들어 Contoso(Dynamics 365 사용자)는 게임 쇼를 진행하고 있습니다. Contoso의 고객 중 한 명(고객)이 게임 쇼에 참석하기를 원합니다. 고객이 Contoso 직원에게 게임 쇼의 슬롯을 예약해 달라고 요청합니다. 예약은 Contoso의 이벤트 참석자 일정에서 발생합니다.
+ **Dynamics 365 사용자를 위한 실행 가능한 정보** – 예를 들어 Surface 장치를 구매하는 고객은 배송 전에 장치를 선물 포장해야 함을 나타내는 특별 지침을 입력합니다. 이러한 지침은 포장을 담당하는 Contoso 직원이 처리해야 하는 실행 가능한 정보입니다.
+ **실행 불가능한 정보** – 예를 들어 고객이 Contoso 매장을 방문하여 매장 직원과 대화하는 동안 *Halo* 게임 및 게임 액세서리에 관심을 보입니다. 상점 직원은 이 정보를 기록합니다. 그런 다음 제품 추천 엔진은 이를 사용하여 고객에게 추천합니다.

일반적으로 실행 가능한 정보는 금융 및 운영 앱 및 Customer Engagement 앱에 *활동* 으로 캡처됩니다. 실행 가능하지 않은 정보는 금융 및 운영 앱에 *노트* 로 Customer Engagement 앱에 *주석* 으로 캡처됩니다.

> [!TIP]
> 메모는 실행할 수 없는 정보를 위한 것이지만 이러한 방식으로 사용하려는 경우 앱에서 실행 가능한 정보를 저장하고 처리하는 데 메모를 사용하는 것을 방지하지 않습니다.

Microsoft는 현재 메모 통합 기능을 출시하고 있습니다. (액티비티 통합 기능은 추후 공개될 예정입니다.) 참고 통합은 고객, 벤더, 판매 주문, 구매 주문에서 가능합니다.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Customer Engagement 앱에서 메모 만들기

Customer Engagement 앱에서 메모를 만든 다음 재무 및 운영 앱과 동기화하려면 다음 단계를 따르세요.

1. Customer Engagement 앱에서 고객의 계정 레코드를 엽니다.
2. **타임라인** 창에서 더하기 기호(**+**)를 선택한 다음 **메모** 를 선택하여 메모를 생성합니다.

    ![Customer Engagement 앱에서 메모 만들기.](media/notes-ce-1.png)

3. 제목과 설명을 입력하고 **메모 추가** 를 선택합니다.

    ![제목과 설명을 입력합니다.](media/notes-ce-2.png)

    새 메모가 고객 타임라인에 추가됩니다.

    ![고객 타임라인에 대한 새로운 메모입니다.](media/notes-ce-3.png)

4. 재무 및 운영 앱에 로그인하고 동일한 고객 기록을 엽니다. 오른쪽 상단의 **첨부 파일** 버튼(종이 클립 기호)은 레코드에 첨부 파일이 있음을 나타냅니다.

    ![첨부 파일에 대한 알림입니다.](media/notes-ce-4.png)

5. **첨부 파일** 버튼을 선택하여 **첨부 파일** 페이지를 엽니다. Customer Engagement 앱에서 작성한 메모를 찾아야 합니다.

    ![Customer Engagement 앱의 메모.](media/notes-ce-5.png)

메모에 대한 모든 업데이트는 재무 및 운영 앱과 Customer Engagement 앱 간에 동기화됩니다.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>재무 및 운영 앱에서 메모 만들기

또한 재무 및 운영 앱에서 메모를 만들면 Customer Engagement 앱에 동기화됩니다.

재무 및 운영 앱에서 메모를 만든 다음 Customer Engagement 앱과 동기화하려면 다음 단계를 따르세요.

1. 재무 및 운영 앱의 **첨부 파일** 페이지에서 **새로 만들기** \> **메모** 를 선택합니다.

    ![재무 및 운영 앱에서 메모 만들기.](media/notes-fo-1.png)

2. 제목과 간단한 지침을 입력한 다음 **저장** 을 선택합니다.

    ![제목과 지침을 입력합니다.](media/notes-fo-2.png)

3. Customer Engagement 앱에서 레코드를 업데이트합니다. 타임라인에서 새 메모를 찾아야 합니다.

    ![Customer Engagement 앱의 타임라인에 대한 새로운 메모입니다.](media/notes-fo-3.png)

메모를 내부 또는 외부로 분류할 수 있습니다.

- 재무 및 운영 앱의 **첨부 파일** 페이지에서 메모를 연 다음 **제한** 필드에서 **내부** 또는 **외부** 를 선택합니다.

    ![제한 필드.](media/notes-fo-4.png)

URL을 만들 수도 있습니다.

1. 재무 및 운영 앱의 **첨부 파일** 페이지에서 **새로 만들기** \> **URL** 을 선택합니다.
2. 제목 및 URL을 입력합니다.
3. **제한** 필드에서 **내부** 또는 **외부** 를 선택합니다.

    ![재무 및 운영 앱에서 URL 만들기.](media/notes-fo-5.png)

4. **저장** 을 선택합니다.

    Customer Engagement 앱에는 URL 유형이 없기 때문에 URL은 메모로 이중 쓰기와 통합됩니다.

    ![Customer Engagement 앱에서 메모로 표시되는 URL.](media/notes-ce-6.png)

> [!NOTE]
> 파일 첨부는 지원되지 않습니다.

## <a name="templates"></a>템플릿

메모 통합에는 다음 표와 같이 데이터 상호 작용 중에 함께 작동하는 테이블 맵 모음이 포함됩니다.

| 금융 및 운영 앱 | Customer Engagement 앱 | 설명 |
|----------------------------|-------------------------|-------------|
| [고객 첨부 파일](mapping-reference.md#230) | 주석 | 일반 텍스트 및 URL을 사용하여 고객별 정보(조직 및 개인 모두에 대해)를 캡처하는 비즈니스. |
| [공급업체 문서 첨부](mapping-reference.md#231) | 주석 | 일반 텍스트 및 URL을 사용하여 공급업체별 정보(조직 및 개인 모두에 대해)를 캡처하는 비즈니스. |
| [매도 주문 헤더 문서 첨부 파일](mapping-reference.md#229) | 주석 | 일반 텍스트와 URL을 사용하여 판매 주문 관련 정보를 캡처하는 비즈니스. |
| [구매 주문 헤더 문서 첨부 파일](mapping-reference.md#232) | 주석 | 일반 텍스트와 URL을 사용하여 구매 주문 관련 정보를 캡처하는 비즈니스. |

## <a name="limitations"></a>제한 사항

메모 솔루션을 설치한 후에는 제거할 수 없습니다. 

자세한 내용은 [이중 쓰기 매핑 참조](mapping-reference.md)를 참조하세요.
