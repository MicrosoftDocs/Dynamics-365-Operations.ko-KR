---
title: 생산 주문을 시작합니다.
description: 이 절차는 작업 현장에서 생산 주문을 시작하는 방법을 보여줍니다.
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationStartJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa47510d84e5ee156d4f38a076ce17fad8359d147997349de023b64483d66160
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446833"
---
# <a name="start-a-production-order"></a>생산 주문을 시작합니다.

[!include [banner](../../includes/banner.md)]

이 절차는 작업 현장에서 생산 주문을 시작하는 방법을 보여줍니다. 이 프로세스에서 시간 및 재료 소비가 보고됩니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 생산 주문 수명 주기를 설명하는 7가지 중 5번째 절차입니다.


## <a name="start-a-production-order"></a>생산 주문을 시작합니다.
1. 생산 관리 > 생산 주문 > 모든 생산 주문으로 이동합니다.
    * 릴리스됨 상태의 생산 주문을 선택합니다.  
2. 작업 창에서 생산 주문을 클릭합니다.
3. 시작을 클릭합니다.
    * 이 페이지에서 생산 주문을 시작함을 확인할 수 있습니다.  
4. 일반 탭을 클릭합니다.
5. 시작 작업 번호 필드에 '10'을 입력합니다.
6. 자동 경로 소비 필드에서 '항상'을 선택합니다.
7. 지금 경로 카드 게시 확인란을 클릭합니다.
8. 자동 BOM 소비 필드에서 '항상'을 선택합니다.
9. 지금 불출 목록 게시 확인란을 클릭합니다.
10. 불출 목록 인쇄 확인란을 클릭합니다.
11. 확인을 클릭합니다.
    * 생산 주문에 사용된 자재를 보여주는 인쇄된 불출 목록입니다.  
12. 페이지를 닫습니다.

## <a name="validate-the-picking-list"></a>불출 목록을 확인합니다.
1. 작업 창에서 보기를 클릭합니다.
2. 불출 목록을 클릭합니다.
3. 목록에서 원하는 레코드를 찾아 선택합니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. 편집을 클릭합니다.
6. 소비 필드에 숫자를 입력합니다.
7. 전기를 클릭합니다.
8. 확인을 클릭합니다.
    * 불출 목록 분개장에 생산 주문에 의해 소비된 자재가 전기됩니다. 분개장을 전기하기 전에 예상 수량과 실제 소비 수량 사이에 차이가 있는 경우 조정할 수 있습니다.  
9. GridPanel 탭을 클릭합니다.
10. 페이지를 닫습니다.

## <a name="verify-the-route-card-journal"></a>경로 카드 분개장 확인
1. 작업 창에서 보기를 클릭합니다.
2. 경로 카드를 클릭합니다.
3. 목록에서 원하는 레코드를 찾아 선택합니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. 편집을 클릭합니다.
6. 시간 필드에 숫자를 입력합니다.
7. 전기를 클릭합니다.
8. 확인을 클릭합니다.
    * 경로 카드 분개장에는 개별 작업에 소요된 시간이 기록됩니다. 양호 및 오류 수량도 보고할 수 있습니다.  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]