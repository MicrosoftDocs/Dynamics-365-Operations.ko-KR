---
title: 직원 역량 및 개발 Power BI 콘텐츠
description: 이번에는 직원 역량 및 개발 Power BI 콘텐츠에 대해 설명합니다.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 572f6bcfa202995d90080e1a31476122f7ec23d71214d5ff0dd44ed919859c57
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460759"
---
# <a name="employee-competencies-and-development-power-bi-content"></a>직원 역량 및 개발 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이번에는 직원 역량 및 개발 Power BI 콘텐츠에 대해 설명합니다. 

## <a name="reports-that-are-included-in-the-content-pack"></a>콘텐츠 팩에 포함된 보고서
콘텐츠 팩을 데이터에 연결하면 보고서에 조직의 데이터가 표시됩니다. 이전에 Microsoft Power BI 사용한 적이 없다면 [Power BI에 대한 안내 학습](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData) 페이지에서 자세히 알아볼 수 있습니다. 콘텐츠 팩에 포함된 보고서에는 추가 정보가 포함된 차트와 테이블이 모두 있습니다. 다음 테이블에서는 보고서를 설명합니다.

| 보고서                            | 목차                                               |
|-----------------------------------|--------------------------------------------------------|
| 역량 및 개발 분석 | 팀원 스킬 유형 및 유형별 팀원 스킬 |
| 기술 프로필                     | 선택한 직원의 기술 프로필                |
| 기술 분석                    | 유형 및 등급별 기술                              |

이러한 보고서에서 차트와 타일을 필터링하고 대시보드에 차트와 타일을 고정할 수 있습니다. Power BI 필터링 및 고정 방법에 대한 자세한 내용은 [대시보드 생성 및 구성](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)을 참조하십시오.

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해
애플리케이션 데이터는 직원 역량 및 개발 콘텐츠 팩의 보고서를 채우는 데 사용됩니다. 다음 표에서는 콘텐츠 팩의 기반이 되는 엔터티를 보여 줍니다.

| 엔터티                            | 목차                                                                                                   | 다른 엔티티와의 관계 |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Workforce\_CalendarOffset         | 슬라이스 보고서에 대한 캘린더 오프셋                                                                          | |
| Workforce\_Company                | 보고서를 필터링할 회사                                                                             | |
| Workforce\_Compensation           | 시간 경과에 따른 급여율 및 빈도                                                                           | |
| Workforce\_CurrentCompensation    | 현재 일자 기준의 급여율 및 빈도                                                              | Workforce\_Company, Workforce\_CurrentCompensation, Workforce\_Demographics, Workforce\_Job, Workforce\_Position |
| Workforce\_CurrentPosition        | 현재 날짜 기준의 직위, FTE(Full-time Equivalent), 공석 및 공석 개설 직위 | Workforce\_Job Workforce\_Position |
| Workforce\_CurrentWorker          | 현재 일자, 연령, 인원수 기준 근로자                                                         | Workforce\_Company Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_PersonSkill, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Job, Workforce\_Employment, Workforce\_Position |
| Workforce\_Date                   | 일, 주, 월 및 년                                                                             | |
| Workforce\_Demographics           | 생년월일, 성별, 출신 민족 및 결혼 여부                                                   | |
| Workforce\_Employment             | 시작 날짜, 종료 날짜 및 전환 날짜                                                                  | |
| Workforce\_GeographicLocation     | 시, 카운티, 우편번호 및 시/도                                                           | |
| Workforce\_Job                    | 함수, 유형 및 제목                                                                                  | |
| Workforce\_JobPreferredSkill      | 중요도, 등급, 기술 및 기술 수준                                                                 | Workforce\_Skill, Workforce\_Job |
| Workforce\_PastPositionAssignment | 발령사유, 시작일, 종료일, 직무                                                           | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_Performance            | 등급, 설명 및 등급 모델                                                                      | |
| Workforce\_PersonSkill            | 레벨, 레벨 날짜 및 스킬                                                                               | Workforce\_Skill |
| Workforce\_PersonSkillAnalysis    | 인증, 레벨, 레벨 날짜 및 기술                                                                    | Workforce\_WorkerName, Workforce\_Skill |
| Workforce\_Position               | 부서, FTE, 직위, 직위 유형 및 직위                                                        | |
| Workforce\_PositionTrend          | 시간 경과에 따른 직위, FTE 및 직무                                                                          | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_ReportsToWorkerName    | 이름, 성 및 전체 이름                                                                       | |
| Workforce\_Skill                  | 기술, 기술 유형 및 등급                                                                              | |
| Workforce\_TerminatedWorker       | 퇴직 근로자, 퇴직 일자, 직위, 직위 및 직무                                             | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job, Workforce\_Position |
| Workforce\_WorkerName             | 이름, 성 및 전체 이름                                                                       | |
| Workforce\_WorkerTitle            | 직위 및 연공서열 날짜                                                                                   | |
| Workorce\_WorkerTrend             | 시간, 인원, 회사 및 직위에 따른 근로자                                                        | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]