---
title: 반년 감가상각 규칙 방법론
description: 이 항목에서는 자산의 사용 첫해와 마지막 해의 6개월 감가상각을 계산하는 반년 규칙으로 고정 자산이 감가상각을 계산하는 방법을 설명합니다.
author: moaamer
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 5e71beb316494d05a3d8ce6066f2a4c72e32a2ad3d75a4ba3560cb0aebfe4cc8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450499"
---
# <a name="half-year-depreciation-convention-methodology"></a>반년 감가상각 규칙 방법론

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

이 항목에서는 고정 자산에서 반년 규칙으로 감가상각을 계산하는 방법을 설명합니다. 반기 규칙은 자산의 사용 첫해와 마지막 해의 6개월 감가상각을 계산합니다. 감가상각에 규칙 대한 자세한 내용은 [감가상각 방법 및 규칙](Fixed-asset-depreciation-conventions.md)을 참조하세요. 

6개월 감가상각 규칙을 사용하는 경우 시스템은 자산을 취득한 연도 또는 사용 개시 연도를 사용하고 해당 연도에서 5년간의 감가상각을 계산한 다음 6개월을 추가합니다. 이 프로세스를 설명하기 위해 50,000달러에 취득하고 2020년 4월에 사용하기 시작한 자산을 예로 들어 보겠습니다. 또한 자산의 서비스 수명이 5년이라고 가정합니다.

최초 사용 연도는 2020년 12월에 종료되므로 자산의 5년 사용 수명은 2024년 12월에 종료됩니다. 반년 감가상각 규칙은 자산의 수명에 6개월을 추가하므로 서비스 수명은 2025년 6월에 종료됩니다. 

> 연간 감가상각 50,000/5 = 10,000 매월 감가상각 10,000/12 = 833.33 <br>
> 첫해 감가상각 10,000/2 = 5,000 및 후속 매월 감가상각 5,000/9 = 555.56

   [![반년 감가상각 규칙에 대한 감가상각 일정.](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)

반년 규칙으로 감가상각 기간을 연장하는 이유는 감가상각을 더 정확하게 할당하기 위한 것입니다. 6개월 규칙은 감가상각 비용을 더 균등하게 나타내므로 손익계산서를 보고하는 데 유용합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]