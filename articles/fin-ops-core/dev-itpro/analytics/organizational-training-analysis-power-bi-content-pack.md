---
title: 조직 교육 Power BI 콘텐츠
description: 이 항목에서는 재무 및 운영 - 조직 교육 Power BI 콘텐츠에 대해 설명합니다.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cd48c12ea3ea31904c437f678888a51e5381cfcfbeef0e1c709858b0c6cb857d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460892"
---
# <a name="organizational-training-power-bi-content"></a>조직 교육 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 항목에서는 재무 및 운영 - 조직 교육 Power BI 콘텐츠에 대해 설명합니다.

## <a name="reports-that-are-included-in-the-content-pack"></a>콘텐츠 팩에 포함된 보고서
콘텐츠 팩을 데이터에 연결하면 보고서에 조직의 데이터가 표시됩니다. 이전에 Microsoft Power BI 사용한 적이 없다면 [Power BI에 대한 안내 학습](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData) 페이지에서 자세히 알아볼 수 있습니다. 콘텐츠 팩에 포함된 보고서에는 추가 정보가 포함된 차트와 테이블이 모두 있습니다. 다음 테이블에서는 보고서를 설명합니다.

| 보고서          | 콘텐츠                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| 과정 분석 | 위치별 등록, 상태별 수강자, 등록리스트 |
| 과정 유형    | 기술별 과정 유형                                                       |

이러한 보고서에서 차트와 타일을 필터링하고 대시보드에 차트와 타일을 고정할 수 있습니다. Power BI 필터링 및 고정 방법에 대한 자세한 내용은 [대시보드 생성 및 구성](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)을 참조하십시오.

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해
애플리케이션 데이터는 조직 교육 콘텐츠 팩의 보고서를 채우는 데 사용됩니다. 다음 표에서는 콘텐츠 팩의 기반이 되는 엔터티를 보여 줍니다.

| 엔터티                    | 콘텐츠                                                         | 다른 엔티티와의 관계 |
|---------------------------|------------------------------------------------------------------|-----------------------------------|
| 학습\_CalendarOffset  | 슬라이스 보고서에 대한 캘린더 오프셋                                | 학습\_CourseAgenda, 학습\_CourseAttendees |
| 학습\_회사         | 보고서를 필터링할 회사                                   | 학습\_CourseAgenda, 학습\_CourseAttendees |
| 학습\_과정          | 과정, 설명, 강사 이름, 위치, 강의실 및 상태 | 학습\_CourseAgenda, 학습\_CourseAttendees, 학습\_CourseSkill |
| 학습\_CourseAgenda    | 의제, 과정, 시작 및 종료 시간                          | 학습\_회사, 학습\_CalendarOffset, 학습\_날짜, 학습\_과정 |
| 학습\_CourseAttendees | 이름, 신분, 직업, 등록일                         | 학습\_회사, 학습\_CalendarOffset, 학습\_날짜, 학습\_인구통계, 학습\_고용, 학습\_과정, 학습\_WorkerName, 학습\_WorkerTitle, 학습\_작업, 학습\_직책 |
| 학습\_CourseSkill     | 스킬, 스킬 종류, 레벨                                     | 학습\_과정 |
| 학습\_날짜            | 일, 주, 월 및 년                                   | 학습\_CourseAgenda, 학습\_CourseAttendees |
| 학습\_인구통계    | 생년월일, 성별, 출신 민족 및 결혼 여부         | 학습\_CourseAgenda, 학습\_CourseAttendees |
| 학습\_고용      | 시작 날짜, 종료 날짜 및 전환 날짜                        | 학습\_CourseAgenda, 학습\_CourseAttendees |
| 학습\_직업             | 함수, 유형 및 제목                                        | 학습\_CourseAgenda, 학습\_CourseAttendees |
| 학습\_직책        | 직위, 직위 및 FTE(정규직)                  | 학습\_CourseAgenda, 학습\_CourseAttendees |
| 학습\_WorkerName      | 이름, 성 및 전체 이름                             | 학습\_CourseAttendees |
| 학습\_WorkerTitle     | 직위 및 연공서열 날짜                                         | 학습\_CourseAttendees |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]