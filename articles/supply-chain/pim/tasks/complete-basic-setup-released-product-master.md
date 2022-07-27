---
title: 출시된 제품 기준의 기본 설정 완료
description: 이 항목에서는 제품 마스터를 BOM 버전에서 사용하기 전에 필요한 최소 설정을 완료하는 방법을 보여줍니다.
author: t-benebo
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1ec567892c09968fe80c3a075d656185aceb4e5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448120"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>출시된 제품 기준의 기본 설정 완료

[!include [banner](../../includes/banner.md)]

이 항목에서는 제품 마스터를 BOM 버전에서 사용하기 전에 필요한 최소 설정을 완료하는 방법을 보여줍니다.

이는 치수 기반 구성을 위한 조합을 구축하는 방법을 설명하는 8개 중 세 번째 절차입니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.

1. **탐색 창 > 모듈 > 제품 정보 관리 > 제품 > 출시된 제품** 으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다. 두 번째 절차에서 릴리스한 제품 마스터를 선택합니다. 이 제품 마스터는 차원 기반 구성 기술로 생성됩니다.  
3. 작업 창에서 **제품** 을 선택합니다.
4. **차원 그룹** 을 선택하여 드롭 대화 상자를 엽니다.
5. **재고 규모 그룹** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다. 저장소 차원 그룹은 제품 트랜잭션에 사용되는 저장소 차원을 결정합니다. 이 절차에 대해 **사이트** 를 선택합니다.  
7. **추적 규모 그룹** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.
8. 목록에서 원하는 레코드를 찾아 선택합니다. 추적 규모 그룹은 제품 트랜잭션에 사용되는 추적 규모를 결정합니다. 이 절차에 대해 **없음** 을 선택합니다.  
9. **확인** 을 클릭합니다.
10. **편집** 을 클릭합니다.
11. **항목 모델 그룹** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.
12. 목록에서 원하는 레코드를 찾아 선택합니다. 항목 모델 그룹에는 항목 입고 및 출고 시 항목을 제어하고 처리하는 방법을 결정하는 설정이 포함되어 있습니다. 또한 항목 소비가 계산되는 방식을 결정합니다. 이 절차에 대해 **FIFO** 를 선택합니다.  
13. **비용 관리** 섹션을 펼칩니다.
14. **항목 모델 그룹** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.
15. 목록에서 원하는 레코드를 찾아 선택합니다. 항목 그룹은 재고 항목을 그룹으로 나누어 재고를 관리하는 데 사용됩니다. 이 절차에 대해 **CarAudio** 를 선택합니다.  
16. 작업 창에서 **계획** 을 선택합니다.
17. **기본 주문 설정** 을 선택합니다.
18. **기본 주문 유형 필드** 에서 옵션을 선택합니다. **생산** 을 선택하여 이 제품 마스터에 대한 기본 공급 옵션이 생산임을 지정합니다.  
19. **저장** 을 선택합니다.
20. 페이지를 닫습니다.
21. **출시된 제품 세부 정보** 양식을 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]