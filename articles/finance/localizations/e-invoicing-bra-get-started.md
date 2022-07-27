---
title: 브라질 전자 송장 발행 시작
description: 이 주제는 브라질에서 Finance 및 Supply Chain Management로 전자 송장 발행을 시작하는 데 도움이 되는 정보를 제공합니다.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 82bbf806d207af0b15406e4bec516420db7f2c06
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451438"
---
# <a name="get-started-with-electronic-invoicing-for-brazil"></a>브라질 전자 송장 발행 시작 

[!include [banner](../includes/banner.md)]

이 주제는 브라질에서 전자 송장 발행을 시작하는 데 도움이 되는 정보를 제공합니다. 이 항목에서는 RCS(Regulatory Configuration Services)의 국가별 구성 단계를 안내하고 [전자 송장 발행 시작](e-invoicing-get-started.md) 항목에 설명된 단계를 보완합니다.

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>브라질 NF-e(BR) 전자 송장 발행 기능에 대한 국가별 구성

**브라질 NF-e(BR) 전자 송장 발행 기능** 의 일부 매개 변수는 기본값으로 게시됩니다. 값을 검토하고 필요한 경우 전자 송장 발행 기능을 서비스 환경에 배포하기 전에 경영 운영을 더 잘 반영하도록 값을 업데이트하십시오.

이 섹션은 [전자 송장 발행 시작](e-invoicing-get-started.md) 항목의 **전자 송장 발행 기능에 대한 국가별 구성** 섹션을 보완합니다.

1. RCS에서 **세계화 기능** 작업 영역의 **기능** 섹션에 있는 **전자 송장 발행** 타일을 선택합니다.
2. **전자 송장 발행 기능** 페이지에서 생성한 **브라질 NF-e(BR)** 전자 송장 발행 기능이 선택되었는지 확인합니다.
3. **버전** 탭에 **초안** 버전이 선택되었는지 확인합니다.
4. **설정** 탭의 그리드에서 **제출** 을 선택한 다음 **편집** 을 선택합니다.
5. **작업** 탭의 **작업** 필드 그룹에서 **(프리뷰) xml 문서에 서명** 작업을 선택합니다.
6. **매개 변수** 필드 그룹에서 **인증서 이름** 을 선택하고 **값** 필드에 키 자격 증명 모음 매개 변수와 연결된 인증서의 이름을 입력합니다.
7. **작업** 탭의 **작업** 필드 그룹에서 **(프리뷰) 브라질 SEFAZ 서비스 호출** 작업을 선택합니다.
8. **매개 변수** 필드 그룹에서 **URL 주소** 매개 변수를 선택합니다.
9. **값** 필드에서 필요한 경우 해당하는 주의 SEFAZ 설명서에서 게시한 웹 서비스의 URL을 검토 및 업데이트한 다음 **저장** 을 선택합니다.
10. **적용 가능성 규칙** 탭의 **적용 가능성 규칙 설정** 필드 그룹에서 웹 서비스의 URL을 참조하는 동일한 상태에 대해 필요에 따라 **상태** 필드 조건을 확인하고 업데이트합니다.
11. **저장** 을 선택하고 페이지를 닫습니다.
12. 서비스 환경에 전자 송장 발행 기능을 배포하려면 [전자 송장 발행 시작](e-invoicing-get-started.md)을 참조하십시오.

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>브라질 NF-e(BR) 전자 송장 발행 기능에 대한 애플리케이션 설정의 국가별 구성

Finance 또는 Supply Chain Management 연결 애플리케이션에 애플리케이션 설정을 배포하기 전에 다음 단계를 완료하십시오.

이 섹션은 [전자 송장 발행 시작](e-invoicing-get-started.md) 항목의 **애플리케이션 설정의 국가별 구성** 섹션을 보완합니다.

