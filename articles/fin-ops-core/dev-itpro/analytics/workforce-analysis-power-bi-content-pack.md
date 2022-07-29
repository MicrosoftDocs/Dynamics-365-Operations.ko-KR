---
title: 인력 지표 Power BI 콘텐츠
description: 이 항목에서는 Workforce 메트릭 Power BI 콘텐츠에 대해 설명합니다.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkforceWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9393b4dcc6cb5f65d38c6904bf38def9d50af281671e0e09314148824f3e6891
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460744"
---
# <a name="workforce-metrics-power-bi-content"></a>인력 지표 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 항목에서는 **Workforce 메트릭** Microsoft Power BI 콘텐츠에 대해 설명합니다. Power BI 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용된 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스
**Workforce 메트릭** Power BI 콘텐츠는 이러한 제품을 사용하는 경우 **인사 관리** 작업 영역에 표시됩니다.

- Microsoft Dynamics 365 Finance
- Microsoft Dynamics 365 Human Resources

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 메트릭
다음 표는 각 보고서에 표시되는 메트릭을 보여줍니다.

| 보고서                                           | 메트릭 |
|--------------------------------------------------|---------|
| 사람 메트릭                                   | 기타 보고서 요약 |
| 인원 분석 회사, 부서, 위치 | 회사별 인원수, 부서별 인원수, 지역별 인원수, 총 인원수 |
| 인원 분석 작업, 단계, 관리자            | 직무별 인원수, 단계별 인원수, 관리자별 인원수, 총 인원수 |
| 인원 추세 분석                         | 회사별 올해 인원 대 작년 및 지난 12개월 동안의 롤링 인원 수 |
| FTE 분석                                     | 총 FTE(Full-time Equivalent), 할당된 총 FTE, 부서별 FTE, 지난 12개월 동안의 FTE, 직무별 FTE |
| 인력 통계                           | 연령별, 성별별 인원수, 민족별 인원수, 병역별 인원수, 혼인 상태별 인원수, 정규 학생 수, 평균 근속 기간, 평균 연령, 남녀 직원 비율, 직원 구사 언어 |
| 포지션 분석                                | 부서별 공석, 공석, 비정규직, 부서별 직위 |
| 특성 분석                               | 올해 퇴사 전년 대비 이직률, 퇴직자 연령·성별, 퇴직자 평균 근속년수, 이달 퇴사자, 퇴사 사유 |
| 부서별 인원                             | 부서별, 직급별, 발령 시작일과 종료일별 인사번호가 있는 사원 |
| 연공서열 분석                               | 평균 근속년수, 회사별 평균 근속연수, 연공서열 목록 |
| 직원 기념일                           | 이번달 기념일, 다음달 기념일, 근속년수별 사원, 부서별 기념일, 근속년수 |
| 직원 생년월일                               | 이번 달 생일, 다음 달 생일, 직원 생일, 월별, 부서별 생일 |
| 대량 채용 프로젝트                               | 전체 대량 채용 프로젝트, 상태별 대량 채용 프로젝트, 부서 및 소유자별 대량 채용 프로젝트, 직무별 대량 채용 프로젝트, 대량 채용 프로젝트 |

이러한 보고서에서 차트와 타일을 필터링하고 대시보드에 차트와 타일을 고정할 수 있습니다. Power BI에서 필터링 및 고정 방법에 대한 자세한 내용은 [대시보드 생성 및 구성](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)을 참조하세요.

사용하는 Microsoft Dynamics 365 버전에 해당하는 **인력 지표** Power BI 콘텐츠를 다운로드하세요.

> [!NOTE]
> Lifecycle Services에서 사용할 수 있는 .pbix 파일은 재무 및 운영 앱에만 적용됩니다.

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해
다음 표는 콘텐츠의 기반이 된 엔터티를 보여줍니다.

| 엔터티                   | 콘텐츠                                                                            | 다른 엔티티와의 관계 |
|--------------------------|-------------------------------------------------------------------------------------|-----------------------------------|
| 캘린더 오프셋          | 슬라이스 보고서에 대한 캘린더 오프셋                                                   | 과거 직책 발령, 직위 추세, 직원 추세, 퇴직 직원 |
| 회사                  | 보고서를 필터링할 회사                                                      | 현재 직원, 퇴직 직원, 직원 동향 |
| 현재 직위         | 현재 일자 기준 직위, FTE, 공석 및 공석 | 직무, 직위 |
| 현재 직원         | 현재 일자, 연령, 인원수 기준 근로자                                  | 회사, 지리적 위치, 직원 이름, 보고 대상, 직원 직위, 인구 통계, 직업, 고용, 직위 |
| 날짜                     | 일, 주, 월 및 년                                                      | 과거 직위 발령, 직위 추세, 퇴직 직원, 직원 추세 |
| 인구통계             | 생년월일, 성별, 출신 민족 및 결혼 여부                            | 현재 직원, 퇴직 직원, 직원 동향 |
| 고용               | 시작 날짜, 종료 날짜 및 전환 날짜                                           | 현재 직원, 퇴직 직원, 직원 동향 |
| 지리적 위치      | 시, 카운티, 우편번호 및 시/도                                    | 현재 직원, 퇴직 직원, 직원 동향 |
| 직무                      | 함수, 유형 및 제목                                                           | 현재 직위, 현재 직원 |
| 이전 직위 할당 | 발령사유, 시작일, 종료일, 직무                                    | 달력 오프셋, 날짜, 작업, 위치 |
| 직위                 | 부서, FTE, 직위, 직위 유형 및 직위                                 | 현재 직위, 현재 직원 |
| 직위 추세           | 시간 경과에 따른 직위, FTE 및 직무                                                   | 달력 오프셋, 날짜, 작업, 위치 |
| 보고 대상               | 이름, 성 및 전체 이름                                                | 현재 직원, 퇴직 직원, 직원 동향 |
| 해고된 직원      | 퇴직 근로자, 퇴직 일자, 직위, 직위 및 직무                      | 회사, 지리적 위치, 직원 이름, 보고 대상, 달력 오프셋, 날짜, 직원 직위, 인구 통계, 고용, 직무, 직위 |
| 직원 이름            | 이름, 성 및 전체 이름                                                | 재직자, 해고된 사원, 사원 동향 |
| 직원 직위           | 직위 및 연공서열 날짜                                                            | 현재 직원, 퇴직 직원, 직원 동향 |
| 직원 동향           | 시간, 인원, 회사 및 직위에 따른 근로자                                 | 회사, 지리적 위치, 직원 이름, 보고 대상, 달력 오프셋, 날짜, 직원 직위, 인구 통계, 고용, 직업 |
| 대량 채용 프로젝트        | 대량 고용 프로젝트 수, 프로젝트 소유자 및 프로젝트 상태                     | 회사, 대량 채용 라인 |
| 대량 채용 라인           | 부서, 고용 유형 및 직위                                           | 날짜, 직위, 대량 채용 프로젝트 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]