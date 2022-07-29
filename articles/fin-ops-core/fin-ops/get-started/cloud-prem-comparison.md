---
title: 클라우드 및 온프레미스 기능 비교
description: 주제는 클라우드 및 온프레미스에서 지원되는 기능을 보여줍니다.
author: sericks007
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: 68082ad0ae264b76a852d8d12412af8c4ad917703441c41e67743d1b499a8d73
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460870"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>클라우드 및 온프레미스 기능 비교

[!include [banner](../includes/banner.md)]

이번에는 다음 애플리케이션에 대해 클라우드와 온프레미스에서 사용할 수 있는 기능을 비교하여 보여줍니다.

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

[개발 및 관리 기능](cloud-prem-comparison.md#development-and-administration-features)에 대한 정보도 포함되어 있습니다.

다음 표는 적용 분야를 나열합니다. 기능에 대한 클라우드 및 온프레미스 지원이 전체적으로 나열됩니다. 특정 기능이 전체 영역과 다른 경우 기능은 기능 열의 별도 행에 나열됩니다.

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **영역**             | **기능**                | **클라우드** | **온프레미스** |
|---------------------|-----------------------------|-----------|-----------------|
| 규정 준수 및 인증        |                                                                                           | 예       | 예             |
|                                      | SOC 1 Type 1 인증                                                                | 예       | 아니요              |
| 데이터 관리 및 통합      |                                                                                           | 예       | 예             |
|                                      | 자체 데이터 웨어하우스로 데이터 내보내기                                                    | 예       | 예             |
|                                      | 데이터 항목에 대한 증분 업데이트 내보내기 활성화                                 | 예       | 예             |
|                                      | 데이터 통합                                                                         | 예       | 예             |
| 문서 관리                  |                                                                                           | 예       | 예             |
| 재무 관리                 |                                                                                           | 예       | 예             |
| 도움말                                 |                                                                                           | 예       | 아니요              |
| '인적 자원',                      |                                                                                           | 예       | 예             |
| 지능                         |                                                                                           | 예       | 예             |
|                                      | 전자보고(ER)                                                                 | 예       | 예             |
|                                      | 어: LCS와 통합                                                                  | 예       | 아니요              |
|                                      | 어: 통합 SharePoint                                                           | 예       | 아니요              |
|                                      | 어: RCS(Regulatory Configuration Services)와의 통합                              | 예       | 아니요              |
|                                      | 어: ER 리포지토리를 통해 액세스할 수 있는 ER 구성의 스토리지로 로컬 파일 시스템 사용 | 아니요        | 예             |
|                                      | PowerBI.com과의 통합                                                              | 예       | 아니요              |
|                                      | PowerBI Desktop과 통합                                                          | 아니요        | 예             |
|                                      | 분석 작업 공간                                                                     | 예       | 아니요              |
|                                      | 지능형 비즈니스 프로세스: 권장 사항                                             | 예       | 아니요              |
|                                      | Power BI Desktop 또는 Excel PowerQuery 도구를 사용하여 OData로 Power BI 보고서 작성    | 예       | 아니요              |
|                                      | SSRS(SQL Server Reporting Services)는 수평 확장을 지원합니다.                                 | 예       | 예             |
|                                      | 원격 측정은 클라우드로 전송됩니다.                                                   | 예       | 아니요              |
| Lifecycle Services                   |                                                                                           | 예       | 예             |
|                                      | 구성 가능한 비즈니스 프로세스                                                           | 예       | 아니요              |
| 현지화                        |                                                                                           | 예       | 예             |
| 모바일 앱, 작업 공간 및 플랫폼 |                                                                                           | 예       | 예             |
| 사무실 통합                   |                                                                                           | 예       | 예             |
| 조직 관리          |                                                                                           | 예       | 예             |
| 급여                              |                                                                                           | 예       | 예             |
|                                      | 계좌 입금                                                                            | 예       | 아니요              |
| 프로젝트 관리 및 회계    |                                                                                           | 예       | 예             |
| 보안                             |                                                                                           | 예       | 예             |
| 서비스 관리                   |                                                                                           | 예       | 예             |
| 웹 클라이언트                           |                                                                                           | 예       | 예             |
|                                      | 작업 레코더 - BPM 라이브러리에서 작업 기록 저장 또는 로드                         | 예       | 아니요              |
| 고객 지원                              |                                                                                           | 예       | 예             |
|                                      | 도움말 및 지원 메뉴를 통한 지원 액세스                                             | 예       | 아니요              |
|                                      | 비즈니스 이벤트                                                                           | 예       | 예(인터넷 연결이 필요하거나 인트라넷 내에서 비즈니스 이벤트를 송수신하기 위해 사용자 지정 끝점을 구현해야 함)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **영역**                | **기능**             | **클라우드** | **온프레미스** |
|-------------------------|-------------------|-----------|-----------------|
| 자산 관리자                     |                                                                                           | 예       | 예             |
| 규정 준수 및 인증        |                                                                                           | 예       | 예             |
|                                      | SOC 1 Type 1 인증                                                                | 예       | 아니요              |
| 원가회계                      |                                                                                           | 예       | 예             |
|                                      | 원가 회계 콘텐츠 팩 Power BI                                                 | 예       | 아니요              |
|                                      | 모바일 앱용 원가회계 작업공간                                                  | 예       | 아니요              |
| 원가 관리                      |                                                                                           | 예       | 예             |
|                                      | 비용 관리 콘텐츠 팩 Power BI                                                 | 예       | 아니요              |
| 데이터 관리 및 통합      |                                                                                           | 예       | 예             |
|                                      | 구성 기반 확장                                                            | 예       | 아니요              |
|                                      | 자체 데이터 웨어하우스로 데이터 내보내기                                                    | 예       | 예             |
|                                      | 데이터 항목에 대한 증분 업데이트 내보내기 활성화                                 | 예       | 예             |
|                                      | 데이터 통합                                                                         | 예       | 예             |
| 문서 관리                  |                                                                                           | 예       | 예             |
| 도움말                                 |                                                                                           | 예       | 아니요              |
| 지능                         |                                                                                           | 예       | 예             |
|                                      | 전자보고(ER)                                                                 | 예       | 예             |
|                                      | 어: LCS와 통합                                                                  | 예       | 아니요              |
|                                      | 어: 통합 SharePoint                                                           | 예       | 아니요              |
|                                      | 어: RCS(Regulatory Configuration Services)와의 통합                              | 예       | 아니요              |
|                                      | 어: ER 리포지토리를 통해 액세스할 수 있는 ER 구성의 스토리지로 로컬 파일 시스템 사용 | 아니요        | 예             |
|                                      | PowerBI.com과의 통합                                                              | 예       | 아니요              |
|                                      | PowerBI Desktop과 통합                                                          | 아니요        | 예             |
|                                      | 분석 작업 공간                                                                     | 예       | 아니요              |
|                                      | 지능형 비즈니스 프로세스: 권장 사항                                             | 예       | 아니요              |
|                                      | Power BI Desktop 또는 Excel PowerQuery 도구를 사용하여 OData로 Power BI 보고서 작성    | 예       | 아니요              |
|                                      | SSRS(SQL Server Reporting Services)는 수평 확장을 지원합니다.                                 | 예       | 예             |
|                                      | 원격 측정은 클라우드로 전송됩니다.                                                   | 예       | 아니요              |
| 재고 관리                 |                                                                                           | 예       | 예             |
| Lifecycle Services                   |                                                                                           | 예       | 예             |
|                                      | 구성 가능한 비즈니스 프로세스                                                           | 예       | 아니요              |
| 현지화                        |                                                                                           | 예       | 예             |
| 제조                        |                                                                                           | 예       | 예             |
| 마스터 플래닝 및 예측      |                                                                                           | 예       | 예             |
| 최적화 계획                |                                                                                           | 예       | 아니요              |
| 모바일 앱, 작업 공간 및 플랫폼 |                                                                                           | 예       | 예             |
| 사무실 통합                   |                                                                                           | 예       | 예             |
| 조직 관리          |                                                                                           | 예       | 예             |
| 조달 및 소싱             |                                                                                           | 예       | 예             |
|                                      | 구매 요청에서 외부 카탈로그로 펀치 아웃                                   | 예       | 아니요              |
|                                      | 구매 지출 분석 Power BI 보고서                                                  | 예       | 아니요              |
| 상품정보 관리       |                                                                                           | 예       | 예             |
| 제품 마스터 데이터                  |                                                                                           | 예       | 예             |
| 생산                           |                                                                                           | 예       | 예             |
|                                      | 생산 실적 Power BI 보고서                                                   | 예       | 아니요              |
| 프로젝트 관리 및 회계    |                                                                                           | 예       | 예             |
| 영업                                |                                                                                           | 예       | 예             |
|                                      | 판매 및 수익성 실적 Power BI 보고서                                      | 예       | 아니요              |
| 보안                             |                                                                                           | 예       | 예             |
| 서비스 관리                   |                                                                                           | 예       | 예             |
| 공급망 관리              |                                                                                           | 예       | 예             |
| 운송 관리            |                                                                                           | 예       | 예             |
| 공급 업체 협업                 |                                                                                           | 예       | 아니요              |
| 물류 창고 관리, 물류 관리                 |                                                                                           | 예       | 예             |
|                                      | 모바일 창고 앱                                                                      | 예       | 예             |
|                                      | 창고 Power BI 보고서                                                              | 예       | 아니요              |
| 웹 클라이언트                           |                                                                                           | 예       | 예             |
|                                      | 작업 레코더 - BPM 라이브러리에서 작업 기록 저장 또는 로드                         | 예       | 아니요              |
| 고객 지원                              |                                                                                           | 예       | 예             |
|                                      | 도움말 및 지원 메뉴를 통한 지원 액세스                                             | 예       | 아니요              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

온 프레미스 배포에서 사용할 수 있는 기능 목록을 보려면 [온 프레미스 배포에서 사용할 수 있는 상거래 기능](../../../commerce/retail-onprem.md)을 참조하십시오.

## <a name="dynamics-365-human-resources"></a>Dynamics 365 Human Resources 

| **영역**         | **기능**         | **클라우드** | **온프레미스** |
|------------------|---------------------|-----------|-----------------|
| 모든 인적 자원 영역 | 모든 인적 자원 기능 | 예       | 아니요              |

## <a name="development-and-administration-features"></a>개발 및 관리 기능

| **영역**                   | **기능**                               | **클라우드** | **온프레미스** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| 빌드 및 테스트             |                                           | 예       | 예             |
| 확대              |                                           | 예       | 예             |
| 모니터링 및 원격 측정   |                                           | 예       | 예             |
| 플랫폼 호환성     |                                           | 예       | 예             |
| 서비스                  |                                           | 예       | 예             |
|                            | 서비스 환경                    | 예       | 아니요              |
| 추적 파서               |                                           | 예       | 예             |
| 성능 타이머                  |                                           | 예       | 예\*           |
| 업그레이드                    |                                           | 예       | 예             |
|                            | 업그레이드                                   | 예       | 아니요              |
|                            | 이전 버전에 대한 업그레이드 및 지원 | 예       | 아니요              |
| Visual Studio 개발 중  |                                           | 예       | 예             |

\* 온프레미스 환경에서 PerfTimer는 클라이언트에 대한 결과만 표시합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
