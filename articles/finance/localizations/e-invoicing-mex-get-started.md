---
title: 멕시코 전자 청구서 발행 시작
description: 이 주제는 멕시코의 전자 송장 발행을 시작하는 데 도움이 되는 정보를 제공합니다.
author: gionoder
ms.date: 12/01/2020
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
ms.openlocfilehash: f512a6208bc85cd5796ce9515d2bc440f92ea79f
ms.sourcegitcommit: 5033d42a2aac852916d726e40bd98a164d1a837d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2022
ms.locfileid: "8451465"
---
# <a name="get-started-with-electronic-invoicing-for-mexico"></a>멕시코 전자 청구서 발행 시작

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> 멕시코의 전자 송장은 현재 CFDI(Comprobante Fiscal Digital por Internet) 문서와 Microsoft Dynamics 365 Finance 또는 Dynamics 365 Supply Chain Management에 구축된 관련 통합에서 사용할 수 있는 모든 기능을 지원하지 않을 수 있습니다.

이 주제는 멕시코의 전자 송장 발행을 시작하는 데 도움이 되는 정보를 제공합니다. RCS(Regulatory Configuration Services) 및 Finance의 국가/지역별 구성 단계를 안내합니다. 또한 Finance에서 서비스를 통해 CFDI 송장을 제출하기 위해 따라야 하는 단계를 안내하고 처리 결과 및 CFDI 송장의 상태를 검토하는 방법을 설명합니다.

## <a name="prerequisites"></a>전제 조건

이 항목의 단계를 완료하기 전에 [전자 송장 발행 서비스 관리 시작](e-invoicing-get-started-service-administration.md) 및 [전자 송장 발행 시작](e-invoicing-get-started.md)의 단계를 완료해야 합니다.

## <a name="set-up-the-cadena-xslt"></a>Cadena XSLT 설정

CFDI 처리를 위한 세계화 기능에 Cadena XSLT 스키마를 추가하려면 다음 단계를 완료합니다.

