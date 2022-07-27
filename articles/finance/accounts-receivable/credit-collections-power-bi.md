---
title: 신용 및 수금 관리 Power BI 콘텐츠
description: 이 토픽에서는 신용 및 수금 관리 Power BI 콘텐츠에 포함된 내용을 설명합니다. Power BI 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용되는 데이터 모델 및 엔터티에 대한 정보를 제공합니다.
author: ShivamPandey-msft
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 65423f49ba106a152f58c92533c4f1a16d47a318982cfe69bb23f9091fa09846
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450667"
---
# <a name="credit-and-collections-management-power-bi-content"></a>신용 및 수금 관리 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 토픽에서는 **신용 및 수금 관리** Microsoft Power BI 콘텐츠에 포함된 내용을 설명합니다. Power BI 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용된 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="overview"></a>개요

**신용 및 수금 관리** Power BI 콘텐츠는 신용 및 수금 관리자와 수금 직원을 위해 만들어졌습니다. 미결제 판매 일수, 연체 잔액, 신용 노출 및 신용 한도를 초과한 고객과 같은 주요 신용 및 수금 지표를 제공합니다. 거래 데이터를 사용하고 모든 회사의 신용 및 수금에 대한 집계 보기를 제공합니다. 또한 회사, 고객 그룹 및 고객별로 내역을 제공합니다.

이 Power BI 콘텐츠는 다음과 같이 10개의 보고서 페이지로 구성됩니다.

- 두 개의 개요 페이지(신용 개요를 위한 한 페이지와 수금 개요를 위한 한 페이지)
- 다양한 차원에 걸쳐 분할된 신용 및 수금 메트릭의 세부 정보를 제공하는 8개의 세부 정보 페이지

모든 금액은 시스템 통화로 표시됩니다. **시스템 매개 변수** 페이지에서 시스템 통화를 설정할 수 있습니다.

기본적으로 현재 회사의 신용 및 수금 데이터가 표시됩니다. 모든 회사의 데이터를 보려면 역할에 **CustCollectionsBICrossCompany** 의무를 할당합니다.

## <a name="setup-needed-to-view-power-bi-content"></a>Power BI 콘텐츠를 보려면 설정이 필요합니다

**고객 신용 및 수금** Power BI 시각적 개체에 데이터를 표시하려면 다음 설정을 완료해야 합니다.

1. **시스템 관리 > 설정 > 시스템 매개 변수** 로 이동하여 **시스템 통화** 및 **시스템 환율** 을 설정합니다.
2. **총계정원장 > 일정 > 회계 일정** 으로 이동하여 활성 기간에 지정된 회계 일정 날짜를 검증합니다.
3. **총계정원장 > 설정 > 원장** 으로 이동하고 **회계 통화** 및 **환율 유형** 을 설정합니다.
4. 거래 통화와 회계 통화, 회계 통화 및 시스템 통화 간의 환율을 정의합니다. 이렇게 하려면 **총계정원장 > 통화 > 통화 환율** 로 이동합니다.
5. **시스템 관리 > 설정 > 엔터티 스토어** 로 이동하여 **CustCollectionsBIMeasurementsV2** 집계 측정값을 새로 고칩니다.

>[!NOTE] 
> 에이징 기간 정의는 Power BI 콘텐츠에서 에이징 데이터를 활성화하려면 **수취 계정 매개 변수 > 수금 > 수금 기본값** 에서 설정해야 합니다.

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스

**신용 및 수금 관리** Power BI 콘텐츠는 **고객 신용 및 수금** 작업 영역에 표시됩니다.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 보고서

**CustCollectionsBICrossCompany** Power BI 콘텐츠에는 메트릭 집합으로 구성된 보고서가 포함됩니다. 이러한 메트릭은 차트, 타일 및 테이블로 시각화됩니다. 다음 표는 **CustCollectionsBICrossCompany** Power BI 콘텐츠의 시각화 개요를 제공합니다.

| 보고서 페이지                 | 시각화 |
|-----------------------------|---------------|
| 수금 개요        | <ul><li>기한이 지난 고객</li><li>신용 한도 초과 고객</li><li>DSO 30일</li><li>미결 케이스</li><li>케이스를 마감하는 평균 일수</li><li>미결 활동</li><li>활동 마감하는 평균 일수</li><li>미결 이자 계산서</li><li>미결 수금 레터</li><li>고객 보류</li><li>판매 보류</li><li>에이징 잔액</li><li>수금 상태 금액</li><li>수금 코드 금액</li><li>사유에 따른 채무 인하</li><li>지역별 미지불 잔액</li><li>예상 지불</li></ul> |
| 신용 개요             | <ul><li>기한이 지난 고객</li><li>신용 한도 대 미지불 잔액</li><li>신용 한도 초과 고객 그리드</li><li>회사별 신용 한도 초과 고객</li><li>사용한 신용 대 총 신용 한도</li><li>신용 한도 대 지역별 사용 신용</li><li>신용 등급별 고객</li></ul> |
| 신용 한도                | <ul><li>신용 한도</li><li>신용 한도 세부 정보</li><li>고객별 신용 한도</li><li>고객 그룹별 신용 한도</li><li>회사별 신용 등급별 신용 한도</li><li>신용 한도 대 지역별 사용 신용</li></ul> |
| 신용 한도 초과 고객 | <ul><li>신용 한도 초과 고객</li><li>신용 한도 초과 고객 세부 정보</li><li>회사별 신용 한도 초과 고객</li><li>고객 그룹별 신용 한도 초과 고객</li><li>지역별 신용 한도 초과 고객</li></ul> |
| 연체 고객          | <ul><li>연체 고객</li><li>연체 고객 세부 정보</li><li>회사별 연체 고객</li><li>고객 그룹별 연체 고객</li><li>지역별 연체 고객</li></ul> |
| 에이징 잔액               | <ul><li>에이징 잔액</li><li>에이징 잔액 세부 정보</li><li>회사별 에이징 잔액</li><li>고객 그룹별 에이징 잔액</li></ul> |
| 예상 지불           | <ul><li>예상 지불</li><li>예상 지불 세부 정보</li><li>회사별 예상 지불</li><li>고객 그룹별 예상 지불</li><li>지역별 예상 지불</li></ul> |
| 채무 인하                  | <ul><li>지역별 채무 인하</li><li>채무 인하 세부 정보</li><li>주 계정별 채무 인하</li><li>회사별 채무 인하</li><li>고객 그룹별 채무 인하</li><li>지역별 채무 인하</li></ul> |
| 수금 상태          | <ul><li>분쟁 중</li><li>지불 약속 위반</li><li>지불 약속</li><li>수금 상태 상세 정보</li><li>수금 상태 금액</li><li>미결 케이스</li><li>미결 활동</li></ul> |
| 수금 레터         | <ul><li>수금 코드 금액</li><li>수금 코드 금액 세부 정보</li><li>회사별 수금 레터 금액</li><li>고객 그룹별 수금 레터 금액</li><li>지역별 수금 레터 금액</li></ul> |

이러한 모든 보고서의 차트와 타일을 필터링하여 대시보드에 고정할 수 있습니다. Power BI에서 필터링 및 고정 방법에 대한 자세한 내용은 [대시보드 생성 및 구성](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/)을 참조하세요. 기본 데이터 내보내기 기능을 사용하여 시각화에 요약된 기본 데이터를 내보낼 수도 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]