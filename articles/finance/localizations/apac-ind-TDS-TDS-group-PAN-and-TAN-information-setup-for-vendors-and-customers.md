---
title: 공급업체 및 고객에 대한 TDS 그룹, PAN 및 TAN 정보 설정
description: 이 토픽에서는 공급업체 및 고객에 대한 원천공제세(TDS) 그룹, 영구 계정 번호(PAN) 및 세금 계정 번호(TAN)에 대한 정보를 설정하는 방법에 대해 설명합니다.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 808fa7b72651ab274415e48f5e0a356784ca6525
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451780"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a>공급업체 및 고객에 대한 TDS 그룹, PAN 및 TAN 정보 설정

[!include [banner](../includes/banner.md)]

이 토픽에서는 공급업체 및 고객에 대한 원천공제세(TDS) 그룹, 영구 계정 번호(PAN) 및 세금 계정 번호(TAN)에 대한 정보를 설정하는 방법에 대해 설명합니다.

1. **지급 계정 \> 공급업체 \> 모든 공급업체** 또는 **지급 계정 \> 고객 \> 모든 고객** 으로 이동합니다.

    [![모든 공급업체 페이지.](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)

2. 작업 창에서 **새로 만들기** 를 선택하여 공급업체 또는 고객을 만들고 필요한 세부 정보를 입력합니다. 또는 기존 공급업체 또는 고객을 선택합니다.
3. **송장 및 전달** 빠른 탭의 **원천징수세** 섹션에서 공급업체 또는 고객에 대한 원천징수세, TDS 또는 원천징수액(TCS)을 계산하려면 **원천징수세 계산** 옵션을 **예** 로 설정합니다.
4. 구매 송장에 대한 TDS는 공급업체 또는 고객에 대해 정의된 기본 TDS 그룹을 기반으로 계산됩니다. **TDS 그룹** 필드에서 기본 TDS 그룹을 선택합니다.

    > [!NOTE]
    > **TDS 그룹** 필드에서 TDS 그룹을 선택하면 **원천징수세 그룹** 및 **TCS 그룹** 필드를 사용할 수 없게 됩니다.

5. **세금 정보** 빠른 탭의 **PAN 정보** 섹션, **상태** 필드에서 공급업체 또는 고객의 영구 계정 번호 상태를 선택합니다.

    - **사용할 수 없음** – 공급업체 또는 고객에게 PAN이 없습니다.
    - **받았음** – 공급업체 또는 고객에게 PAN이 있습니다.
    - **신청함** – 공급업체 또는 고객이 PAN을 신청했습니다.
    - **유효하지 않은** – 공급업체 또는 고객에게 PAN이 있지만 유효하지 않습니다.

6. **상태** 필드에서 **받았음** 을 선택한 경우 공급업체 또는 고객에게 PAN이 있음을 나타내기 위해 **번호** 필드에 PAN을 입력합니다. PAN은 5개의 알파벳 문자, 4개의 숫자, 1개의 알파벳 문자로 구성되어야 합니다. 다음은 예입니다: **ABCDE1260A**.
7. **상태** 필드에서 **신정함** 을 선택한 경우 공급업체 또는 고객이 PAN을 신청했음 나타내기 위해 **참조 번호** 필드에 참조 번호를 입력합니다.
8. **피납세자 특성** 필드에서 공급업체 또는 고객이 속한 피납세자 범주의 특성을 선택합니다.

    - 회사
    - HUF
    - 기업
    - 개인
    - AOP
    - BOI
    - 현지 기관
    - 기타

    [![세금 정보 빠른 탭.](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)

9. 작업 창의 **공급업체** 탭에 있는 **등록** 그룹에서 **등록 ID** 를 선택하여 **주소 관리** 페이지를 엽니다.
10. **주소 관리** 페이지의 **세금 정보** 빠른 탭에서 **추가** 또는 **편집** 을 선택하여 **세금 정보 관리** 페이지를 엽니다. 여기서 세금 등록 항목을 유지할 수 있습니다.
11. **세금 정보 관리** 페이지의 **원천징수세** 빠른 탭의 **세금 계정 번호(TAN)** 필드에 TAN을 입력합니다. TAN은 4개의 알파벳 문자, 5개의 숫자, 1개의 알파벳 문자로 구성되어야 합니다. 다음은 예입니다: **AFGH54821T**.
12. 페이지를 닫습니다.
