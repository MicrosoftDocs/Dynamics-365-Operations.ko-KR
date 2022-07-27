---
title: 허브 보조 요금 및 보조 마스터 설정
description: 이 절차는 허브에 대한 보조 마스터를 생성하고 해당 마스터를 사용하여 허브 보조 요금을 생성하는 방법을 보여줍니다.
author: Henrikan
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1480dec82912d547bde5db614703164e3f8451c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448885"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>허브 보조 요금 및 보조 마스터 설정

[!include [banner](../../includes/banner.md)]

이 절차는 허브에 대한 보조 마스터를 생성하고 해당 마스터를 사용하여 허브 보조 요금을 생성하는 방법을 보여줍니다. 절차는 USMF 데이터 세트를 사용합니다. 이 설정은 일반적으로 운송 조정자가 수행합니다.


## <a name="set-up-a-hub-master"></a>허브 마스터 설정
1. 운송 관리 > 설정 > 등급 > 보조 마스터로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 보조 마스터 필드에 값을 입력합니다.
4. 이름 필드에 값을 입력합니다.
5. 보조 유형 필드에서 '허브'를 선택합니다.
6. 저장을 클릭합니다.
7. 페이지를 닫습니다.

## <a name="set-up-a-hub-accessorial-charge"></a>허브 보조 요금 설정
1. 운송 관리 > 설정 > 등급 > 허브 보조 요금으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 허브 보조 ID 필드에 값을 입력합니다.
4. 허브 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
5. 목록에서 원하는 레코드를 찾아 선택합니다.
6. 허브 포지션 필드에서 옵션을 선택합니다.
    * 픽업 또는 하차로 요금을 생성할 수 있습니다. 선택에 따라 요금은 경로의 해당 운송 세그먼트에 적용됩니다.  
7. 보조 마스터 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
8. 목록에서 선택한 행의 링크를 클릭합니다.
    * 방금 만든 마스터를 선택합니다.  
9. 저장을 클릭합니다.
10. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]