1. RCS에서 **세계화 기능** 작업 영역의 **기능** 섹션에 있는 **전자 송장 발행** 타일을 선택합니다.
2. **전자 송장 발행 기능** 페이지에서 **브라질 NF-e(BR)** 전자 송장 발행 기능이 선택되었는지 확인합니다.
3. **버전** 탭에 **초안** 버전이 선택되었는지 확인합니다.
4. **설정** 탭의 **연결된 애플리케이션** 필드에서 **애플리케이션 설정** 을 선택하고 배포할 대상 애플리케이션을 선택합니다.
5. **테이블 이름** 필드에 **회계 문서 헤더** 가 선택되었는지 확인합니다.
6. **응답 유형** 을 선택한 다음 **새로 만들기** 를 선택합니다.
7. **응답 유형** 필드에 고정된 값으로 "Response"를 입력하고 **설명** 필드에 "Description"을 입력합니다.
8. **제출 상태** 필드에서 **보류 중** 을 선택합니다.
9. **모델 매핑** 필드에서 **응답 메시지에서 모델 매핑** 과 함께 **(프리뷰) 응답 메시지 가져오기 형식** 을 선택하고 **저장** 을 선택합니다.
10. **새로 만들기** 를 선택하고 **응답 유형** 필드에 고정된 값으로 "ResponseData"를 입력하고 **설명** 필드에 "Description"을 입력합니다.
11. **제출 상태** 필드에서 **보류 중** 을 선택합니다.
12. **모델 매핑** 필드에서 **응답 데이터 가져오기** 와 함께 **(프리뷰) NF-e 응답 데이터 가져오기 형식(BR)** 을 선택하고 **저장** 을 선택합니다.
13. 애플리케이션을 Finance 또는 Supply Chain 연결된 애플리케이션에 배포하려면 [전자 송장 발행 시작](e-invoicing-get-started.md)을 참조하십시오.

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>브라질 NFS-e ABRASF Curitiba(BR) 전자 송장 발행 기능에 대한 국가별 구성

**브라질 NFS-e ABRASF Curitiba(BR) 전자 송장 발행 기능** 의 일부 매개 변수는 기본값으로 게시됩니다. 검토하고 필요한 경우 전자 송장 발행 기능을 서비스 환경에 배포하기 전에 경영 운영에 더 잘 맞도록 값을 업데이트하십시오.

이 섹션은 [전자 송장 발행 시작](e-invoicing-get-started.md) 항목의 **전자 송장 발행 기능에 대한 국가별 구성** 섹션을 보완합니다.

1. RCS에서 **세계화 기능** 작업 영역의 **기능** 섹션에 있는 **전자 송장 발행** 타일을 선택합니다.
2. **전자 송장 발행 기능** 페이지에서 생성한 **브라질 NFS-e ABRASF Curitiba(BR)** 전자 송장 발행 기능이 선택되었는지 확인합니다.
3. **버전** 탭에서 **초안** 버전이 선택되었는지 확인하고 **설정** 탭의 그리드에서 **제출** 을 선택합니다.
4. **편집** 을 선택하고 **작업** 탭의 **작업** 필드 그룹에서 첫 번째 **(프리뷰) xml 문서에 서명** 을 선택합니다.
5. **매개 변수** 필드 그룹에서 **인증서 이름** 을 선택합니다.
6. **값** 필드에 키 자격 증명 모음 매개 변수와 연결된 인증서 이름을 입력합니다.
7. **작업** 필드 그룹에서 두 번째 **(프리뷰) xml 문서에 서명** 을 선택합니다.
8. **매개 변수** 필드 그룹에서 **인증서 이름** 을 선택합니다.
9. **값** 필드에 키 자격 증명 모음 매개 변수와 연결된 인증서 이름을 입력합니다.
10. **작업** 탭의 **작업** 필드 그룹에서 **(프리뷰) 브라질 SEFAZ 서비스 호출** 작업을 선택합니다.
11. **매개 변수** 필드 그룹에서 **URL 주소** 매개 변수를 선택합니다.
12. **값** 필드에서 필요한 경우 해당하는 Curitiba 시 세무 부서에서 게시한 웹 서비스의 URL을 검토 및 업데이트한 다음 **저장** 을 선택합니다.
13. **설정** 탭의 그리드에서 **문의** 를 선택한 다음 **편집** 을 선택합니다.
14. **작업** 탭의 **작업** 필드 그룹에서 **(프리뷰) 브라질 SEFAZ 서비스 호출** 작업을 선택합니다.
15. **매개 변수** 필드 그룹에서 **URL 주소** 매개 변수를 선택합니다.
16. **값** 필드에서 필요한 경우 해당하는 Curitiba 시 세무 부서에서 게시한 웹 서비스의 URL을 검토 및 업데이트합니다.
17. **저장** 을 선택한 다음 페이지를 닫습니다.
18. 서비스 환경에 전자 송장 발행 기능을 배포하려면 [전자 송장 발행 시작](e-invoicing-get-started.md)을 참조하십시오.

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>브라질 NFS-e ABRASF Curitiba(BR) 전자 송장 발행 기능에 대한 애플리케이션 설정의 국가별 구성

Finance 또는 Supply Chain Management 연결 애플리케이션에 애플리케이션 설정을 배포하기 전에 다음 단계를 완료하십시오.

