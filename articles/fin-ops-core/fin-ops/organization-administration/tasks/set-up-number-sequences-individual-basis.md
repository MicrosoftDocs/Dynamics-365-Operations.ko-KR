---
title: 개별적으로 번호 시퀀스 설정
description: 이 항목에서는 개별적으로 번호 시퀀스를 설정하는 방법에 대해 설명합니다.
author: SunilGarg
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b95a639c593c0f126a9aa1dd50434838d09ef746
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "8460626"
---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>개별적으로 번호 시퀀스 설정

[!include [banner](../../includes/banner.md)]

이 항목에서는 개별적으로 번호 시퀀스를 설정하는 방법에 대해 설명합니다. 번호 시퀀스는 필요한 마스터 데이터 레코드 및 트랜잭션 레코드에 대해 읽을 수 있는 고유 식별자를 생성하는 데 사용됩니다. 식별자가 필요한 마스터 데이터 또는 트랜잭션 레코드를 참조라고 합니다. 참조에 대한 새 레코드를 생성하려면 먼저 번호 시퀀스를 설정하고 참조와 연결해야 합니다. **숫자 시퀀스 설정** 마법사를 사용하여 필요한 모든 번호 시퀀스를 동시에 설정하거나 **숫자 시퀀스** 페이지를 사용하여 개별 번호 시퀀스를 생성하거나 수정할 수 있습니다.

1. **탐색 창 > 모듈 > 조직 관리 > 번호 시퀀스 > 번호 시퀀스** 로 이동합니다.
2. **숫자 시퀀스** 를 선택합니다.
3. **숫자 시퀀스 코드** 필드에 값을 입력합니다.
4. **이름** 필드에 값을 입력합니다.
5. **범위 매개 변수** 빠른 탭에서 숫자 시퀀스의 범위를 선택하고 드롭다운 목록에서 범위 값을 선택합니다. 범위는 번호 시퀀스를 사용하는 조직을 정의합니다. 또한 **공유** 와 범위가 다른 번호 시퀀스는 범위에 해당하는 세그먼트를 포함할 수 있습니다. 예를 들어 **법인** 범위의 숫자 시퀀스는 법인 세그먼트를 가질 수 있습니다. 범위에 대한 자세한 내용은 [번호 시퀀스 개요](../number-sequence-overview.md)를 참조하세요. 
6. **세그먼트** 섹션을 펼칩니다.
    - 세그먼트를 추가, 제거 및 재정렬하여 숫자 시퀀스의 형식을 정의합니다.  
    - 모든 범위의 숫자 시퀀스는 *상수 세그먼트* 및 *영숫자 세그먼트* 를 포함할 수 있습니다. 상수 세그먼트에는 변경되지 않는 일련의 영숫자 문자가 포함됩니다. 이 세그먼트 유형을 사용하여 숫자 시퀀스 세그먼트 사이에 하이픈이나 기타 구분 기호를 추가합니다. 영숫자 세그먼트에는 숫자 기호(#)와 앰퍼샌드(&)의 조합이 포함됩니다. 이 문자는 시퀀스의 숫자가 사용될 때마다 증가하는 문자와 숫자를 나타냅니다. 숫자 기호(#)를 사용하여 증가하는 숫자를 나타내고 앰퍼샌드(&)는 증가하는 문자를 나타냅니다. 예를 들어 형식 `#####_2014`는 시퀀스 `00001_2014`, `00002_2014` 등을 만듭니다. 하나 이상의 영숫자 세그먼트가 있어야 합니다. 회사 또는 법인과 같은 범위 세그먼트는 필요하지 않습니다. 그러나 형식에 범위 세그먼트를 포함하지 않으면 선택한 참조에 대한 숫자가 여전히 범위별로 생성됩니다.  
7. **참조** 섹션을 펼칩니다. 이 번호 시퀀스를 할당할 문서 유형 또는 레코드를 선택합니다. 이 단계는 특수 응용 프로그램 사용 패턴에 대해 정의된 시퀀스의 경우 선택 사항입니다. 이러한 시나리오에서는 참조를 사용하지 않고 번호 시퀀스 코드 또는 ID 값을 사용하여 새 번호가 생성됩니다. 특별한 애플리케이션 사용 패턴의 예로는 특정 저널 이름에 사용되는 바우처 시리즈가 있습니다. 그러나 이러한 패턴은 사용하지 않는 것이 좋습니다.  
8. **일반** 섹션을 확장합니다. 일반 빠른 탭에서 숫자 시퀀스가 수동인지 연속인지 비연속인지 지정합니다. 또한, 일련번호에 사용할 수 있는 가장 낮은 숫자와 가장 높은 숫자를 입력합니다. 비연속 번호 시퀀스를 연속 번호 시퀀스로 변경하지 않는 것이 좋습니다. 숫자 시퀀스는 실제로 연속적이지 않습니다. 이 변경으로 인해 데이터베이스에서 중복 키 위반이 발생할 수도 있습니다. 또한 연속 숫자 시퀀스는 성능에 더 큰 영향을 미칩니다.   
9. **저장** 을 클릭합니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]