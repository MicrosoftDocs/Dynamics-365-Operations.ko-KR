---
title: 공정 제조를 위한 시퀀스 생산 작업
description: 이 절차에서는 페인트 제품을 예로 사용하여 색상 및 패키지 크기의 우선 순위에 따라 계획 주문의 순서를 지정하는 방법을 보여줍니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransPo, PMFSeqReqRouteChangesListPage, PMFSeqReqRoute, PMFSeqReqRouteChanges, PMFSeqReqSchedDetailsFactBox, PMFSequenceGroup, PMFSequenceItemTable, PMFSequenceTable, PmfSeqWrkCtrCapRes
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e54cfa60fa9efd511aef8c074484b9b1a738e8cb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448552"
---
# <a name="sequence-production-jobs-for-process-manufacturing"></a>공정 제조를 위한 시퀀스 생산 작업

[!include [banner](../../includes/banner.md)]

이 절차에서는 페인트 제품을 예로 사용하여 색상 및 패키지 크기의 우선 순위에 따라 계획 주문의 순서를 지정하는 방법을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USPI입니다. 이 절차는 생산 계획자를 위한 것입니다.


## <a name="run-master-planning-for-uspi"></a>USPI에 대한 기준 계획 실행
1. 기준 계획 > 기준 계획 > 실행 > 기준 계획으로 이동합니다.
2. 기준 계획 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
    * 마스터계획을 선택합니다.  
4. 확인을 클릭합니다.
    * 그러면 시퀀스 프로세스를 포함한 기준 계획이 시작됩니다. 이 프로세스는 몇 분 정도 걸릴 수 있습니다.  

## <a name="view-planned-orders-for-the-paint-products"></a>페인트 제품에 대한 계획 주문 보기
1. 기준 계획 > 기준 계획 > 계획 주문으로 이동합니다.
2. 항목 세부 정보 팩트 상자를 확장합니다.
3. 일정 세부 정보 팩트 상자를 확장합니다.
4. 계획 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
5. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 마스터계획을 선택합니다.  
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. 빠른 필터를 사용하여 'P300' 값으로 품목 번호 필드를 필터링합니다.
    * 잠금을 해제하면 오른쪽으로 스크롤하여 주문 날짜와 배송 날짜를 볼 수 있습니다. 이러한 항목의 주문 날짜는 오늘이며 계획 주문의 배송 날짜는 제품 이름에서 볼 수 있듯이 색상 및 패키지 크기의 우선 순위 이후에 순서가 지정되지 않습니다. 품목 번호 위로 마우스를 가져가면 제품 이름과 우선 순위를 볼 수 있습니다.  

## <a name="sequence-planned-orders-for-paint"></a>페인트에 대한 시퀀스 계획 주문
1. 페이지를 닫습니다.
2. 기준 계획 > 기준 계획 > 시퀀스된 계획 주문으로 이동합니다.
3. 항목 세부 정보 팩트 상자를 확장합니다.
4. 일정 세부 정보 팩트 상자를 확장합니다.
    * 참고: 여기에서 계획 주문의 시작 날짜/시간이 28일의 버킷 기간 내에서 색상 및 패키지 크기에 따라 순서가 지정되었음을 알 수 있습니다. 이러한 기간은 캠페인 필드의 숫자로 정의됩니다. 시퀀스된 계획 주문 양식은 일반적인 계획 주문 양식처럼 작동하며 생산 계획자는 여기에서 계획 주문을 확정할 수 있습니다.  
5. 모든 행을 표시합니다.
6. 수락을 클릭합니다.
    * 그러면 연기 또는 사전 중에서 선택한 순서 조치로 계획 주문이 업데이트됩니다.  

## <a name="verify-the-sequence-of-the-planned-orders"></a>계획 주문의 순서 확인
1. 페이지를 닫습니다.
2. 기준 계획 > 기준 계획 > 계획 주문으로 이동합니다.
3. 항목 세부 정보 팩트 상자를 확장합니다.
4. 일정 세부 정보 팩트 상자를 확장합니다.
5. 계획 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 마스터계획을 선택합니다.  
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. 빠른 필터를 사용하여 'P300' 값으로 품목 번호 필드를 필터링합니다.
    * 현재 주문은 색상 및 크기의 우선 순위에 따라 순서가 지정되며 계획 주문은 가장 빠른 주문 날짜와 배송 날짜에 시작됩니다. 일정 세부 정보 팩트 상자에서 주문 날짜 열 또는 시작 날짜를 확인합니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]