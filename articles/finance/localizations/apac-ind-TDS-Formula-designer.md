---
title: TDS 계산을 위한 공식 디자이너
description: 이 토픽에서는 거래에 연결된 TDS 그룹의 각 TDS 세금 코드에 대해 정의된 공식을 기반으로 TDS(원천에서 공제된 세금)를 계산하는 방법의 예를 제공합니다.
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
ms.openlocfilehash: 3d8e098243688ebf6977db97130592443e269973
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451825"
---
# <a name="formula-designer-for-tds-calculations"></a>TDS 계산을 위한 공식 디자이너

[!include [banner](../includes/banner.md)]

이 토픽에서는 각 TDS 세금 코드에 대해 정의된 공식을 기반으로 원천 공제 세금(TDS)이 계산되는 방법의 예를 제공합니다. TDS 세금 코드는 거래에 연결된 TDS 그룹에서 정의됩니다. TDS 공식을 설계하기 전에 다음 단계에 나열된 대로 TDS에 필요한 기본 설정을 완료합니다. 

- **원천징수세 구성 요소 그룹** 페이지를 사용하여 TDS 구성 요소 그룹을 설정합니다. 
- **원천징수세 구성 요소** 페이지를 사용하여 TDS 구성 요소를 설정하고 TDS 구성 요소 그룹을 TDS 구성 요소에 첨부합니다. 
- **원천징수세 코드** 페이지를 사용하여 TDS 세금 코드를 설정하고 TDS 구성요소를 세금 코드에 첨부합니다. 
- **원천징수세 그룹** 페이지를 사용하여 TDS 세금 그룹을 설정합니다. 그런 다음 TDS 세금 코드를 세금 그룹에 첨부하고 **수식 디자이너** 페이지를 사용하여 공식을 정의합니다. 

**수식 예**

이 예에서 TDS 그룹 Rent는 공급업체 A에 대해 생성된 구매 송장에 연결됩니다. 송장 금액은 $100,000입니다. 송장에 대한 TDS 계산을 보려면 다음 표를 참조하세요.

| TDS 그룹                                                   | TDS 그룹에 첨부된 TDS 세금 코드 | 값              | 과세 기준(수식 디자이너) | 계산식(수식 디자이너) | 기본 금액 | 계산된 TDS 금액 |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| 임대료                                                         | TDS(TDS 구성요소-TDS)                | 10%                | 총액                      |                                            | 100,000      | 10,000                 |
| 추가 요금(TDS 구성 요소-추가 요금)                         | 10%                                     | 제외 총액 | +TDS                              |                   10000                    | 1,000        |                       |
| PE-Cess(TDS 구성 요소-PE-Cess)                            | 2%                                      | 제외 총액 | +TDS+할증료                    |                   11000                    | 220         |                       |
| SHE Cess(TDS 구성요소 - SHE Cess)                          | 1%                                      | 제외 총액 | +TDS+할증료                    |                   11000                    | 110         |                       |
| **송장에** **대해** **계산****된** **총** **TDS** | **11,330**                               |                    |                                   |                                            |             |                       |

바우처 항목은 다음과 같이 생성됩니다.

| 거래처           | 차변  | 대변 |
| ----------------- | ------ | ------ |
| 임대료              | 100,000 |        |
| 공급업체 A          |        | 100,000 |
| 공급업체 A          | 11,330  |        |
| TDS 지불       |        | 10,000  |
| 추가 요금 지불 |        | 1,000   |
| PE-Cess 지불   |        | 220    |
| SHE Cess 지불  |        | 110    |
