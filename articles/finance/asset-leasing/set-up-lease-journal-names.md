---
title: 임대 분개장 이름 설정
description: 이 항목에서는 임대 분개장 이름을 정의하는 방법에 대해 설명합니다. 임대 분개장 이름은 자산 임대에서 시작된 항목이 게시되는 분개장을 지정합니다.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b9d8136ae4f960a586b9526751fc8bf6e7675c8d
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451273"
---
# <a name="set-up-lease-journal-names"></a>임대 분개장 이름 설정

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


임대 분개장 이름은 자산 임대 트랜잭션을 게시할 분개장을 지정합니다. **자산 임대** 분개장 유형에 할당된 분개장 이름만 **자산 임대 매개 변수** 페이지의 **초기 인식**, **월간 분개장 이름** 필드에 표시됩니다. **공급업체 송장 기록** 분개장 유형만 **송장 분개장 이름** 필드에 할당할 수 있습니다.

시스템은 트랜잭션과 일정 간의 차이를 방지하기 위해 특정 재무 필드를 편집하지 못하도록 잠급니다. 잠긴 필드에는 **계정**, **금액,** **재무 차원**, **통화**, **트랜잭션 유형** 입니다. 또한, 일정과 거래 간에 차이가 발생할 수 있으므로 자산 임대 분개에 분개 라인을 추가하거나 삭제할 수 없습니다.


임대 저널 이름을 구성하려면 다음 단계를 완료하십시오.

1. **자산 임대 \> 설정 \> 자산 임대 매개 변수** 로 이동합니다.
2. **일반** 탭의 **초기 인식 분개장 이름** 필드에서 분개장을 선택하십시오. 모든 초기 인식 분개장 항목이 이 분개장 이름에 게시됩니다.
3. **송장 분개장 이름** 필드에서 분개장을 선택합니다. 임대 장부에 대해 **공급업체 결제** 옵션을 **예** 로 설정하면 임대, 비용 결제 송장이 이 분개장 이름에 게시됩니다.
4. **임대 분개장 이름** 필드에서 분개장을 선택합니다. 모든 감가상각, 이자 및 단기 재분류 항목은 이 분개 이름에 게시됩니다. 임대 기록에 대해 **공급업체 결제** 옵션을 **아니요** 로 설정하면 임대료, 비용 결제 항목도 이 분개장 이름에 게시됩니다.
5. **임대 수정 분개장 이름** 필드에서 분개장을 선택합니다. 임대 조정, 해지, 손상 트랜잭션이 이 분개장 이름에 게시됩니다. 선택한 분개장 이름에는 워크플로 또는 승인이 할당되어 있지 않아야 합니다. 임대 수정 분개장 이름이 정의되지 않은 경우 **임대 분개장 이름** 필드에서 선택한 분개장 이름에 임대 조정, 해지, 손상 트랜잭션이 게시됩니다. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
