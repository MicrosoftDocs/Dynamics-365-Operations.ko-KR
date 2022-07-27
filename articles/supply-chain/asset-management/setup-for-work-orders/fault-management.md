---
title: 장애 관리
description: 자산 관리의 오류 관리에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 149d4fc8026a2a1878155d2b708cf3a79dd0e5af966db4e7f9339d8ca582da70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446617"
---
# <a name="fault-management"></a>장애 관리

[!include [banner](../../includes/banner.md)]

 

자산 관리에서 결함 디자이너를 사용하여 자산 유형에 대한 결함 증상, 결함 영역 및 결함 유형을 설정할 수 있습니다. 이러한 방식으로 자산에서 감지된 결함을 관리할 수 있습니다. 또한, 작업 주문에 고장원인 및 고장수리에 대한 제안사항을 등록할 수 있습니다.

장애 등록 및 관리 프로세스는 다음 단계로 구성됩니다.

1. 자산 유형에서 발생할 수 있는 결함 증상, 결함 영역 및 결함 유형 목록을 작성하세요.
2. 결함 디자이너에서 증상, 결함 영역 및 결함 유형을 설정합니다.

다음은 결함 증상, 결함 영역 및 결함 유형 간의 차이점을 이해하는 데 도움이 되는 몇 가지 예입니다.

**결함 증상:**

- 불평형 전압
- 단락
- 소음
- 누수
- 진동

**결함 영역:**

- 전기
- 기계
- 유압
- 영적

**결함 유형**

- 주 고정자 권선 결함
- 결함 다이오드
- 더티 와인딩
- 발전기 결함
- 센서 결함

## <a name="create-fault-symptoms"></a>장애 증상 생성

다음 단계에 따라 결함 설계자에서 사용할 수 있는 증상 목록을 작성하세요.

1. **자산 관리** \> **설정** \> **오류** \> **오류 증상** 을 선택합니다.
2. **새로 만들기** 를 선택하여 레코드를 만듭니다.
3. **오류 증상** 필드에 오류 증상의 이름을 입력합니다.
4. **설명** 필드에 설명을 입력합니다.
5. **저장** 을 선택합니다.

## <a name="create-fault-areas"></a>결함 영역 생성

다음 단계에 따라 결함 설계자에서 사용할 수 있는 영역 또는 위치 목록을 작성하세요.

1. **자산 관리** \> **설정** \> **결함** \> **결함 영역** 을 선택합니다.
2. **새로 만들기** 를 선택하여 레코드를 만듭니다.
3. **결함 영역** 필드에 결함 영역의 이름을 입력합니다.
4. **설명** 필드에 설명을 입력합니다.
5. **저장** 을 선택합니다.

## <a name="create-fault-types"></a>결함 유형 생성

다음 단계에 따라 오류 디자이너에서 사용할 수 있는 결함 유형 목록을 만듭니다.

1. **자산 관리** \> **설정** \> **결함** \> **결함 유형** 을 선택합니다.
2. **새로 만들기** 를 선택하여 레코드를 만듭니다.
3. **결함 유형** 필드에 결함 유형의 이름을 입력합니다.
4. **설명** 필드에 설명을 입력합니다.
5. **저장** 을 선택합니다.

## <a name="set-up-the-fault-designer"></a>결함 디자이너 설정

결함 디자이너에서 자산 유형에 대한 결함 데이터를 설정합니다.

1. **자산 관리** \> **설정** \> **결함** \> **결함 디자이너** 를 선택합니다.
2. 왼쪽 창에서 오류 레코드를 설정할 자산 유형을 선택합니다.
3. **결함 증상** 빠른 탭에서 **회선 추가** 를 선택한 다음 **오류 증상** 필드에서 오류 증상을 선택합니다.
4. **결함 영역** 빠른 탭에서 **회선 추가** 를 선택한 다음 오류 영역 필드에서 **결함 영역** 을 선택합니다.
5. **결함 유형** 빠른 탭에서 **회선 추가** 를 선택한 다음 **결함 유형** 필드에서 오류 증상을 선택합니다.
6. 선택한 자산 유형에 대한 모든 기존 결함 증상, 영역 및 유형의 조합을 빠르게 생성하려면 **결함 조합 생성** 을 선택합니다. 이 기능은 많은 결함 증상, 영역 및 유형을 추가한 경우에 유용합니다. 새 라인을 수동으로 생성하는 것보다 자산 유형과 관련이 없는 조합의 라인을 삭제하는 것이 더 쉽습니다.

    > [!NOTE]
    > 한 자산 유형에서 선택한 자산 유형으로 결함 증상, 영역 및 유형 설정을 복사하려면 **자산 유형에서 복사** 를 선택하세요.

7. **저장** 을 선택하여 변경 내용을 저장합니다.

![결함 디자이너 페이지.](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a>결함 원인 만들기

다음 단계에 따라 작업 주문 또는 유지 관리 요청에 추가할 수 있는 알려진 결함 원인 목록을 만드세요.

1. **자산 관리** \> **설정** \> **결함** \> **결함 사유** 를 선택합니다.
2. **새로 만들기** 를 선택하여 레코드를 만듭니다.
3. **결함 원인** 필드에 결함 원인의 이름을 입력합니다.
4. **설명** 필드에 설명을 입력합니다.
5. **저장** 을 선택합니다.

## <a name="create-fault-remedies"></a>결함 수정 생성

작업 주문 또는 유지 관리 요청에 추가할 수 있는 수정 및 수리 제안 목록을 작성하려면 다음 단계를 따르세요.

1. **자산 관리** \> **설정** \> **결함** \> **결함 수정** 을 선택합니다.
2. **새로 만들기** 를 선택하여 레코드를 만듭니다.
3. **결함 수정** 필드에 결함 수정의 이름을 입력합니다.
4. **설명** 필드에 설명을 입력합니다.
5. **저장** 을 선택합니다.

> [!NOTE]
> 필요에 따라 장애 증상, 영역, 유형, 원인 및 해결 방법의 이름을 변경할 수 있습니다. 이름 변경은 관련 오류 등록에 자동으로 반영됩니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]