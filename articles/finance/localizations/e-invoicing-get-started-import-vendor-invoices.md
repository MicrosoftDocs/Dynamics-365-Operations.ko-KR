---
title: 전자 송장 발행 서비스를 사용하여 공급업체 송장 가져오기
description: 이 항목에서는 전자 송장 발행 서비스를 사용하여 공급업체 송장을 가져오는 방법에 대한 정보를 제공합니다.
author: gionoder
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c28adbfe532e77a52cab7625b9539d1e8e528bea
ms.sourcegitcommit: 19f0e69a131e9e4ff680eac13efa51b04ad55a38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2022
ms.locfileid: "8451405"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>전자 송장 발행 서비스를 사용하여 공급업체 송장 가져오기

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

이 항목은 전자 송장 발행 서비스를 사용하여 공급업체 송장을 가져오기 시작하는 데 도움이 되는 정보를 제공합니다. 여기에서는 공급업체로부터 전자 공급업체 송장을 받기 위해 따라야 하는 RCS(Regulatory Configuration Services), Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management의 구성 단계를 안내합니다.

## <a name="set-up-vendor-invoice-import-in-rcs"></a>RCS에서 공급업체 송장 가져오기 설정
RCS에서 공급업체 송장 가져오기를 설정하려면 다음 단계를 따릅니다.

