---
title: 번호판 통제가 아닌 장소에 완료로 보고(적용, 2016년 5월)
description: 이 작업 가이드는 번호판으로 제어되지 않는 위치에 완료된 것으로 보고하는 예를 보여줍니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdParmCostEstimation, ProdParmStartUp, ProdParmReportFinished, WHSWorkTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f891b2e3b20993a08138dfac1aed4f4bab33c6b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448936"
---
# <a name="report-as-finished-to-a-non-license-plate-controlled-location--application-may-2016"></a>번호판 통제가 아닌 장소에 완료로 보고(적용, 2016년 5월)

[!include [banner](../../includes/banner.md)]

이 작업 가이드는 번호판으로 제어되지 않는 위치에 완료된 것으로 보고하는 예를 보여줍니다. 해당 작업 정책은 이 작업의 전제 조건입니다. 이전 작업 가이드는 작업 정책의 설정을 보여주었습니다. 이 작업 가이드는 Dynamics AX 애플리케이션 7.0.1 이상이 필요합니다.




## <a name="set-up-an-output-location"></a>출력 위치 설정
1. 조직 관리 > 리소스 > 리소스 그룹으로 이동합니다.
2. 목록에서 리소스 그룹 '5102'를 선택합니다.
3. 편집을 클릭합니다.
4. 출력 창고 필드에 '51'을 입력합니다.
5. 출력 위치 필드에 '001'을 입력합니다.
    * 위치 001은 번호판이 통제되는 위치가 아닙니다. 해당 위치에 적용 가능한 작업 정책이 있는 경우에만 비번호판 출력 위치를 설정할 수 있습니다.  

## <a name="create-a-production-order-and-report-it-as-finished"></a>생산 주문을 생성하고 완료된 것으로 보고합니다.
1. 페이지를 닫습니다.
2. 생산 관리 > 생산 주문 > 모든 생산 주문으로 이동합니다.
3. 새로운 생산 주문을 클릭합니다.
4. 품목 번호 필드에 'L0101'을 입력합니다.
5. 만들기를 클릭합니다.
6. 작업 창에서 생산 주문을 클릭합니다.
7. 견적을 클릭합니다.
8. 확인을 클릭합니다.
9. 시작을 클릭합니다.
10. 일반 탭을 클릭합니다.
11. 자동 BOM 소비 필드에서 '안함'을 선택합니다.
12. 확인을 클릭합니다.
13. 완료로 보고를 클릭합니다.
14. 일반 탭을 클릭합니다.
15. 오류 수락 필드에서 예를 선택합니다.
16. 확인을 클릭합니다.
17. 작업 창에서 창고를 클릭합니다.
18. 작업 세부정보를 클릭합니다.
    * 생산 주문이 완료된 것으로 보고되었을 때 배치할 작업이 생성되지 않았습니다. 이는 제품 L0101이 위치 001까지 완료된 것으로 보고될 때 작업이 생성되지 않도록 하는 작업 정책이 정의되어 있기 때문에 발생합니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]