1. [SAT 웹 사이트](http://www.sat.gob.mx/sitio_internet/cfd/3/cadenaoriginal_3_3/cadenaoriginal_3_3.xslt)에서 스키마를 다운로드합니다.
2. 스키마를 ZIP 파일로 압축합니다.
3. 새 컨테이너에 대해 서비스 환경에 설정된 Azure Storage 계정에 xslt 파일을 저장합니다.

## <a name="rcs-setup"></a>RCS 설정

RCS 설정 중에 다음 작업을 완료합니다.

1. CFDI 송장 처리를 위한 전자 송장 발행 기능을 가져옵니다.
2. CFDI 송장에 대한 응답을 생성, 제출 및 수신하고 취소에 대한 응답을 제출 및 수신하는 데 필요한 형식 구성을 검토합니다.
3. CFDI 송장 제출 시나리오를 지원하는 이벤트를 구성합니다.
4. CFDI 송장을 위한 전자 송장 발행 기능을 게시합니다.

> [!NOTE]
> "전자 송장 발행 기능"은 전자 송장 발행 서버를 사용하도록 구성 및 게시되는 리소스의 일반 이름입니다. 이 경우 CFDI 송장(MX)은 설정할 전자 송장 발행 기능입니다.

## <a name="import-the-e-invoicing-feature"></a>전자 송장 발행 기능 가져오기

1. RCS 계정에 로그인합니다.
2. **세계화 기능** 작업 영역의 **기능** 섹션에 있는 **전자 청구서 발행** 타일을 선택합니다.
3. **전자 송장 발행 기능** 페이지에서 **가져오기** 를 선택하여 글로벌 리포지토리에서 **CFDI 송장(MX)** 기능을 가져옵니다.

    > [!NOTE]
    > 목록에 기능이 표시되지 않으면 **동기화** 를 선택하고 3단계를 반복합니다.

![CFDI 인보이스(MX) 기능 가져오기.](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

글로벌 리포지토리에서 **CFDI 송장(MX)** 기능을 가져오면 구성 및 작업을 포함한 모든 기능 설정도 가져옵니다.

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a>CFDI 송장(MX) 기능의 새 버전 만들기

예를 들어 URL을 업데이트해야 하는 경우 새 버전을 만들 수 있습니다. 자세한 내용은 [전자 송장 CFDI ](tasks/mx-00010-e-invoicing-cfdi.md)를 참조하십시오.

- **전자 송장 발행 기능** 페이지의 **버전** 탭에서 **새로 만들기** 를 선택합니다.

![새로운 전자 송장 발행 기능 버전 추가.](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a>구성 버전 업데이트

1. 구성 버전(ER 파일 형식 구성)을 관리하려면 **전자 송장 청구 기능** 페이지의 **구성** 탭에서 **추가** 또는 **삭제** 를 선택합니다.

    ![전자 송장 발행 기능 구성 관리.](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    새 버전을 만들면 모든 구성이 마지막으로 게시된 버전에서 상속됩니다. CFDI 송장을 처리하려면 다음 구성이 필요합니다.

    - CFDI 송장(BusinessDocumentService)
    - CFDI 응답 메시지 가져오기
    - CFDI 오류 로그 가져오기
    - CFDI 취소 요청(MX)(BusinessDocumentService)
    - CFDI 송장(BusinessDocumentService)

2. 목록에서 구성 버전을 선택한 다음 **편집** 또는 **보기** 를 선택하여 구성을 편집하거나 볼 수 있는 **형식 디자이너** 페이지를 엽니다.

    ![형식 디자이너 페이지 열기.](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. **형식 디자이너** 페이지를 사용하여 ER 형식 파일 구성을 편집하고 볼 수 있습니다. 자세한 내용은 [전자 문서 구성 만들기](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md)를 참조하십시오.

    ![형식 디자이너 페이지.](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>전자 송장 발행 기능 설정 관리

- 전자 송장 발행 기능 설정을 관리하려면 **전자 송장 발행 기능** 페이지의 **설정** 탭에서 **추가**, **삭제** 또는 **편집** 을 선택합니다.

![전자 송장 발행 기능 설정 관리.](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

승인을 위해 CFDI 송장을 제출하려면(XML 파일 생성, XML 파일 제출 및 응답 처리) **판매 송장** 기능 설정이 필요합니다.

CFDI 송장 취소를 제출하려면 **해지** 및 **취소** 기능 설정이 필요합니다.

### <a name="configure-the-sales-invoice-feature-setup"></a>판매 송장 기능 설정 구성

1. **전자 송장 발행 기능** 페이지의 **설정** 탭에 있는 **기능 설정** 열에서 **판매 송장** 을 선택합니다.
2. 작업, 적용 가능성 규칙 및 변수를 구성하려면 **편집** 을 선택합니다.

    ![전자 송장 발행 기능 설정 편집.](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. 작업 목록을 관리하려면 **기능 버전 설정** 페이지에서 **작업** 탭을 선택합니다. 작업은 이벤트의 전체 실행을 달성하기 위해 순차적으로 실행해야 하는 작업 목록을 정의합니다.

    ![작업 탭.](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | 작업 ID | 작업                   | 작업 이름                                  | 작업 설명                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | 1         | 문서 변환       | 디지털 서명 없이 CFDI 전자 송장 생성 | CFDI 전자 송장을 생성합니다.                                |
    | 2         | 문서 서명            | 디지털 서명                                 | 제출을 위해 전자 송장에 디지털 서명합니다.                |
    | 3         | 멕시코 PAC 서비스 호출 | CFDI 전자 송장 제출                        | WCF(Windows Communication Foundation) 클라이언트는 CFDI 전자 청구서를 제출합니다. |
    | 4         | 응답 처리         | 웹 서비스 응답 분석                 | 웹 서비스 응답을 분석하고 오류 로그를 반환합니다. |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a>멕시코 PAC 웹 서비스에 대한 URL 설정 

1. **기능 버전 설정** 페이지의 **작업** 탭, **작업** 빠른 탭에서 **멕시코 PAC 서비스 호출** 을 선택합니다.
2. **매개 변수** 빠른 탭의 **URL 주소** 필드에 CFDI 송장 제출을 위한 웹 서비스의 URL을 입력합니다.

> [!NOTE]
> **취소** 및 **요청 취소** 기능 설정에 대한 **멕시코 PAC 서비스 호출** 작업의 URL을 업데이트하려면 동일한 단계를 사용합니다.

### <a name="set-up-the-path-for-the-cadena-xlst-schema"></a>Cadena XLST 스키마의 경로 설정

1. **기능 버전 설정** 페이지의 **변수** 탭에서 변수 이름 **DigitalSignatureXSLT** 를 선택합니다.
2. **값** 필터에서 다음을 입력합니다. {"containerUrl":"https://&lt;AccountStorageName&gt;.blob.core.windows.net/&lt;ContainerName&gt;","path":"&lt;RelativePath&gt;"}
   
    이중 슬래시가 있는 <RelativePath> = folder\\folder\\filename에서 ContainerName은 서비스에 사용되는 컨테이너를 나타내야 합니다.
   
    변수의 예는 다음과 같습니다.
    
    {"path":"xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\\dev\\cadena_xslt","containerUrl":https://yyyyyyyyyy.blob.core.windows.net/containername}

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a>전자 송장 발행 환경에 초안 버전 지정

1. **전자 송장 발행 기능** 페이지의 **환경** 탭에서 **사용** 을 선택합니다.
2. **환경** 필드에서 환경을 선택합니다.
3. **유효 기간 시작** 필드에서 환경이 활성화되는 날짜를 선택합니다.
3. **사용** 을 선택합니다.

![전자 송장 발행 환경 활성화.](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a>버전 상태를 완료로 변경

1. **전자 송장 발행 기능** 페이지의 **버전** 탭에서 **초안** 상태의 전자 송장 발행 기능의 버전을 선택합니다.
2. **상태 변경 \> 완료** 를 선택합니다.

## <a name="change-the-version-status-to-published"></a>버전 상태를 게시로 변경

- **전자 송장 발행 기능** 페이지의 **버전** 탭에서 **상태 변경 \> 게시** 를 선택합니다.

## <a name="publish-the-e-invoicing-feature"></a>전자 송장 발행 기능 게시

1. **CFDI 송장(MX)** 기능의 상태를 관리하려면 **전자 송장 발행 기능** 페이지에서 **버전** 탭을 선택합니다.
2. 기능의 상태를 변경하려면 **상태 변경** 을 선택합니다.

![전자 송장 발행 기능의 상태를 변경.](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing--integration-in-finance"></a>Finance에서 전자 송장 발행 통합 설정

Finance에서 전자 송장 발행을 설정하려면 다음 작업을 완료해야 합니다.

1. ER 데이터 모델, ER 데이터 모델 매핑, 그리고 CFDI 송장에 필요한 형식을 가져옵니다.
2. CFDI 송장 업데이트를 위한 응답 유형을 구성합니다. 이러한 응답 유형은 PAC(인증된 인증 공급자) 서버의 응답에 사용됩니다.

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a>ER 데이터 모델, ER 데이터 모델 매핑 및 CFDI 송장에 대한 컨텍스트 구성 가져오기

1. Finance에 로그인합니다.
2. **전자 보고** 작업 영역의 **구성 공급자** 섹션에서 **Microsoft** 타일을 선택합니다. 이 구성 공급자가 **활성** 으로 설정되었는지 확인합니다. 공급자를 **활성** 으로 설정하는 방법에 대한 자세한 내용은 [구성 공급자를 만들고 활성으로 표시](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하십시오.
3. **리포지토리** 를 선택합니다.
4. **글로벌 리포지토리 \> 열기** 를 선택합니다.
5. **송장 모델**, **송장 모델 매핑**, **CFDI 송장 형식(MX)**, **CFDI 송장 취소 요청 형식(MX)** 및 **CFDI 송장 취소 형식(MX)** 을 가져옵니다.

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a>CFDI 송장 처리 기능 켜기

1. **조직 관리 \> 설정 \> 전자 문서 매개 변수** 로 이동합니다.
2. **기능** 탭의 **MX-00010** 및 **MX-00016** 기능 참조 행에서 **사용** 확인란을 선택합니다.

![CFDI 송장 처리 기능 켜기.](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a>ER 구성 가져오기 및 CFDI 송장 업데이트를 위한 응답 유형 설정

#### <a name="import-er-configurations"></a>ER 구성 가져오기

1. **전자 보고** 작업 영역의 **구성 공급자** 섹션에서 **Microsoft** 타일을 선택합니다.
3. **리포지토리** 를 선택합니다.
4. **글로벌 리포지토리 \> 열기** 를 선택합니다.
5. **응답 메시지 모델**, **CFDI 오류 로그 가져오기(MX)** 및 **CFDI 응답 메시지 가져오기(MX)** 를 가져옵니다.

#### <a name="set-up-the-response-types"></a>응답 유형 설정

1. **조직 관리 \> 설정 \> 전자 문서 매개 변수** 로 이동합니다.
2. **전자 문서** 탭에서 **추가** 를 선택합니다.
3. 고객 송장 분개장을 입력한 다음 **테이블 이름** 필드에서 프로젝트 송장을 선택합니다.
4. 각 표에 대해 관련 문서 컨텍스트를 정의합니다.

    - **고객 송장 분개장** 에 **고객 송장 컨텍스트** 를 입력합니다.
    - **프로젝트 송장** 에 **프로젝트 송장 컨텍스트** 를 입력합니다.

4. 전자 송장에서 반환될 수 있고 고객 송장 분개장이나 프로젝트 송장에 포함될 수 있는 응답 유형을 구성하려면 **응답 유형** 을 선택합니다.
5. **새로 만들기** 를 선택한 다음 **응답 유형** 필드에서 **응답** 을 선택합니다.
6. **제출 상태** 필드에서 **보류 중** 을 선택합니다.
7. **모델 매핑** 필드에서 **응답 메시지 가져오기 형식 – 응답 메시지에서 모델 매핑** 을 선택합니다.
8. **저장** 을 선택합니다.
9. **새로 만들기** 를 선택한 다음 **응답 유형** 필드에서 **응답 데이터** 를 선택합니다.
10. **제출 상태** 필드에서 **보류 중** 을 선택합니다.
11. **모델 매핑** 필드에서 **CFDI 응답 데이터 가져오기 형식(세부 정보) – 응답 데이터 가져오기** 를 선택합니다.
12. **저장** 을 선택합니다.

## <a name="process-electronic-invoices-in-finance"></a>Finance에서 전자 송장 처리 

Finance에서 전자 송장 발행을 통해 CFDI 송장을 처리하는 동안 다음 작업을 수행할 수 있습니다.

- CFDI 송장 제출.
- 제출 실행 로그 보기.
- CFDI 송장 취소 제출.

### <a name="submit-cfdi-invoices"></a>CFDI 송장 제출

**구성 가능한 전자 송장 통합** 기능을 켜면 CFDI 송장 제출을 위한 **전자 송장 내보내기/가져오기** 프로세스(**수취 계정 \> 송장 \> 전자 송장**)를 더는 사용할 수 없습니다. **전자 문서 제출** 이라는 새 프로세스로 대체됩니다.

> [!NOTE]
> 새로운 **전자 문서 제출** 프로세스를 사용하기 전에 멕시코 전자 송장에 필요한 설정이 완료되었는지 확인하십시오. 자세한 내용은 [CFDI 레이아웃 버전 3.3](./latam-mex-cfdi-3-3.md)을 참조하십시오.

1. **조직 관리 \> 정기 \> 전자 문서 \> 전자 문서 제출** 로 이동합니다.
2. 문서를 처음 제출하는 경우 항상 **문서 다시 제출** 옵션을 **아니요** 로 설정합니다. 서비스를 통해 문서를 다시 제출해야 하는 경우 이 옵션을 **예** 로 설정합니다.
3. **포함할 레코드** 빠른 탭에서 **필터** 를 선택하여 **문의** 대화 상자를 엽니다. 여기에서 쿼리를 작성하여 제출할 문서를 선택할 수 있습니다.

![CFDI 문서 제출.](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> 서비스를 통해 문서를 처음 제출하려고 하면 전자 송장 발행과의 연결을 확인하라는 메시지가 표시됩니다. **전자 문서 제출 서비스에 연결하려면 여기를 클릭하십시오** 를 선택합니다.

### <a name="view-submission-logs"></a>제출 로그 보기

제출된 모든 문서 또는 하나의 제출된 문서에 대한 제출 로그를 볼 수 있습니다.

#### <a name="view-all-submission-logs"></a>모든 제출 로그 보기

**구성 가능한 전자 송장 통합** 기능을 켜면 문서 제출 프로세스를 추적할 수 있는 새 페이지를 사용할 수 있습니다. 이 페이지를 사용하여 제출된 모든 문서에 대한 제출 로그를 볼 수 있습니다.

1. **조직 관리 \> 정기 \> 전자 문서 \> 전자 문서 제출 로그** 로 이동합니다.
2. 필수 전자 문서를 필터링하기 위해 **문서 유형** 필드에서 **고객 송장 분개장** 을 선택합니다.

    ![제출 로그를 볼 문서 유형을 선택합니다.](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. 작업 창에서 **문의 \> 제출 세부 정보** 를 선택하여 제출 실행 로그의 세부 정보를 봅니다.

    ![제출 로그 세부 정보 보기.](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

제출 로그의 정보는 세 개의 빠른 탭으로 분할됩니다.

- **처리 중인 작업** – 이 빠른 탭에는 RCS에서 설정한 기능 버전에 구성된 작업에 대한 실행 로그가 표시됩니다. **상태** 열은 작업이 정상적으로 실행되었는지를 보여줍니다.
- **작업 파일** – 이 빠른 탭에는 작업 실행 중에 생성된 중간 파일이 표시됩니다. **보기** 를 선택하여 파일을 다운로드하고 볼 수 있습니다.
- **처리 중인 작업 로그** – 이 빠른 탭에는 전자 송장과 대상 웹 서비스 간의 통신 결과가 표시됩니다. 또한 웹 서비스에서 처리하여 반환된 내용이 표시됩니다. **에러 코드** 열에는 인증 웹 서비스에서 반환된 반환 코드가 표시됩니다.

제출된 CFDI 송장이 승인되면 상태가 **승인됨** 으로 업데이트됩니다.

#### <a name="view-submission-logs-from-cfdi-invoices"></a>CFDI 송장의 제출 로그 보기

**구성 가능한 전자 송장 발행 통합** 기능을 켠 후에는 CFDI 송장에서도 제출 로그를 볼 수 있습니다.

1. **수취 계정 \> 문의 및 보고 \> CFDI(전자 송장)** 로 이동합니다.
2. **구성 가능한 전자 송장 발행 통합** 기능이 켜진 후 제출된 CFDI 인보이스를 선택합니다.
3. 작업 창의 **기록** 탭에서 **전자 문서 로그** 를 선택합니다.

![CFDI 송장의 제출 로그 보기.](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> **구성 가능한 전자 송장 발행 통합** 기능이 설정되기 전에 제출된 CFDI 송장의 경우 **기록** 버튼을 사용할 수 있습니다. **구성 가능한 전자 송장 발행 통합** 기능이 켜진 후 제출된 CFDI 송장에는 **기록** 버튼을 사용할 수 없습니다.

### <a name="submit-cancellation-of-cfdi-invoices"></a>CFDI 송장 취소 제출

**구성 가능한 전자 송장 발행 통합** 기능을 켠 후에는 CFDI 송장 취소를 위한 이전 프로세스를 더 이상 사용할 수 없습니다. **전자 문서 제출 로그** 페이지에 포함된 새로운 취소 프로세스로 대체되었습니다.

1. **수취 계정 \> 문의 및 보고 \> CFDI(전자 송장)** 로 이동합니다.
2. CFDI 송장의 상태가 **승인됨** 인 경우 **기능 \> CFDI 취소** 를 선택합니다.
3. **조직 관리 \> 정기 \> 전자 문서 \> 전자 문서 제출 로그** 로 이동합니다.
4. CFDI 송장을 선택한 다음 **기능 \> 관련 제출 보내기** 를 선택합니다.
5. 관련 제출에 대한 설명을 입력한 다음 **확인** 을 선택합니다.

#### <a name="view-cancellation-submission-logs"></a>취소 제출 로그 보기

1. **조직 관리 \> 정기 \> 전자 문서 \> 전자 문서 제출 로그** 로 이동합니다.
2. 고객 송장 분개장 문서만 필터링하기 위해 **문서 유형** 필드에서 **고객 송장 분개장** 을 선택합니다.
3. CFDI 송장을 선택한 다음 작업 창에서 **문의 \> 관련 제출** 을 선택합니다.

    **관련 제출** 페이지에는 지정된 CFDI 송장에 대한 모든 관련 제출 및 제출 상태가 표시됩니다. 다음 그림에서 첫 번째 라인은 CFDI 송장의 승인을 요청한 제출을 나타냅니다. 두 번째 라인은 해당 CFDI 송장을 취소한 제출을 나타냅니다.

    ![취소 제출 로그 보기.](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. 작업 창에서 **문의 \> 제출 세부 정보** 를 선택하여 제출 실행 로그의 세부 정보를 봅니다.

    ![취소 제출 로그 세부 정보 보기.](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a>개인정보보호 통지
**CFDI 멕시코 전자 송장(MX)** 기능을 활성화하려면 조직 세금 등록 ID를 포함한 제한된 데이터를 보내야 할 수 있습니다. 이 데이터는 정부 웹 서비스와의 통합에 필요한 사전 정의된 형식으로 이 세무 당국에 전자 송장을 보내기 위해 세무 당국이 승인한 타사 기관으로 전송됩니다. 관리자는 **조직 관리 \> 설정 \> 전자 문서 매개 변수** 로 이동하여 **CFDI 멕시코 전자 송장(MX)** 기능을 활성화 및 비활성화할 수 있습니다. **기능** 탭을 선택하고 **CFDI 멕시코 전자 송장(MX)** 기능이 포함된 행을 선택한 다음 적절하게 선택합니다. 이러한 외부 시스템에서 Dynamics 365 온라인 서비스로 가져온 데이터에는 당사의 [개인 정보 처리 방침](https://go.microsoft.com/fwlink/?LinkId=512132)이 적용됩니다. 자세한 내용은 국가별 기능 설명서의 개인 정보 보호 고지 섹션을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

- [전자 송장 발행 개요](e-invoicing-service-overview.md)
- [전자 송장 발행 시작](e-invoicing-get-started.md)
- [전자 송장 발행 설정](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
