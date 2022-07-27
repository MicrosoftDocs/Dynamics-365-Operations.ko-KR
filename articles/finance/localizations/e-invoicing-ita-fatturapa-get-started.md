---
title: 이탈리아 FatturaPA와 SDI의 직접 통합 설정
description: 이 항목에서는 이탈리아 전자 송장 발행을 시작하고 이탈리아 FatturaPA와 Exchange 시스템(SDI)의 직접 통합을 설정하는 데 도움이 되는 정보를 제공합니다.
author: abaryshnikov
ms.date: 01/15/2022
ms.topic: article
audience: Application User, Developer
ms.reviewer: kfend
ms.search.region: Global
ms.author: abaryshnikov
ms.search.validFrom: 2021-10-18
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 73cb08c880d7b3459201acfc7aeaa8d0dee1674f
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451432"
---
# <a name="set-up-direct-integration-of-italian-fatturapa-with-sdi"></a>이탈리아 FatturaPA와 SDI의 직접 통합 설정

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> 이탈리아의 전자 송장 발행은 현재 Microsoft Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management에서 전자 송장에 사용할 수 있는 일부 기능을 지원하지 않을 수 있습니다.

이 항목은 이탈리아에서 Finance 및 Supply Chain Management로 전자 송장 발행을 시작하는 데 도움이 되는 정보를 제공합니다. RCS(Regulatory Configuration Services)의 국가/지역별 구성 단계를 안내합니다. 이러한 단계는 [전자 송장 발행 시작](e-invoicing-get-started.md)에 설명된 단계를 보완합니다.

## <a name="prerequisites"></a>전제 조건

이 항목의 단계를 완료하기 전에 다음 전제 조건이 충족되어야 합니다.

