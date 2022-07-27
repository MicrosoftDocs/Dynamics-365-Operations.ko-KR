---
title: 리소스 기능 정의
description: 리소스 기능은 리소스가 수행할 수 있는 작업을 설명합니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42451da0bd465ce3a18ecf18570f3331847474c1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449179"
---
# <a name="define-resource-capabilities"></a>리소스 기능 정의

[!include [banner](../../includes/banner.md)]

리소스 기능은 리소스가 수행할 수 있는 작업을 설명합니다. 일정을 잡는 동안 각 작업 및 작업의 요구 사항은 사용 가능한 리소스의 기능과 일치합니다. 이 작업 가이드는 리소스 기능을 만들고 리소스에 할당하는 데 도움이 됩니다. 이 작업을 만드는 데 사용된 데모 데이터 회사는 USMF입니다.


## <a name="create-a-resource-capability"></a>리소스 기능 생성
1. 리소스 기능으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 기능 필드에 리소스 기능의 ID를 입력합니다.
    * 지정된 작업에 대해 기능 ID를 사용하여 리소스에 작업을 수행하기 위해 이 기능이 있어야 함을 지정합니다.  
4. 설명 필드에 기능에 대한 설명을 입력합니다.

## <a name="assign-capability-to-a-resource"></a>리소스에 기능 할당
1. 추가를 클릭합니다.
2. 리소스 필드에 리소스 ID를 입력합니다.
    * 리소스 기능은 하나 이상의 리소스에 할당될 수 있습니다.  
3. 만료 필드에 날짜를 입력합니다.
    * 이 필드를 사용하여 리소스가 제한된 시간 동안만 기능을 갖도록 지정할 수 있습니다.  
4. 우선 순위 필드에 숫자를 입력합니다.
    * 작업 및 작업을 예약할 때 우선 순위에 따라 리소스를 선택할지 여부를 지정할 수 있습니다. 이 작업을 수행하도록 선택하고 요청 날짜까지 둘 이상의 자원이 작업 또는 작업을 수행할 수 있는 경우 필요한 기능과 관련하여 가장 낮은 우선 순위를 갖는 자원이 선택됩니다.  
5. 수준 필드에 숫자를 입력합니다.
    * 작업이나 작업에 특정 기능이 필요하다고 지정할 때 필요한 최소 수준도 지정할 수 있습니다. 기능 수준을 사용하여 동일한 작업을 수행할 수 있지만 속도, 강점, 크기 등이 다른 리소스를 구별합니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]