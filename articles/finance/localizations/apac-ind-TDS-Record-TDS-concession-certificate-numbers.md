---
title: TDS 허가증 번호 기록
description: 이 토픽에서는 공급업체에 발급된 원천 공제 세금(TDS) 할인 증명서 번호를 기록하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: d83379b0377bdbb848158f83f1f3229e09323602
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451783"
---
# <a name="record-tds-concession-certificate-numbers"></a>TDS 허가증 번호 기록

[!include [banner](../includes/banner.md)]

이 토픽에서는 공급업체에 발급된 원천 공제 세금(TDS) 할인 증명서 번호를 기록하는 방법에 대해 설명합니다.

1. **세금 \> 간접세 \> 원천징수세 \> 원천징수세 허가** 로 이동합니다.
2. **세금 유형** 필드에서 **TDS** 를 선택하여 TDS 세금 유형에 대한 할인 증명서를 기록합니다.
3. **개요** 탭에서 **Alt+N** 을 선택하여 선을 만듭니다.

    [![새 줄의 헤더입니다.](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)

4. **원천징수세 코드** 필드에서 공급업체 할인 증명서가 발급되는 TDS 세금 코드를 선택합니다. **원천징수세 코드 이름** 필드에는 TDS 세금 코드의 이름이 표시됩니다.
5. **시작 날짜** 및 **종료 날짜** 필드에서 TDS 세금 코드를 사용하여 할인 기준으로 공급업체의 TDS를 계산하는 할인 증명서의 유효 기간을 정의합니다.
6. **비고** 필드에 비고를 입력합니다.
7. **섹션** 필드에 TDS 허가 인증서를 사용할 수 있는 법적 섹션 코드를 입력합니다.

    섹션 코드가 197인 경우 양식 26Q의 "비공제/더 낮은 공제 사유" 열과 양식 27Q의 "비공제/더 낮은 공제/총액 가산(있는 경우) 사유" 열 모두에 값 "A"가 나타납니다. 섹션 코드가 197A인 경우 "B" 값이 두 위치에 모두 나타납니다.

8. 공급업체에 대한 TDS 허가 인증서 번호를 기록하려면 **인증서** 빠른 탭을 선택합니다.
9. **공급업체 계정** 필드에서 TDS 할인 인증서가 발급되는 공급업체 계정을 선택합니다.
10. **시작 날짜** 및 **종료 날짜** 필드에서 TDS 허가 인증서의 유효 기간을 정의합니다.

    양허 기반의 TDS 계산은 공급업체에 대해 인증서가 생성된 기간을 기준으로 합니다.

11. **인증서** 필드에 TDS 허가 인증서 번호를 입력합니다.

    [![인증서 빠른 탭.](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)

12. 페이지를 닫습니다
