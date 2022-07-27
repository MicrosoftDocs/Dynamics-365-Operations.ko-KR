---
title: 전자 보고 샘플 공급업체 확인
description: 이 항목에서는 전자 보고 샘플 확인 형식을 사용하는 방법에 대한 일반 정보를 제공합니다.
author: sunfzam
ms.date: 06/14/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 2e1aa349b505713d0502aa90ddd5c3caff1f083c
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451021"
---
# <a name="electronic-reporting-sample-vendor-checks"></a>전자 보고 샘플 공급업체 확인

[!include [banner](../includes/banner.md)]

전자 보고(ER)를 사용하여 공급업체 수표의 형식을 지정할 수 있습니다. 많은 은행별 및 수표 제공업체별 수표 형식을 시중에서 구할 수 있습니다. 샘플 수표 형식은 ER 도구 저장소의 지불 수표 모델에 포함되었습니다. 이러한 검체 검사에는 **Check in the middle (US)** 및 **Check on top stub below (US)** 라는 레이블이 있습니다.

## <a name="what-check-formats-are-currently-supported"></a>현재 지원되는 수표 형식은 무엇입니까?

항상 LCS(Microsoft Dynamics Lifecycle Services)의 공유 자산 라이브러리로 이동하여 자산 유형의 **GER 구성** 을 가진 사용 가능한 파일의 현재 목록을 확인해야 합니다. 다음 섹션인 "무엇을 설정해야 합니까?"에는 사용 가능한 구성을 검토하고 선택한 구성을 가져올 수 있도록 LCS 리포지토리를 만드는 방법을 설명하는 항목에 대한 링크가 포함되어 있습니다.

Microsoft Dynamics 365 Finance 수표가 맨 위에 있고 두 개의 송금 섹션이 뒤따르는 샘플 형식이 포함됩니다. 또한 두 개의 송금 섹션 사이에 수표가 중간에 있는 샘플 형식도 포함됩니다. 이 샘플 형식은 Deluxe 비즈니스 수표 형식에 해당합니다.

## <a name="what-do-i-have-to-set-up"></a>무엇을 설정해야 하나요?

- ER을 사용하여 수표를 인쇄하려면 먼저 하나 이상의 활성 수표 구성을 ER 구성으로 가져와야 합니다. 이에 대한 지침은 [Lifecycle Services에서 전자 보고 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)를 참조하세요.
- 은행 계정에 대한 현금 및 은행 관리 검사를 구성할 때 **일반 전자 내보내기 형식** 확인란을 선택한 다음 적절한 확인 형식을 내보내기 형식 구성으로 선택합니다.
- 또한 수탁에 인쇄될 슬립 라인의 수를 지정해야 합니다. 이 숫자를 계산할 때 머리글 행을 포함해야 합니다. 두 가지 샘플 수표 형식의 경우 권장되는 슬립 라인 수는 17입니다. 그러나 이 숫자는 수표 재고 및 프린터 드라이버에 따라 다릅니다.
- 수표 레이아웃을 확인하려면 테스트 수표를 인쇄하는 것이 좋습니다. 테스트 검사를 인쇄하려면 **테스트 인쇄** 옵션을 선택합니다. 샘플 수표 형식은 Microsoft Excel의 고급 프린터 속성에서 **여백** 이 **없음** 으로 설정되어 있을 때 가장 잘 작동합니다. 테스트 수표가 생성된 후 Excel 출력 편집을 활성화하고 모든 여백이 **0**(영)으로 설정되도록 페이지 레이아웃을 구성합니다. 수표의 테스트 사본을 수표 스톡과 비교하고 정렬에 만족할 때까지 설정을 조정합니다.
- 지급 분개에서 구성된 은행 계좌에 대한 지급을 생성할 때 지정된 형식을 사용하여 수표가 인쇄됩니다.

자세한 내용은 [전자 보고 형식 수정](../../fin-ops-core/dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template.md)을 참조하십시오.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