1. [일반적으로 사용 가능한 전자 송장 발행 기능](e-invoicing-configuration-rcs.md#generally-available-features)의 목록을 참조하십시오.
2. 전자 송장 발행 기능을 선택하여 가져옵니다. 자세한 내용은 [Microsoft 구성 공급자에서 전자 송장 발행 기능 가져오기](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider)를 참조하십시오.
3. 조직을 위한 전자 송장 발행 기능을 만듭니다. 자세한 내용은 [조직 공급자에서 전자 송장 발행 기능 만들기](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider)를 참조하십시오.

## <a name="configure-an-email-account-channel"></a>이메일 계정 채널 구성

만든 전자 송장 발행 기능이 이메일로 수신된 첨부 파일에서 전자 공급업체 송장을 가져오는 경우 이메일 계정 채널을 구성합니다.

1. RCS에서 생성한 전자 송장 발행 기능을 선택합니다. **초안** 상태의 버전을 선택했는지 확인합니다.
2. **설정** 탭의 그리드에서 기능 설정을 선택한 다음 **편집** 을 선택합니다.
3. **매개 변수** 필드 그룹의 **데이터 채널** 탭에서 **데이터 채널** 필드에 채널 이름을 입력합니다. 채널 이름은 10자 이하여야 합니다.
4. **서버 주소** 필드에 이메일 계정 공급자를 입력합니다. 예를 들어 **https://outlook.live.com/** 의 서버 주소는 **imap-mail.outlook.com** 입니다.
5. **서버 포트** 필드에 이메일 계정 공급자가 사용하는 포트를 입력합니다. 예를 들어 **https://outlook.live.com/** 의 서버 포트는 **993** 입니다.
6. **사용자 이름 비밀** 필드에 이메일 사용자 계정의 ID가 포함된 Key Vault 비밀의 이름을 입력합니다. 이 비밀은 Azure Key Vault에서 만들고 서비스 환경에서 설정해야 합니다. 
7. **사용자 암호 비밀** 필드에 이메일 사용자 계정의 암호가 포함된 Key Vault 비밀의 이름을 입력합니다.
8. 선택적 - **보낸 사람 필터**, **제목 필터**, **날짜** 필드에 값을 입력합니다.
9. 메일이 있을 사서함 폴더의 이름을 입력합니다.

    - 가져온 위치: **기본 폴더**
    - 처리 후 저장: **보관 폴더**
    - 처리 실패 후 저장: **오류 폴더** 사서함에 이러한 폴더를 만들 필요는 없습니다. 폴더는 첫 번째 전자 송장 가져오기 및 처리 후에 자동으로 생성됩니다. 
   
10. **첨부 파일 필터** 필터 그룹에서 파일 필터링 정보를 추가합니다. 정의된 필터를 충족하는 첨부 파일만 처리됩니다. 예를 들어 확장자가 xml인 첨부 파일에 대해 "\*.xml"을 설정할 수 있습니다. 첨부 파일의 이름은 설정하는 동안 Dynamics 365 Finance 또는 Dynamics 365 Supply Chain Management에서 사용됩니다. 
11. **적용 가능성 규칙** 탭에서 필요에 따라 기준을 검토하고 업데이트합니다. **채널** 필드는 이전에 제공한 **데이터 채널** 과 같아야 합니다. 자세한 내용은 [적용 가능성 규칙](e-invoicing-configuration-rcs.md#applicability-rules)을 참조하십시오.
12. **저장** 을 선택하고 페이지를 닫습니다.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Microsoft SharePoint 채널 구성

전자 송장 발행 기능이 SharePoint 폴더에 있는 파일에서 전자 공급업체 송장을 가져오는 경우 Microsoft SharePoint 채널을 구성합니다.

1. RCS에서 생성한 전자 송장 발행 기능을 선택합니다. **초안** 상태의 **버전** 을 선택했는지 확인합니다.
2. **설정** 탭의 그리드에서 기능 설정을 선택한 다음 **편집** 을 선택합니다.
3. **데이터 채널** 탭의 **매개 변수** 필드 그룹에서 **SharePoint 주소** 를 선택하고 SharePoint URL을 입력합니다.
4. **서버 포트** 를 선택하고 이메일 계정 공급자가 사용하는 포트를 입력합니다.
5. **애플리케이션 ID** 를 선택하고 SharePoint 클라이언트의 ID가 포함된 Key Vault 비밀의 이름을 입력합니다.
6. **애플리케이션 비밀** 을 선택하고 SharePoint 클라이언트의 암호가 포함된 Key Vault 비밀의 이름을 입력합니다.
7. **파일 필터** 를 선택합니다. 가져올 전자 공급업체 송장이 포함된 파일을 필터링 마스크를 검토하고 업데이트합니다.
8. **적용 가능성 규칙** 탭에서 필요에 따라 기준을 검토하고 업데이트합니다. 자세한 내용은 [적용 가능성 규칙](e-invoicing-configuration-rcs.md#applicability-rules)을 참조하십시오.
9. **저장** 을 선택하고 페이지를 닫습니다.

### <a name="deploy-an-electronic-invoicing-feature"></a>전자 송장 발행 기능 배포

전자 송장 발행 기능을 배포하려면 [서비스 환경에 전자 송장 발행 기능 배포](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment)를 참조하십시오.

## <a name="set-up-vendor-invoice-import-in-finance-or-supply-chain-management"></a>Finance 또는 Supply Chain Management에서 공급업체 송장 가져오기 설정
다양한 유형의 공급업체 송장 가져오기를 설정하려면 다음 두 섹션의 단계를 완료합니다.

### <a name="import-brazilian-nf-e-from-email"></a>이메일에서 브라질 NF-e 가져오기

1. 올바른 법인으로 Finance 또는 Supply Chain Management 환경에 로그인합니다.
2. **조직 관리** > **설정** > **전자 문서 매개 변수** 로 이동합니다.
3. **기능** 탭에서 **NF-e Federal - 브라질 전자 송장** 이 선택되어 있는지 확인합니다.
4. **외부 채널** 탭의 **채널** 필드 그룹에서 **추가** 를 선택합니다.
5. **채널** 필드에 **NFe**(RCS에서 전자 송장 발행 기능의 데이터 채널 구성에 제공된 채널 이름)를 입력합니다.
6. **설명** 필드에 설명을 입력합니다. **회사** 필드에서 법인을 선택합니다.
7. **문서 컨텍스트** 필드에서 **회계 문서 컨텍스트 – 고객 송장 컨텍스트 모델** 을 선택합니다.
8. **가져오기 원본** 필드 그룹에서 **추가** 를 선택합니다.
9. **이름** 필드에 **XmlFile**(RCS의 전자 송장 발행 기능에 대한 데이터 채널 구성에 제공된 **첨부 파일 필터** 의 이름)을 입력합니다.
10. **설명** 필드에 설명을 입력하고 **데이터 엔터티 이름** 필드에 **수신된 NF-e XML 문서** 를 선택합니다.
11. **모델 매핑** 필드에서 **NF-e 메일 가져오기 – NF-e 이메일 가져오기(BR)** 를 선택하고 **저장** 을 선택합니다.
12. **전자 문서** 탭의 **전자 보고** 필드 그룹에서 **추가** 를 선택하고 **테이블 이름** 필드에서 **수신된 NF-e XML 문서** 를 선택합니다.
13. **문서 컨텍스트** 필드에서 **회계 문서 컨텍스트 문의 – 고객 송장 컨텍스트** 를 선택합니다.
14. **전자 문서 모델 매핑** 필드에서 **매핑 문의 – 회계 문서 매핑** 을 선택합니다.
15. **응답 유형** 을 선택한 다음 **새로 만들기** 를 선택합니다.
16. **응답 유형** 필드에 **응답** 을 입력합니다. **제출 상태** 필드에 **예약** 을 입력합니다.
17. **모델 매핑** 필드에서 **응답 메시지에서 모델 매핑 – 응답 메시지 가져오기 형식** 을 선택합니다.
18. **저장** 을 선택한 다음 페이지를 닫습니다.

### <a name="import-peppol-electronic-vendor-invoices"></a>PEPPOL 전자 공급업체 송장 가져오기

1. **전자 보고** 작업 공간으로 이동하고 **보고 구성** 을 선택합니다.
2. **고객 송장 컨텍스트 모델** 을 선택한 다음 **구성 만들기** > **이름에서 파생: 고객 송장 컨텍스트 모델, Microsoft** 를 선택하여 파생 구성을 만듭니다.
3. **초안** 버전에서 **데이터 모델** 트리에 **디자이너** 를 선택하고 **데이터 원본으로 모델 매핑** 을 선택합니다.
4. **정의** 트리에서 **DataChannel** 을 선택하고 **디자이너** 를 선택합니다.
5. **데이터 원본** 트리에서 **$Context\_Channel** 컨테이너를 확장합니다. **값** 필드에서 **편집** 을 선택하고 데이터 채널 이름을 입력합니다. 이것은 RCS에서 전자 송장 발행 기능의 데이터 채널 구성에 제공된 채널 이름입니다. 
7. **저장** 을 선택하고 페이지를 닫습니다.
8. 페이지를 닫습니다.
9. **고객 송장 컨텍스트 모델** 에서 방금 만든 파생 구성을 선택하고 **버전** 빠른 탭에서 **상태 변경** > **완료** 를 선택합니다.
10. **조직 관리** > **설정** > **전자 문서 매개 변수** 로 이동하고 **기능** 탭에서 **PEPPOL 글로벌 전자 송장** 이 선택되어 있는지 확인합니다. 
11. **외부 채널** 탭의 **채널** 필드 그룹에서 **추가** 를 선택합니다.
12. **채널** 필드에 데이터 채널 이름을 입력하고 **설명** 필드에 설명을 입력합니다.
13. **회사** 필드에서 법인을 선택합니다. 
14. **문서 컨텍스트** 필드에 **고객 송장 컨텍스트 모델** 에서 새로 파생된 구성을 선택합니다. 매핑 설명은 **데이터 채널 컨텍스트** 여야 합니다.
15. **가져오기 원본** 필드 그룹에서 **추가** 를 선택합니다.
16. **이름** 필드에 **첨부 파일 필터 이름** 을 입력하고 **데이터 엔터티 이름** 필드에 **공급업체 송장 헤더** 를 입력합니다.
17. **모델 매핑** 필드에서 **공급업체 송장 가져오기 - 공급업체 송장 가져오기** 를 선택합니다.
18. **저장** 을 클릭한 다음 페이지를 닫습니다.


## <a name="receive-electronic-invoices"></a>전자 송장 수신

전자 송장 발행 서비스는 데이터 채널에서 송장을 가져오는 동안 두 단계를 수행합니다.

1. 사서함에 액세스하고 이메일을 읽습니다.
2. 이메일을 처리합니다. 
    
이 두 단계를 수행하려면 클라이언트가 각 단계의 서비스를 수동으로 호출해야 합니다. 단, 일괄 처리로 전자 문서를 수신하도록 설정하기를 권장합니다.

전자 송장을 받으려면 다음 단계를 따릅니다.

1. **조직 관리** > **정기** > **전자 문서** > **전자 문서 수신** 으로 이동합니다.
2. **확인** 을 선택한 다음 페이지를 닫습니다.


## <a name="view-receive-logs-for-electronic-invoices"></a>전자 송장 수신 로그 보기

전자 송장 수신 로그를 보려면 **조직 관리** > **정기** > **전자 문서** > **전자 문서 수신 로그** 로 이동합니다.
정상적으로 처리된 송장이 표시되지 않으면 테이블 필터를 제거합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
