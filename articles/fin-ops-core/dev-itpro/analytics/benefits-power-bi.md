---
title: 혜택 Power BI 내용
description: 이번에는 혜택 Power BI 내용에 대해 설명합니다.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 0e7cadc16c5ed6c6eab8c90090cac017221f63f466115b04a6a3b843db44b1c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460628"
---
# <a name="benefits-power-bi-content"></a>혜택 Power BI 내용

[!include [banner](../includes/banner.md)]

이번에는 **혜택** Microsoft Power BI 내용에 대해 설명합니다. 포함된 보고서에 액세스하는 방법을 설명하고 콘텐츠를 작성하는 데 사용된 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스
**혜택** Power BI 콘텐츠는 다음 제품 중 하나를 사용하는 경우 **혜택 관리** 작업 공간에 표시됩니다.

- Microsoft Dynamics 365 Finance
- Microsoft Dynamics 365 Human Resources

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 보고서
**혜택** Power BI 콘텐츠에 포함된 보고서에는 추가 정보가 포함된 차트와 테이블이 모두 있습니다. 다음 테이블에서는 보고서를 설명합니다.

| 보고서                      | 목차                                                                                       |
|-----------------------------|------------------------------------------------------------------------------------------------|
| 혜택 등록 개요 | 가장 많이 등록된 제도와 가장 적게 등록된 제도, 사원 그룹별 등록, 선택한 복리후생 제도 옵션 |
| 직원 복리후생           | 선택한 복리후생별 사원 등록                                                        |

이러한 보고서에서 차트와 타일을 필터링하고 대시보드에 차트와 타일을 고정할 수 있습니다. Power BI 필터링 및 고정 방법에 대한 자세한 내용은 [대시보드 생성 및 구성](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)을 참조하십시오.

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해
다음 데이터는 **혜택** Power BI 콘텐츠의 보고서를 작성하는 데 사용됩니다. 이 표는 콘텐츠의 기반이 된 엔터티를 보여줍니다.

| 엔터티                   | 목차                                                                                                   | 다른 엔티티와의 관계 |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| 캘린더 오프셋          | 슬라이스 보고서에 대한 캘린더 오프셋                                                                          | 과거 직책 발령, 직위 추세, 직원 추세, 퇴직 직원 |
| 회사                  | 보고서를 필터링할 회사                                                                             | 현재 보상, 현재 직원, 퇴직 직원, 직원 동향 |
| 보상             | 시간 경과에 따른 급여율 및 빈도                                                                           | 현재 보상, 현재 직원, 퇴직 직원, 직원 동향 |
| 현재 보상     | 현재 일자 기준의 급여율 및 빈도                                                              | 회사, 보상, 인구 통계, 직업, 직위 |
| 현재 위치         | 현재 날짜 기준의 직위, FTE(Full-time Equivalent), 공석 및 공석 개설 직위 | 직업, 직위 |
| 현재 직원         | 현재 일자, 연령, 인원수 기준 근로자                                                         | 회사, 보상, 지리적 위치, 직원 이름, 보고 대상, 직원 직위, 인구 통계, 직업, 고용, 직위, 복리후생 |
| 날짜                     | 일, 주, 월 및 년                                                                             | 과거 직위 발령, 직위 추세, 퇴직 직원, 직원 추세 |
| 인구통계             | 생년월일, 성별, 출신 민족 및 결혼 여부                                                   | 현재 직원, 퇴직 직원, 직원 동향 |
| 고용               | 시작 날짜, 종료 날짜 및 전환 날짜                                                                  | 현재 직원, 퇴직 직원, 직원 동향 |
| 지리적 위치      | 시, 카운티, 우편번호 및 시/도                                                           | 현재 직원, 퇴직 직원, 직원 동향 |
| 직무                      | 함수, 유형 및 제목                                                                                  | 현재 직위, 현재 직원 |
| 과거 직책 할당 | 발령사유, 시작일, 종료일, 직무                                                           | 달력 오프셋, 날짜, 작업, 위치 |
| 직위                 | 부서, FTE, 직위, 직위 유형 및 직위                                                        | 현재 직위, 현재 직원 |
| 포지션 동향           | 시간 경과에 따른 직위, FTE 및 직무                                                                          | 달력 오프셋, 날짜, 작업, 위치 |
| 보고 대상               | 이름, 성 및 전체 이름                                                                       | 재직자, 해고된 사원, 사원 동향 |
| 해고된 직원      | 퇴직 직원, 퇴직 일자, 직위, 직위 및 직무                                           | 회사, 보상, 지리적 위치, 직원 이름, 보고 대상, 달력 오프셋, 날짜, 직원 직위, 인구 통계, 고용, 직업, 직위, 혜택 |
| 이익                 | 유효 일자, 혜택 옵션, 혜택 플랜 및 혜택 유형                                             | 현재 이름, 퇴직 직원, 직원 동향 |
| 직원 이름            | 이름, 성 및 전체 이름                                                                       | 현재 직원, 퇴직 직원, 직원 동향 |
| 직원 직위           | 직위 및 연공서열 날짜                                                                                   | 현재 직원, 퇴직 직원, 직원 동향 |
| 직원 동향           | 시간, 인원, 회사 및 직위에 따른 근로자                                                        | 회사, 보상, 지리적 위치, 직원 이름, 보고 대상, 달력 오프셋, 날짜, 직원 직위, 인구 통계, 고용, 직업, 혜택 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]