- [전자 송장 발행 시작](e-invoicing-get-started.md)의 단계를 완료합니다.
- 글로벌 리포지토리에서 **이탈리아 FatturaPA (IT)** 전자 송장 발행 기능을 RCS로 가져옵니다. 자세한 내용은 이전에 언급한 "전자 송장 발행 시작" 항목의 [Microsoft 구성 공급자에서 전자 송장 발행 기능 가져오기](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider) 섹션을 참조하십시오.
- 필요한 인증서의 링크를 서비스 환경에 추가합니다. 필수 인증서에는 디지털 서명 인증서, 인증 기관(CA) 인증서 및 클라이언트 인증서가 포함됩니다. 자세한 내용은 "전자 송장 발행 서비스 관리 시작" 항목의 [디지털 인증서 비밀 만들기](e-invoicing-get-started-service-administration.md#create-a-digital-certificate-secret) 섹션을 참조하십시오.

## <a name="country-specific-configuration-for-the-italian-fatturapa-it-electronic-invoicing-feature"></a>이탈리아 FatturaPA(IT) 전자 송장 발행 기능에 대한 국가별 구성

연결된 Finance 또는 Supply Chain Management 앱에 애플리케이션 설정을 배포하기 전에 다음 절차를 완료하십시오.

이 섹션은 "전자 송장 발행 시작" 항목의 [애플리케이션 설정의 국가별 구성](e-invoicing-get-started.md#country-specific-configuration-of-application-setup) 섹션을 보완합니다.

### <a name="create-a-new-feature"></a>새 기능 만들기

1. RCS에 로그인합니다.
2. **전자 보고** 작업 영역의 **구성 공급자** 섹션에서 회사의 구성 공급자를 활성으로 표시합니다.
3. **세계화 기능** 작업 영역의 **기능** 섹션에 있는 **전자 청구서 발행** 타일을 선택합니다.
4. **전자 송장 발행 기능** 페이지에서 **추가** \> **기존 기능 기반** 을 선택합니다.
5. **Microsoft 구성 공급자** 에서 **이탈리아 FatturaPA(IT)** 를 기본 기능으로 선택하고 이름을 입력한 다음 **기능 만들기** 를 선택합니다.

### <a name="set-up-application-specific-parameters"></a>애플리케이션별 매개 변수 설정

1. **전자 송장 발행 기능** 페이지에서 추가 편집할 기능을 선택합니다.
2. **버전** 탭에 **초안** 버전이 선택되었는지 확인합니다.
3. **구성** 탭에서 구성을 선택한 다음 **애플리케이션별 매개 변수** 를 선택합니다.
4. **조회** 섹션에서 **Natura 수신인 부담 하위 범주** 조회가 선택되어 있는지 확인합니다.
5. **조건** 섹션에서 **추가** 를 선택합니다.
6. 시스템에 정의된 각 하위 범주에 대한 특정 조건을 추가한 다음 변경 사항을 저장합니다.

    > [!NOTE]
    > **이름** 열에서 특정 값 대신 **\*공백\*** 또는 **\*공백이 아님\*** 자리 표시자 값을 선택할 수 있습니다.

### <a name="configure-a-processing-pipeline-for-export"></a>내보내기를 위한 처리 파이프라인 구성

1. **전자 송장 발행 기능** 페이지에서 추가 편집할 기능을 선택합니다.
2. **설정** 탭에서 **판매 송장** 을 선택하고 **편집** 을 선택합니다.
3. **처리 파이프라인** 섹션에서 작업을 검토하고 모든 필수 필드를 설정합니다.

    - **문서 서명** 작업의 경우 **인증서 이름** 필드에 디지털 서명 인증서를 지정합니다.
    - **제출** 작업의 경우 **URL 주소** 및 **인증서** 필드를 설정합니다. **인증서** 필드의 값은 인증서 체인으로, 첫 번째는 루트 CA 인증서(caentrate.cer)이고 두 번째는 클라이언트 인증서입니다.

4. **유효성 검사** 를 선택하여 모든 필수 필드가 설정되었는지 확인합니다.
5. 변경 내용을 저장하고 페이지를 닫습니다.
6. **설정** 탭에서 **프로젝트 송장** 을 선택하고 **편집** 을 선택합니다.
7. 프로젝트 송장에 대해 3~5단계를 반복합니다.

### <a name="configure-the-processing-pipeline-for-import"></a>가져오기를 위한 처리 파이프라인 구성

1. **전자 송장 발행 기능** 페이지에서 추가 편집할 기능을 선택합니다.
2. **설정** 탭에서 **송장 가져오기** 를 선택하고 **편집** 을 선택합니다.
3. **데이터 채널** 섹션의 **매개 변수** 탭에 있는 **데이터 채널** 필드에 문자열 값을 입력합니다.
4. **적용 가능성 규칙** 탭에서 설정 필드를 설정합니다. 이전 단계에서 **데이터 채널** 필드에 대해 설정한 값을 **값** 필드에 전달하여 기본 **채널** 조항을 사용할 수 있습니다.

    ![적용 가능성 규칙 설정.](media/e-invoicing-ita-fatturapa-get-started-apprules-setup.png)

5. **유효성 검사** 를 선택하여 모든 필수 필드가 설정되었는지 확인합니다.

### <a name="deploy-the-feature"></a>기능 배포

1. 기능을 완료, 게시 및 서비스 환경에 배포합니다. 자세한 내용은 이전에 언급한 "전자 송장 발행 시작" 항목의 [서비스 환경에 전자 송장 발행 기능 배포](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment) 섹션을 참조하십시오.
2. 연결된 애플리케이션에 기능을 배포합니다. 자세한 내용은 이전에 언급한 "전자 송장 발행 시작" 항목의 [전자 송장 발행 기능을 연결된 애플리케이션에 배포](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application) 섹션을 참조하십시오.

### <a name="set-up-finance"></a>Finance 설정

1. Finance 환경에 로그인합니다.
2. **전자 보고** 작업 영역의 **구성 공급자** 섹션에서 **Microsoft** 타일을 선택합니다.
3. **리포지토리** \> **글로벌** \> **열기** 를 선택합니다.
4. **고객 송장 컨텍스트 모델** 및 **공급업체 송장 가져오기(IT)** 구성을 선택하고 가져옵니다.
5. **조직 관리** \> **설정** \> **전자 문서 매개 변수** 로 이동합니다.
6. **기능** 탭에서 **이탈리아 전자 송장** 기능을 찾아 선택한 다음 **사용** 확인란을 선택합니다.
7. **전자 문서** 탭에서 **고객 송장 분개장** 및 **프로젝트 송장** 필드가 [애플리케이션 설정 구성](e-invoicing-get-started.md#configure-the-application-setup)의 정보에 따라 설정되었는지 확인합니다.

### <a name="set-up-vendor-invoice-import"></a>공급업체 송장 가져오기 설정 

1. Finance에서 **전자 보고** 작업 영역의 **구성 공급자** 섹션에서 회사의 구성 공급자를 활성으로 표시합니다.
2. **보고 구성** 을 선택합니다.
3. **고객 송장 컨텍스트 모델** 을 선택한 다음 **구성 만들기** 를 선택합니다.
4. 파생 구성을 만들려면 **이름에서 파생: 고객 송장 컨텍스트, Microsoft** 를 선택합니다.
5. **초안** 버전에서 **디자이너** 를 선택합니다.
6. **데이터 모델** 트리에서 **데이터 원본으로 모델 매핑** 을 선택합니다.
7. **정의** 트리에서 **DataChannel** 을 선택하고 **디자이너** 를 선택합니다.
8. **데이터 원본** 트리에서 **\$Context\_Channel** 컨테이너를 확장합니다.
9. **값** 필드에서 **편집** 을 선택합니다. 
10. 데이터 채널의 이름을 입력합니다. 이름은 최대 10자야 합니다. 이는 RCS의 전자 송장 발행 기능에 대한 데이터 채널의 **데이터 채널** 매개 변수 값과 일치해야 합니다.
11. 변경 사항을 저장한 다음 **보고 구성** \> **완료 구성 버전** 으로 이동합니다.
12. **외부 채널** 탭의 **채널** 선택에서 **추가** 를 선택합니다.
13. **채널** 필드에서 **\$Context Channel** 값을 입력합니다.
14. **설명** 및 **회사** 필드에 값을 입력합니다.
15. **문서 컨텍스트** 필드에 **고객 송장 컨텍스트 모델** 에서 파생된 새 구성을 선택합니다. 매핑 설명은 **데이터 채널 컨텍스트** 여야 합니다.
16. **소스 가져오기** 탭에서 **추가** 를 선택하고 다음 값을 설정합니다.

    - **이름:** OutputFile
    - **데이터 엔터티 이름:** 공급업체 송장 헤더(**데이터 엔터티:** VendorInvoiceHeaderEntity)
    - **모델 매핑:** 공급업체 송장 가져오기(IT)

> [!NOTE]
> 다른 원본에서 공급업체 송장을 가져오는 경우 **\$Context Channel** 값이 다른 여러 외부 채널과 파생 구성을 여러 개 만들 수 있습니다. 예를 들어 다양한 법인의 공급업체 송장을 가져올 수 있습니다.

## <a name="proxy-server-setup"></a>프록시 서버 설정

이 섹션에서는 Exchange 시스템(SDI)과 전자 송장 발행 서비스 간의 통신을 위한 프록시 서비스를 설정하고 구성하는 데 도움이 되는 정보를 제공합니다.

### <a name="create-an-app-registration"></a>앱 등록 만들기

1. 다음 Windows PowerShell 스크립트를 사용하여 서비스 간(S2S) 인증을 위한 자체 서명된 인증서를 만듭니다.

    ```powershell
    $certOutputLocation = "C:\certs\proxytest"
    $certName = "sdiProxyClientS2SCert"
    $certPassword = "123"

    $certCerFile = Join-Path $certOutputLocation "$certName.cer"
    $certPfxFile = Join-Path $certOutputLocation "$certName.pfx"

    $securePassword = ConvertTo-SecureString $certPassword -AsPlainText -Force

    $cert = New-SelfSignedCertificate -KeyLength 2048 -KeyExportPolicy Exportable -FriendlyName "CN=$certName" -CertStoreLocation Cert:\CurrentUser\My -Subject $certName -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider"

    Export-Certificate -Cert $cert -FilePath $certCerFile -type CERT | Out-Null
    Export-PfxCertificate -Cert $cert -FilePath $certPfxFile -Password $securePassword | Out-Null
    ```

2. .pfx 인증서 파일을 Key Vault에 저장한 다음 로컬 복사본을 삭제합니다.
3. [Azure Portal](https://portal.azure.com)에 관리자로 로그인합니다.
4. SDI 프록시 서비스에 대한 앱 등록을 만듭니다.

    1. **앱 등록** 으로 이동하고 등록을 만든 후 다음 값을 설정합니다.

        - **이름:** SDI 프록시 클라이언트
        - **지원되는 계정 유형:** 이 조직 디렉터리의 계정만(단일 테넌트)

    2. **등록** 을 선택한 다음 방금 만든 앱 등록을 선택합니다.
    3. **API 사용 권한** 으로 이동하고 **관리자 동의 부여** 를 선택합니다.
    4. **인증서 및 비밀** 로 이동하고 **인증서 업로드** 를 선택한 다음 S2S 인증을 위한 .cer 인증서 파일을 업로드합니다.
    5. **엔터프라이즈 애플리케이션** 으로 이동하고 만든 앱을 선택합니다.
    6. 앱의 **애플리케이션 ID**(클라이언트 ID) 및 **개체 ID** 값을 저장합니다.
    7. 송장 발행 서비스 팀은 앱에 서비스에 대한 액세스 권한을 부여해야 합니다. 다음 매개 변수의 값을 <D365EInvoiceSupport@microsoft.com>에 보냅니다.

        - AAD 테넌트 ID
        - LCS 환경 ID
        - 애플리케이션 ID
        - 개체 ID

5. RCS에서 서비스 환경의 애플리케이션 목록에 앱을 추가합니다.

    1. **세계화 기능** \> **환경** \> **전자 송장 발행** \> **서비스 환경** 으로 이동하고 환경을 선택합니다.
    2. **애플리케이션** 섹션에서 그리드에 행을 추가하고 앱의 이름과 개체 ID를 입력합니다.

        ![서비스 환경에 애플리케이션 추가.](media/e-invoicing-ita-fatturapa-get-started-add-app-to-env.png)

    3. **저장** 을 선택하고 **게시** 를 선택합니다.

### <a name="create-an-azure-virtual-machine"></a>Azure 가상 머신 만들기

1. [Azure Portal](https://portal.azure.com)에서 **가상 머신** 으로 이동하고 **새로 만들기** 를 선택합니다.
2. **기본** 탭에서 구독 및 리소스 그룹을 선택합니다. 값은 Key Vault 및 Blob Storage가 있는 구독 및 리소스 그룹이어야 합니다.
3. 하위 지역을 선택합니다. 이 값은 Finance 환경이 배포된 하위 지역이어야 합니다.
4. 관리자의 사용자 이름과 암호를 추가하고 Key Vault에 저장합니다.
5. **인바운드 포트 선택** 필드에서 **HTTPS(443)** 및 **RPD(3389)** 를 선택합니다.

    > [!NOTE]
    > 시스템이 프로덕션으로 전환되면 **RDP(3389)** 포트를 비활성화하는 것이 좋습니다. 문제 해결을 위해 가상 머신(VM)에 연결해야 하는 경우 다시 활성화할 수 있습니다.

    ![기본 탭의 필드를 설정하여 Azure VM 만들기.](media/e-invoicing-ita-fatturapa-get-started-create-vm-1.png)

6. **디스크** 탭의 **고급** 빠른 탭에서 **Managed Disks 사용** 확인란을 선택합니다. **임시 OS 디스크** 확인란을 선택 취소합니다.

    ![디스크 탭의 필드를 설정하여 Azure VM을 만듭니다.](media/e-invoicing-ita-fatturapa-get-started-create-vm-2.png)

7. **네트워킹** 탭의 **공용 IP** 필드에서 **새로 만들기** 를 선택합니다.

    ![네트워킹 탭의 필드를 설정하여 Azure VM을 만듭니다.](media/e-invoicing-ita-fatturapa-get-started-create-vm-3.png)

8. **공용 IP 주소 만들기** 대화 상자의 **SKU** 필드 그룹에서 **표준** 옵션을 선택합니다. **할당** 필드 그룹에서 **정적** 옵션을 선택합니다.

    ![공용 IP 주소 만들기.](media/e-invoicing-ita-fatturapa-get-started-create-vm-4.png)

9. **관리** 탭에서 **자동 종료** 확인란을 선택 취소하여 자동 종료를 비활성화합니다.
10. **게스트 OS 업데이트** 필드를 **수동** 으로 설정한 다음 다른 정책을 설정합니다.
11. VM을 검토하고 만듭니다.
12. 새 VM에서 **ID** \> **할당된 시스템** 으로 이동하고 **상태** 옵션을 **켜짐** 으로 설정합니다.
13. VM에 Key Vault에 대한 액세스 권한을 부여합니다.

    1. Key Vault에서 **액세스 제어(IAM)** \> **역할 할당** 으로 이동합니다.
    2. **역할 할당 추가** 를 선택하고 다음 필드를 설정합니다.

        1. **역할** 필드에서 **Key Vault 비밀 사용자** 를 지정합니다.
        2. **액세스 권한 할당** 필드에서 **가상 머신** 을 지정합니다.
        3. **구독** 필드에서 구독을 지정합니다.
        4. **선택** 필드에서 VM을 지정합니다.

    3. **액세스 정책** 으로 이동합니다.
    4. **액세스 정책 추가** 를 선택하고 다음 필드를 설정합니다.

        1. **보안 주체 선택** 필드에서 VM을 선택합니다.
        2. **인증서** 섹션에서 사용 권한 **목록** 및 **가져오기** 를 선택합니다.

14. [Azure Portal](https://portal.azure.com)에서 **공용 IP 주소** 로 이동하고 VM에서 만든 IP 주소를 선택합니다.
15. **구성** 으로 이동하고 DNS(Domain Name System) 이름을 입력합니다.

### <a name="prepare-the-proxy-service-environment"></a>프록시 서비스 환경 준비

프록시 서비스가 호스팅되는 시스템에서 다음 단계를 따릅니다.

1. 원격 데스크톱 연결을 사용하여 VM에 연결합니다.
2. 로컬 컴퓨터 인증서 스냅인을 엽니다. 자세한 내용은 [방법: MMC 스냅인으로 인증서 보기](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in)를 참조하십시오.
3. 프로덕션을 위한 **caentrate.cer** 인증서와 테스팅을 위한 **CAEntratetest.cer** 인증서를 [신뢰할 수 있는 루트 인증 기관 저장소](/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores)로 가져옵니다. (**CAEntratetest.cer** 은 기관에서 제공한 루트 CA 인증서입니다.)
4. 제어판에서 **Windows 기능 켜기/끄기** 를 열거나 서버 운영 체제(OS)의 **서버 관리자** \> **역할 및 기능 추가** 로 이동하여 다음 인터넷 정보 서비스(IIS) 기능을 켭니다.

    - 웹 관리 도구
        - IIS 관리 콘솔
    - World Wide Web 서비스
        - 응용 프로그램 개발 기능
            - .NET 확장성 4.7(또는 4.8)
            - ASP
            - ASP.NET 4.7(또는 4.8)
            - CGI
            - ISAPI 확장
            - ISAPI 필터
        - 일반 HTTP 기능
            - 기본 문서
            - 디렉터리 검색
            - HTTP 오류
            - 정적 콘텐츠
        - 상태 및 진단
            - HTTP 로깅
            - 추적
        - 성능 기능
            - 정적 콘텐츠 압축
        - 보안
            - 요청 필터링

    ![IIS 기능 켜기.](media/e-invoicing-ita-fatturapa-get-started-turnon-features.png)

### <a name="set-up-the-sdi-proxy-service-in-iis"></a>IIS에서 SDI 프록시 서비스 설정

1. Microsoft Dynamics Lifecycle Services(LCS)에서 공유 에셋 라이브러리로 이동하고 자산 유형으로 **데이터 패키지** 를 선택합니다.
2. **전자 송장 발생 서비스 SDI 프록시** 를 찾고 VM으로 다운로드합니다.
3. 서비스를 구성합니다.

    1. 다운로드한 **전자 송장 발행 서비스 SDI 프록시** 보관 폴더의 압축을 풉니다.
    2. **src\\FattureService** 폴더에서 **appsettings.json** 파일을 열고 다음 매개 변수를 설정합니다.

        - **KeyVaultUri** – 송장 발행 서비스에 대한 클라이언트 인증서를 저장하는 Key Vault의 주소를 지정합니다.
        - **TenantId** – 고객 테넌트의 GUID(Globally Unique Identifier)를 지정합니다.
        - **EnvironmentId** – LCS 환경의 ID를 지정합니다.
        - **ClientId** – 고객 테넌트에서 중간 서비스 앱 등록의 앱 ID를 지정합니다.
        - **ClientCertificateName** – Key Vault에서 S2S 인증서의 이름을 지정합니다.
        - **SecurityServiceClientOptions.Endpoint** – 보안 서비스의 URL을 지정합니다.
        - **SecurityServiceClientOptions.Resource** – 토큰을 얻을 범위를 지정합니다.
        - **InvoicingServiceClientOptions.Endpoint** – 송장 발행 서비스의 엔드포인트를 지정합니다. 이 값은 RCS 및 Finance에 사용되는 것과 동일한 엔드포인트여야 합니다.
        - **InvoicingServiceClientOptions.ServiceEnvironmentId** – 서비스 환경의 이름을 지정합니다. 이 값은 Finance 환경의 이름이어야 합니다.
        - **NotificationsFolder** – 수신 알림 파일을 저장할 폴더를 지정합니다.

    3. **web.config** 파일에서 다음 라인을 찾아 프록시 서버 인증서의 지문을 추가합니다.

        `<serviceCertificate findValue="[certificate thumbprint]" storeLocation="LocalMachine" storeName="My" x509FindType="FindByThumbprint">`

        > [!TIP]
        > 시스템이 프로덕션으로 전환되면 web.config 파일에서 일부 값을 변경하여 수집되는 로그 정보의 양을 줄이고 디스크 공간을 절약할 수 있습니다. **\<system.diagnostics\>\<source\>** 노드에서 **switchValue** 의 값을 **Critical,Error** 로 변경합니다. 자세한 내용은 [MS Service Trace Viewer](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe)를 참조하십시오.

4. IIS 관리자를 엽니다. 왼쪽 트리에 루트 노드를 유지합니다. 오른쪽에서 **서버 인증서** 를 선택합니다.

    ![IIS 관리자에서 서비스 인증서 선택.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-1.png)

5. 메뉴를 열고 **가져오기** 를 선택합니다.
6. **인증서 가져오기** 대화 상자의 **인증서 파일(.pfx)** 필드에 프록시 서버 인증서의 .pfx 파일 경로를 지정합니다.

    ![프록시 서비스 인증서 파일을 지정합니다.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-2.png)

7. **사이트** 를 길게 선택하고(또는 오른쪽 버튼으로 클릭) **웹 사이트 추가** 를 선택합니다.
8. **웹 사이트 추가** 대화 상자의 **사이트 이름** 필드에 사이트 이름을 입력합니다.
9. **실제 경로** 필드에 **src\\FattureService** 폴더를 지정합니다.
10. **바인딩 유형** 필드에 **https** 를 선택합니다.
11. **호스트 이름** 필드에 호스트 이름을 지정합니다.
12. **IP 주소** 및 **포트** 필드는 기본값으로 둡니다.
13. SDI는 해당 기술을 지원하지 않으므로 **서버 이름 표시 필요** 확인란이 선택 취소되었는지 확인합니다.
14. **SSL 인증서** 필드에서 가져온 프록시 서버 인증서를 선택합니다.
15. **애플리케이션 풀** 필드에서 사이트에 대한 풀을 지정하고 이름(예: **SdiAppPool**)을 기록해 둡니다.

    ![웹사이트 추가.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-1.png)

16. 웹사이트 만들기를 완료한 후 **SSL 설정** 메뉴를 엽니다.

    ![SSL 설정 메뉴 열기.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-2.png)

17. **SSL 필요** 확인란을 선택한 다음 **클라이언트 인증서** 필드 그룹에서 **필수** 옵션을 선택합니다.

    ![SSL 설정 구성.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-3.png)

18. **Directory 검색** 을 열고 **사용** 을 선택합니다.
19. 아무 웹 브라우저에서 **serverDNS/TrasmissioneFatture.svc** 로 이동합니다. 서비스에 대한 표준 페이지가 표시됩니다.

    ![브라우저에서 서비스 확인.](media/e-invoicing-ita-fatturapa-get-started-proxy-open-browser.png)

20. 로그 및 파일을 저장할 다음 폴더를 만듭니다.

    - **C:\\Logs\\** – 여기에 로그 파일을 저장합니다. 이러한 파일은 [MS Service Trace Viewer](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe)로 볼 수 있습니다.
    - **C:\\Files\\** – 여기에 모든 응답 파일을 저장합니다.

21. 파일 탐색기에서 **Logs** 및 **Files** 폴더에 대해 **네트워크 서비스** 및 **IIS AppPool\\SdiAppPool**(또는 기본 풀을 사용하는 경우 **IIS AppPool\\DefaultAppPool**) 액세스 권한을 부여합니다.

    1. 폴더 중 하나를 길게 선택하고(또는 오른쪽 버튼으로 클릭) **속성** 을 선택합니다.
    2. **속성** 대화 상자의 **보안** 탭에서 **편집** 을 선택합니다.
    3. 목록에 없는 경우 사용자를 추가합니다.
    4. 다른 폴더에 대해 1~3단계를 반복합니다.

    ![서비스 사용자에게 권한 추가.](media/e-invoicing-ita-fatturapa-get-started-proxy-add-user.png)

## <a name="privacy-notice"></a>개인정보보호 통지 

**이탈리아 전자 송장** 기능을 활성화하려면 제한된 데이터를 보내야 할 수 있습니다. 이 데이터에는 조직의 납세자 등록 ID가 포함됩니다. 관리자는 이탈리아 전자 송장 기능을 활성화 및 비활성화할 수 있습니다. 기능을 비활성화하려면 다음 단계를 따릅니다.

1. **조직 관리** \> **설정** \> **전자 문서 매개 변수** 로 이동합니다.
2. **기능** 탭에서 **이탈리아 전자 송장** 기능을 포함하는 행을 선택한 다음 **지금 사용 안 함** 을 선택합니다.

이러한 외부 시스템에서 Dynamics 365 온라인 서비스로 가져온 데이터에는 당사의 [개인 정보 처리 방침](https://go.microsoft.com/fwlink/?LinkId=512132)이 적용됩니다. 자세한 내용은 국가/지역별 기능 설명서의 "개인 정보 보호 고지" 섹션을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

- [전자 송장 발행 개요](e-invoicing-service-overview.md)
- [전자 송장 발행 서비스 관리 시작](e-invoicing-get-started-service-administration.md)
- [전자 송장 발행 시작](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
