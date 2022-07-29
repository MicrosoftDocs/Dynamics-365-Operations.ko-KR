---
title: Power BI 콘텐츠 학습
description: 이 토픽에서는 Power BI 콘텐츠 학습에 대해 설명합니다.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6236868dca26be8cf54ad3cf73e846f2e689af8635e212c493b65a5d1aaa62ed
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460656"
---
# <a name="learning-power-bi-content"></a>Power BI 콘텐츠 학습

[!include [banner](../includes/banner.md)]

이 토픽에서는 Microsoft Power BI 콘텐츠 **학습** 에 대해 설명합니다.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 보고서

Power BI 콘텐츠 **학습** 에 포함된 보고서에는 추가 정보가 포함된 차트와 테이블이 모두 있습니다. 다음 테이블에서는 보고서를 설명합니다.

| 보고서                | 콘텐츠 |
|-----------------------|----------|
| 학습 개요     | 기타 보고서 요약 |
| 과정 분석       | 지역별 등록, 신분별 수강인원, 기업별 유형별 수강신청, 직무별 수강신청 |
| 등록 분석 | 등록 목록 |
| 과정 유형          | 기술별 과정 유형 |
| 강사 분석   | 강사 대비 강의 비율, 강사 수, 강사별 강좌, 강사 1인당 강좌, 강사별 강좌 일정 |
| 제공되는 과정       | 과정 목록 |
| 과정 디자인        | 과정 의제 |

이러한 보고서에서 차트와 타일을 필터링하고 대시보드에 차트와 타일을 고정할 수 있습니다. Power BI 필터링 및 고정 방법에 대한 자세한 내용은 [대시보드 생성 및 구성](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)을 참조하십시오.

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해

다음 데이터는 Power BI 콘텐츠 **학습** 에서 보고서를 작성하는 데 사용됩니다. 이 표는 콘텐츠의 기반이 된 엔터티를 보여줍니다.

| 엔터티           | 콘텐츠                                                         | 다른 엔티티와의 관계 |
|------------------|------------------------------------------------------------------|-----------------------------------|
| 캘린더 오프셋  | 슬라이스 보고서에 대한 캘린더 오프셋                                | 과정 의제, 과정 참석자 |
| 회사          | 보고서를 필터링할 회사                                   | 과정 의제, 과정 참석자 |
| 과정           | 과정, 설명, 강사 이름, 위치, 강의실 및 상태 | 과정 의제, 과정 참석자, 과정 기술 |
| 과정 의제    | 의제, 과정, 시작 및 종료 시간                          | 회사, 캘린더 오프셋, 날짜, 과정 |
| 과정 참석자 | 이름, 신분, 직업, 등록일                         | 회사, 달력 오프셋, 날짜, 코스, 인구 통계, 고용, 코스, 직원 이름, 직원 직위, 직무, 직위 |
| 코스 스킬     | 스킬, 스킬 종류, 레벨                                     | 과정 |
| 날짜             | 일, 주, 월 및 년                                   | 과정 의제, 과정 참석자 |
| 인구통계     | 생년월일, 성별, 출신 민족 및 결혼 여부         | 과정 의제, 과정 참석자 |
| 고용       | 시작 날짜, 종료 날짜 및 전환 날짜                        | 과정 의제, 과정 참석자 |
| 직무              | 함수, 유형 및 제목                                        | 과정 의제, 과정 참석자 |
| 직위         | 직위, 직위 및 FTE(정규직)                  | 과정 의제, 과정 참석자 |
| 직원 이름    | 이름, 성 및 전체 이름                             | 과정 참석자 |
| 직원 직위   | 직위 및 연공서열 날짜                                         | 과정 참석자 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]