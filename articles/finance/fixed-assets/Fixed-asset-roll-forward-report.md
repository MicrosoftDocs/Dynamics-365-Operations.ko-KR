---
title: 고정 자산 롤포워드 보고서
description: 이 항목에서는 고정 자산 롤포워드 보고서를 사용하는 방법을 설명합니다.
author: moaamer
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2017-12-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: b0c0c8b1a33041e266ce266dc79b29c8a7dbfa14
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451249"
---
# <a name="fixed-assets-roll-forward-report"></a>고정 자산 롤포워드 보고서

[!include [banner](../includes/banner.md)]

**고정 자산 롤포워드** 보고서는 읽기 쉬운 Microsoft Excel 형식으로 기간 마감, 재무제표 및 세금 보고에 필요한 자세한 고정 자산 데이터를 제공합니다. 이 보고서에는 고정 자산의 개시 및 마감 잔액, 해당 기간의 평가 변동, 해당 기간의 모든 신규 자산 취득 및 처분이 포함됩니다. 개별 고정 자산에 대한 데이터가 보고되고 고정 자산 그룹과 법인에 대한 값도 요약됩니다.

**고정 자산 롤포워드** 보고서에는 전자 보고(ER) 프레임워크가 사용됩니다. 보고서를 실행하기 전에 Microsoft Dynamics Lifecycle Services(LCS)에서 고정 자산 모델 및 고정 자산 롤포워드 구성을 가져와야 합니다. 이에 대한 지침은 [Lifecycle Services에서 전자 보고 구성 다운로드](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)를 참조하세요.

이 보고서는 Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 또는 Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition(2017년 7월)의 핫픽스로 제공됩니다. 2017년 7월 릴리스가 있는 환경에는 세 가지 핫픽스를 적용해야 합니다.

- **KB 4041754:** 플랫폼 업데이트 패키지 적용 후 현재 버전에 적용되지 않아 LCS에서 전자 보고(ER) 구성을 다운로드할 수 없음
- **KB 4056107:** 전자 보고(ER) 누적 업데이트 5
- **KB 4056353:** 고정 자산 명세서 및 메모 보고서가 GAAP 및 IFRS의 요구 사항을 충족하지 않음

다음 표에서는 각 보고서에 사용할 수 있는 필드에 관해 설명합니다.


|                    필드                    |                                                                                                                                설명                                                                                                                                |
|---------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              잔액: 개시              |                                                                                           보고서에 지정된 "시작" 날짜 기준의 고정 자산 순 장부가액.                                                                                           |
|              잔액: 마감              |                                                                                            보고서에 지정된 "종료" 날짜 기준의 고정 자산 순 장부가액.                                                                                            |
|         취득: 개시 가치         |                                                 보고서에 지정된 "시작" 날짜까지 <strong>취득</strong> 및 <strong>취득 조정</strong> 유형의 모든 거래 합계.                                                  |
|      취득: 기간 취득      |                                                 보고서의 날짜 범위 동안 게시된 <strong>취득</strong> 및 <strong>취득 조정</strong> 유형의 모든 거래 합계.                                                  |
|       취득: 기간 처분        |                                                                        보고서 날짜 범위 동안 처분 거래가 있는 게시된 모든 취득 취소의 합계.                                                                        |
|         취득: 마감 가치         |                                                  보고서에 지정된 "종료" 날짜까지 <strong>취득</strong> 및 <strong>취득 조정</strong> 유형의 모든 거래 합계.                                                   |
|        감가상각: 개시 가치         | 보고서에 지정된 "시작" 날짜까지 <strong>감가상각</strong>, <strong>감가상각 조정</strong>, <strong>특수 감가상각 허용값</strong> 및 <strong>특별 감가상각</strong> 유형의 모든 거래 합계. |
|     감가상각: 기간 감가상각     |                         보고서의 날짜 범위 동안 게시된 <strong>감가상각</strong>, <strong>감가상각 조정</strong> 및 <strong>특별 감가상각</strong> 유형의 모든 거래 합계.                          |
| 감가상각: 기간 특수 감가상각 |                                                              보고서의 날짜 범위 동안 게시된 <strong>특수 감가상각 허용값</strong> 유형의 모든 거래 합계.                                                               |
|       감가상각: 기간 처분       |                                                                       보고서 날짜 범위 동안 처분 거래가 있는 게시된 모든 감가상각 취소의 합계.                                                                        |
|        감가상각: 마감 가치         |  보고서에 지정된 "종료" 날짜까지 <strong>감가상각</strong>, <strong>감가상각 조정</strong>, <strong>특수 감가상각 허용값</strong> 및 <strong>특별 감가상각</strong> 유형의 모든 거래 합계.  |
|    상향/하향: 개시 가치     |                              보고서에 지정된 "시작" 날짜까지 <strong>상향 조정</strong>, <strong>하향 조정</strong> 및 <strong>재평가</strong> 유형의 모든 거래 합계.                               |
|   상향/하향: 기간 상향   |                                                                    보고서의 날짜 범위 동안 게시된 <strong>상향 조정</strong> 유형의 모든 거래 합계.                                                                    |
|  상향/하향: 기간 하향  |                                                                   보고서의 날짜 범위 동안 게시된 <strong>하향 조정</strong> 유형의 모든 거래 합계.                                                                   |
| 상향/하향: 기간 재평가  |                                                                        보고서의 날짜 범위 동안 게시된 <strong>재평가</strong> 유형의 모든 거래 합계.                                                                        |
|   상향/하향: 기간 처분   |                                                           보고서 날짜 범위 동안 처분 거래가 있는 게시된 모든 상향, 하향 및 재평가 취소의 합계.                                                           |
|    상향/하향: 마감 가치     |                               보고서에 지정된 "종료" 날짜까지 <strong>상향 조정</strong>, <strong>하향 조정</strong> 및 <strong>재평가</strong> 유형의 모든 거래 합계.                                |
|          처분: 처분 날짜           |                                                                                                                고정 자산 장부의 처분 날짜.                                                                                                                |
|    처분: 처분 시 순 장부가액    |                                                                                                    처분 당시 고정 자산 장부의 순 장부가액.                                                                                                    |
|            처분: 판매 가치            |                                                                                               고정 자산 장부에서 처분 – 판매 거래의 판매 가치.                                                                                                |
|           처분: 폐기 가치            |                                                                                               고정 자산 장부에서 처분 – 폐기 거래의 폐기 가치.                                                                                               |
|           처분 : 손익            |                                                                                 고정 자산 장부에서 처분 거래의 일부로 계산되는 손익 가치.                                                                                 |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
