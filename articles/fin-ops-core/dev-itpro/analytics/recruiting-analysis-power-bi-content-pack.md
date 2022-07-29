---
title: 모집 Power BI 콘텐츠
description: 이 토픽에서는 Power BI 모집 콘텐츠에 대해 설명합니다.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmRecruitmentWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 36ea9f204b50b3d7a6c8e33e69a9c3fd7d82cd79d466e2b9547c6733aa294aea
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460822"
---
# <a name="recruiting-power-bi-content"></a>모집 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 토픽에서는 **모집** Microsoft Power BI 콘텐츠에 대해 설명합니다. Power BI 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용된 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스
**모집** Power BI 콘텐츠는 **채용 관리** 작업 공간에 표시됩니다.

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>채용 관리 작업 공간의 보고서 및 시각적 개체
**채용 관리** 작업 공간에는 **분석** 탭이 있습니다. 이 탭에는 모집에 대해 포함된 Power BI 콘텐츠가 있습니다. 내용은 개요 탭과 세부 정보가 포함된 추가 탭으로 구성됩니다. 다음 테이블에서는 각 탭의 보고서에 대해 설명합니다.

| 보고서               | 콘텐츠 |
|----------------------|----------|
| 모집 개요 | 기타 보고서 요약 |
| 지원자 분석   | 총 지원자 수, 직무별 지원자, 지원자 출처, 여성에서 남성 지원자, 지역별 지원자 |
| 지원자 상태     | 지원자 유형 및 지위별, 지원자 지위 |
| 모집 분석  | 순채용 비율, 평균 채용일수, 불량채용 비율, 채용비용, 채용 프로젝트 수, 지원 대상 채용, 채용 프로젝트별 지원자 대 모집 |

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해
이러한 보고서에서 차트와 타일을 필터링하고 대시보드에 차트와 타일을 고정할 수 있습니다. Power BI 필터링 및 고정 방법에 대한 자세한 내용은 [대시보드 생성 및 구성](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)을 참조하십시오.

다음 표는 **모집** Power BI 콘텐츠의 기반이 되는 엔터티를 보여줍니다.

| 엔터티               | 콘텐츠                                                         | 다른 엔티티와의 관계 |
|----------------------|------------------------------------------------------------------|-----------------------------------|
| 지원자            | 지원자, 채용 지원자, 순 채용 비율 및 비용          | 지원자 이름, 회사, 달력 오프셋, 날짜, 지리적 위치, 인구 통계, 직업, 미디어, 모집 프로젝트 |
| 지원자 이름       | 신청자 이름, 성 및 전체 이름                   | 지원자, 고용된 지원자, 해고된 지원자 |
| 캘린더 오프셋      | 슬라이스 보고서에 대한 캘린더 오프셋                                | 지원자, 고용된 지원자, 해고된 지원자 |
| 회사              | 보고서를 필터링할 회사                                   | 지원자, 고용된 지원자, 해고된 지원자 |
| 날짜                 | 일, 주, 월 및 년                                   | 지원자, 고용된 지원자, 해고된 지원자 |
| 인구통계         | 생년월일, 성별, 출신 민족 및 결혼 여부         | 지원자, 고용된 지원자, 해고된 지원자 |
| 취업 지원자   | 지원자, 성과, 시작일 및 지원자 유형           | 회사, 달력 오프셋, 날짜, 지리적 위치, 지원자 이름, 고용, 성과, 직업, 미디어, 모집 프로젝트 |
| 고용           | 시작 날짜, 종료 날짜 및 전환 날짜                        | 지원자, 고용된 지원자, 해고된 지원자 |
| 지리적 위치  | 시, 카운티, 우편번호 및 시/도                 | 지원자, 고용된 지원자, 해고된 지원자 |
| 직무                  | 함수, 유형 및 제목                                        | 지원자, 고용된 지원자, 해고된 지원자 |
| 미디어                | 지원자의 출처                                             | 지원자, 고용된 지원자, 해고된 지원자 |
| 성능          | 등급, 설명 및 등급 모델                            | 지원자, 고용된 지원자, 해고된 지원자 |
| 구인 프로젝트  | 프로젝트 설명, 프로젝트 상태 및 오프닝                | 지원자, 고용된 지원자, 해고된 지원자 |
| 종료된 지원자 | 해지된 지원자, 사유, 성과, 해지일 | 회사, 달력 오프셋, 날짜, 지리적 위치, 성과, 인구통계, 고용, 미디어, 모집 프로젝트, 지원자 이름 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]