이 섹션은 [전자 송장 발행 시작](e-invoicing-get-started.md) 항목의 **애플리케이션 설정의 국가별 구성** 섹션을 보완합니다.

1. RCS에서 **세계화 기능** 작업 영역의 **기능** 섹션에 있는 **전자 송장 발행** 타일을 선택합니다.
2. **전자 송장 발행 기능** 페이지에서 **브라질 NFS-e ABRASF Curitiba(BR)** 전자 송장 발행 기능이 선택되었는지 확인합니다.
3. **버전** 탭에서 **초안** 버전이 선택되었는지 확인하고 **설정** 탭에서 **애플리케이션 설정** 을 선택합니다.
4. **연결된 애플리케이션** 필드에서 배포할 애플리케이션을 선택합니다.
5. **테이블 이름** 필드에 회계 문서 헤더가 선택되었는지 확인합니다.
6. **응답 유형** 을 선택하고 **새로 만들기** 를 선택합니다.
7. **응답 유형** 필드에 고정된 값으로 "ABRASFCuritibaSubmitResponse"를 입력하고 **설명** 필드에 "Description"을 입력합니다.
8. **제출 상태** 필드에서 **보류 중** 을 선택합니다.
9. **모델 매핑** 필드에서 **응답 메시지 가져오기** 와 함께 **(프리뷰) NFS-e ABRASF Curitiba 응답 메시지 가져오기(BR)** 를 선택하고 **저장** 을 선택합니다.
10. **새로 만들기** 를 선택하고 **응답 유형** 필드에 고정된 값으로 "ABRASFCuritibaSubmitResponseData"를 입력하고 **설명** 필드에 "Description"을 입력합니다.
11. **제출 상태** 필드에서 **보류 중** 을 선택합니다.
12. **모델 매핑** 필드에서 **응답 데이터 가져오기** 와 함께 **(프리뷰) NFS-e ABRASF 응답 데이터 가져오기 형식(BR)** 을 선택하고 **저장** 을 선택합니다.
13. **새로 만들기** 를 선택하고 **응답 유형** 필드에 고정된 값으로 "ABRASFCuritibaInquireResponse"를 입력하고 **설명** 필드에 "Description"을 입력합니다.
14. **제출 상태** 필드에서 **보류 중** 을 선택합니다.
15. **모델 매핑** 필드에서 **응답 메시지 가져오기** 와 함께 **(프리뷰) NFS-e ABRASF Curitiba 응답 메시지 가져오기(BR)** 를 선택합니다.
16. **저장** 을 선택하고 페이지를 닫습니다.
17. 애플리케이션을 Finance 또는 Supply Chain 연결된 애플리케이션에 배포하려면 [전자 송장 발행 시작](e-invoicing-get-started.md)을 참조하십시오.

## <a name="privacy-notice"></a>개인정보보호 통지
**NF-e Federal - 브라질 전자 송장(BR)** 및 **NFS-e - 브라질 서비스(시) 전자 송장** 기능을 활성화하려면 조직 세금 등록 ID를 포함한 제한된 데이터를 보내야 할 수 있습니다. 이 데이터는 정부 웹 서비스와의 통합에 필요한 사전 정의된 형식으로 이 세무 당국에 전자 송장을 보내기 위해 세무 당국이 승인한 타사 기관으로 전송됩니다. 관리자는 **NF-e Federal - 브라질 전자 송장(BR)** 및 **NFS-e - 브라질 서비스(시) 전자 송장** 기능을 활성화 또는 비활성화할 수 있습니다. 다음 단계는 이 작업을 수행하는 방법을 보여줍니다. 

1. **조직 관리** > **설정** > **전자 문서 매개 변수** 로 이동합니다. 
2. **기능** 탭에서 **NF-e Federal - 브라질 전자 송장(BR)** 또는 **NFS-e - 브라질 서비스(시) 전자 송장** 기능이 포함된 행을 선택하고 기능을 선택합니다. 이러한 외부 시스템에서 Dynamics 365 온라인 서비스로 가져온 데이터에는 당사의 [개인 정보 처리 방침](https://go.microsoft.com/fwlink/?LinkId=512132)이 적용됩니다. 자세한 내용은 국가별 기능 설명서의 개인 정보 보호 고지 섹션을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

- [전자 송장 발행 개요](e-invoicing-service-overview.md)
- [전자 송장 발행 서비스 관리 시작](e-invoicing-get-started-service-administration.md)
- [전자 송장 발행 시작](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
