---
title: 인도네시아 원천징수세 신고
description: 이 토픽에서는 인도네시아에 대한 원천징수세 신고를 구성하고 생성하는 방법에 대해 설명합니다.
author: sndray
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2021-12-02
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6cf2f9240ea747054578c52343af34b15c250f38
ms.sourcegitcommit: f51e74ee9162fe2b63c6ce236e514840795acfe1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2021
ms.locfileid: "8451315"
---
# <a name="withholding-tax-report-for-indonesia-id-00005"></a>인도네시아 원천징수세 신고(ID-00005)

[!include [banner](../includes/banner.md)]

이 토픽에서는 인도네시아 법인이 e-Bupot 애플리케이션에서 원천징수세 거래를 보고하는 데 사용하는 PPH 원천징수세 파일을 설정하고 생성하는 방법에 대해 설명합니다.

인도네시아 세무 당국(DGT)은 KPP Pratama에 소득세 원천징수/징수인(PPh) 23조 및/또는 26조로 등록된 과세 대상 기업가(PKP)가 e-Bupot 애플리케이션을 사용하여 소득세 신고 23조 및 26조를 전자적으로 보고해야 한다고 결정합니다. 

- **제23조** – 보고서에는 기본 주소의 국가/지역 코드가 인도네시아 코드인 공급업체의 모든 원천징수 거래가 포함됩니다.
- **제26조** – 보고서에는 기본 주소의 국가/지역 코드가 인도네시아 코드가 아닌 공급업체의 모든 원천징수 거래가 포함됩니다.

## <a name="prerequisites"></a>전제 조건

- 법인의 기본 주소는 인도네시아에 있어야 합니다.
- **기능 관리** 작업 영역에서 **글로벌 원천징수세** 기능을 활성화해야 합니다. 기능을 활성화하는 방법에 대한 자세한 내용은 [기능 관리 개요](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하십시오.

### <a name="download-electronic-reporting-configurations"></a>전자 보고 구성 다운로드

가져오기 파일 생성은 전자 보고(ER) 구성을 기반으로 합니다. 구성 가능한 보고의 기능 및 개념에 대한 자세한 내용은 [전자 보고](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)를 참조하십시오.

운영 및 사용자 수용 테스트(UAT) 환경의 경우 [Lifecycle Services에서 전자 보고 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md) 토픽의 지침을 따르세요.

가져오기 파일을 생성하려면 리포지토리에서 다음 구성을 업로드합니다.

- **세금 신고 model.version.93.xml** 또는 이후 버전
- **세금 신고 모델 mapping.version.93.153.xml** 이상 버전
- **WHT PPh 스키마 가져오기(ID).version.93.14** 이상 버전

## <a name="set-up-general-ledger-parameters"></a>총계정원장 매개 변수 설정

1. **세금** \> **설정** \> **총계정원장 매개 변수** 로 이동합니다.
2. **원천징수세** 탭의 **WHT 선언 형식 매핑** 필드에서 **WHT PPh 스키마 가져오기(ID)** 를 선택합니다. 
3. **세금** \> **설정** \> **원천징수세** \> **원천징수세 수익 유형** 으로 이동하여 **Kode Bukti Potong** 원천징수세 수익 유형을 설정한 다음 관련 항목 원천징수세 그룹에 코드를 할당합니다. e-Bupot 애플리케이션을 사용하여 통합 파일을 생성하려면 코드가 필요합니다. 

## <a name="generate-the-withholding-import-file"></a>원천징수 가져오기 파일 생성

특정 기간에 대한 e-Bupot 파일을 준비하고 생성하는 과정은 세금 정산 또는 후불 작업 중에 게시된 원천징수세 거래를 기반으로 합니다.

다음 단계에 따라 파일을 생성하세요.

1. **세금** \> **신고** \> **원천징수세** \> **PPH 수입 파일 e-bupot 23 및 26** 으로 이동합니다.
2. 보고서의 "시작" 날짜와 "끝" 날짜를 선택한 다음 결산 기간을 선택합니다.
3. 거래 날짜를 입력한 후 **확인** 을 선택합니다.
4. 언어를 선택합니다. 모든 보고서는 미국 영어(**en-us**) 및 인도네시아어(**id**)로 번역됩니다.
5. 비즈니스 유형을 선택한 다음 수표 및 문서 번호를 입력합니다. 
6. 보고서에 관리자가 서명했는지 확인합니다. 이 정보는 파일에 보고됩니다. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
