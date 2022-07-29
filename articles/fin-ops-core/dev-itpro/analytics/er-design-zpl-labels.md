---
title: ZPL 라벨 인쇄를 위한 새로운 ER 솔루션 설계
description: 이번에는 Zebra 프로그래밍 언어(ZPL) 라벨을 인쇄하기 위한 새로운 전자 보고(ER) 솔루션을 설계하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 4fb89f4b56ce8189482bf1a86582ef7e3684b15a
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2022
ms.locfileid: "8461046"
---
# <a name="design-a-new-er-solution-to-print-zpl-labels"></a>ZPL 라벨 인쇄를 위한 새로운 ER 솔루션 설계

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

이번에는 시스템 관리자, 전자 보고 개발자 또는 전자 보고 함수 컨설턴트 역할의 사용자가 [전자 보고(ER)](general-electronic-reporting.md) 프레임워크의 매개 변수를 구성하고 창고의 데이터에 액세스하기 위해 새 ER 솔루션의 필수 ER [구성](general-electronic-reporting.md#Configuration)을 설계하는 방법에 대해 설명합니다. 관리 시스템, Zebra 프로그래밍 언어(ZPL) II 형식으로 맞춤형 창고 위치 라벨을 생성합니다. 이러한 단계는 **USRT** 회사에서 완료할 수 있습니다.

## <a name="business-scenario"></a>비즈니스 시나리오

귀하는 Microsoft Dynamics 365 Finance에서 창고 관리를 구현한 회사를 대표합니다. 모든 창고 위치에는 바코드가 포함된 접착식 라벨이 부착되어 있어야 합니다. 창고 직원은 휴대용 바코드 판독기를 사용하여 바코드를 스캔합니다.

모든 창고 위치는 가동 전 활동 범위에서 레이블이 지정되었습니다. 그러나 기존 레이블이 손상되거나 창고 선반이 재구성된 경우 주문형 창고 위치 레이블을 인쇄할 수도 있어야 합니다. 최근에 출시된 ER 함수를 사용하여 창고 감독자가 라벨을 감열식 라벨 프린터로 직접 인쇄할 수 있는 새로운 ER 솔루션을 구성할 수 있습니다.

## <a name="configure-the-er-framework"></a>ER 프레임워크 구성

ER 프레임워크 구성의 단계에 따라 [ER 매개 변수의 최소 집합](er-quick-start2-customize-report.md#ConfigureFramework)을 설정합니다. ER 프레임워크를 사용하여 새 ER 솔루션을 설계하기 시작하기 전에 이 설정을 완료해야 합니다.

## <a name="design-a-domain-specific-data-model"></a>도메인별 데이터 모델 설계

창고 관리 도메인에 대한 [데이터 모델](er-overview-components.md#data-model-component) 구성 요소를 포함하는 새 ER 구성을 작성하십시오. 이 데이터 모델은 나중에 창고 위치 레이블을 생성하기 위해 ER 형식을 디자인할 때 데이터 소스로 사용됩니다.

### <a name="import-a-data-model-configuration"></a>데이터 모델 구성 가져오기

Microsoft에서 제공하는 XML 파일에서 필요한 데이터 모델을 가져오려면 다음 단계를 따르십시오. 또는 다음 섹션에 설명된 대로 고유한 데이터 모델을 만들 수 있습니다.

1. [Warehouse model.version.1.xml](https://download.microsoft.com/download/9/f/1/9f136e9b-bf5f-403a-b089-a2b2ed1da2ba/Warehouse-model.version.1.xml) 파일을 다운로드하고 로컬 컴퓨터에 저장하십시오.
2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **전자 보고** 작업 영역에서 **보고 구성** 을 선택합니다.
4. **구성** 페이지의 작업 창에서 XML 파일에서 **Exchange** \> **로드** 를 선택합니다.
5. **찾아보기** 를 선택한 다음 **Warehouse model.version.1.xml** 파일을 찾아 선택합니다.
6. **확인** 을 선택하여 구성을 가져옵니다.

![구성 페이지에서 가져온 ER 데이터 모델 구성.](./media/er-design-zpl-labels-imported-model.png)

### <a name="create-a-data-model-configuration"></a>데이터 모델 구성 만들기

Microsoft에서 제공하는 데이터 모델 파일을 가져오는 대신 처음부터 데이터 모델을 만들 수 있습니다. 이 작업을 완료하는 방법을 보여주는 예는 [새 데이터 모델 구성 만들기](er-quick-start1-new-solution.md#DesignDataModel)를 참조하십시오.

### <a name="review-the-data-model"></a>데이터 모델 검토

**데이터 모델 디자이너** 페이지에서 구성된 데이터 모델의 편집 가능한 버전을 볼 수 있습니다.

![데이터 모델 디자이너 페이지의 ER 데이터 모델 구조.](./media/er-design-zpl-labels-model.png)

## <a name="design-a-model-mapping-for-the-configured-data-model"></a>구성된 데이터 모델에 대한 모델 매핑 설계

전자 보고 개발자 역할의 사용자는 웨어하우스 데이터 모델에 대한 [모델 매핑](er-overview-components.md#model-mapping-component) 구성 요소를 포함하는 새 ER 구성을 생성해야 합니다. 이 구성 요소는 해당 Dynamics 365 Finance 앱에 대해 구성된 데이터 모델을 구현합니다. 런타임 시 구성된 데이터 모델을 애플리케이션 데이터로 채우는 데 사용할 애플리케이션 개체를 지정하도록 구성해야 합니다. 이 작업을 완료하려면 창고 관리 비즈니스 도메인의 데이터 구조가 재무에서 구현되는 방식을 이해해야 합니다.

### <a name="import-a-model-mapping-configuration"></a>모델 매핑 구성 가져오기

Microsoft에서 제공하는 XML 파일에서 필요한 모델 매핑을 가져오려면 다음 단계를 따르십시오. 또는 다음 섹션에 설명된 대로 고유한 모델 매핑을 생성할 수 있습니다.

1. [웨어하우스 모델 mapping.version.1.1.xml](https://download.microsoft.com/download/1/c/c/1cc94d28-3d90-4ffd-a118-77d6c322904f/Warehouse-model-mapping.version.1.1.xml) 파일을 다운로드하고 로컬 컴퓨터에 저장합니다.
2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **전자 보고** 작업 영역에서 **보고 구성** 을 선택합니다.
4. **구성** 페이지의 작업 창에서 XML 파일에서 **Exchange** \> **로드** 를 선택합니다.
5. **찾아보기** 를 선택한 다음 **웨어하우스 모델 mapping.version.1.1.xml** 파일을 찾아 선택합니다.
6. **확인** 을 선택하여 구성을 가져옵니다.

![구성 페이지에서 가져온 ER 모델 매핑 구성.](./media/er-design-zpl-labels-imported-mapping.png)

### <a name="create-a-model-mapping-configuration"></a>모델 매핑 구성 만들기

Microsoft에서 제공하는 모델 매핑 파일을 가져오는 대신 처음부터 모델 매핑을 생성할 수 있습니다. 이 작업을 완료하는 방법을 보여주는 예는 [새 모델 매핑 구성 만들기](er-quick-start1-new-solution.md#CreateModelMapping)를 참조하십시오.

### <a name="review-the-model-mapping"></a>모델 매핑 검토

**모델 매핑 디자이너** 페이지에서 구성된 모델 매핑의 편집 가능한 버전을 볼 수 있습니다.

![모델 매핑 디자이너 페이지의 ER 모델 매핑 구조입니다.](./media/er-design-zpl-labels-mapping.png)

## <a name="design-a-format"></a>형식을 디자인하다

전자 보고 함수 컨설턴트 역할의 사용자는 [형식](er-overview-components.md#format-component) 구성 요소가 포함된 새 ER 구성을 생성해야 합니다. 이 구성 요소를 구성하려면 ZPL II 코드를 사용하여 창고 위치 레이블의 레이아웃을 지정합니다.

### <a name="import-a-format-configuration"></a>형식 구성 가져오기

다음 단계에 따라 Microsoft에서 제공하는 XML 파일에서 필요한 형식을 가져옵니다. 또는 다음 섹션에 설명된 대로 고유한 형식을 만들 수 있습니다.

1. [창고 위치labels.version.1.1.xml](https://download.microsoft.com/download/5/7/5/5758b551-69a5-45bd-a2b2-21c3db73a6fc/Warehouse-location-labels.version.1.1.xml) 파일을 다운로드하고 로컬 컴퓨터에 저장하십시오.
2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **전자 보고** 작업 영역에서 **보고 구성** 을 선택합니다.
4. **구성** 페이지의 작업 창에서 XML 파일에서 **Exchange** \> **로드** 를 선택합니다.
5. **찾아보기** 를 선택한 다음 **창고 위치labels.version.1.1.xml** 파일을 찾아 선택하십시오.
6. **확인** 을 선택하여 구성을 가져옵니다.

![구성 페이지에서 가져온 ER 형식 구성.](./media/er-design-zpl-labels-imported-format.png)

### <a name="create-a-format-configuration"></a>형식 구성 만들기

Microsoft에서 제공하는 형식 파일을 가져오는 대신 처음부터 형식을 만들 수 있습니다. 이 작업을 완료하는 방법을 보여주는 예는 [새 형식 구성 만들기](er-quick-start1-new-solution.md#FormatCreate)를 참조하십시오.

### <a name="review-the-format"></a>형식 검토

**형식 디자이너** 페이지에서 구성된 형식의 편집 가능한 버전을 볼 수 있습니다.

![형식 디자이너 페이지의 ER 형식 구조입니다.](./media/er-design-zpl-labels-format.png)

이 형식의 `model.Location.Label` 데이터 소스는 다음 정보가 포함된 레이블을 생성하도록 구성됩니다.

- 텍스트로 된 창고 제목
- 창고 제목을 바코드로
- 위치 제목
- 숫자 확인

데이터 원본에 대한 **수식 디자이너** 페이지에서 레이블을 생성하는 데 사용되는 ER 수식은 원하는 레이아웃의 정보를 결합하는 `CONCATENATE` 함수를 포함합니다.

![수식 디자이너 페이지의 데이터 원본에 대한 수식입니다.](./media/er-design-zpl-labels-review-formula.png)

> [!TIP]
> 레이블 레이아웃은 위치 제목과 확인 숫자가 레이블 중앙에 정렬되도록 설계되었습니다. 그러나 ZPL II는 바코드의 중앙 정렬을 지원하지 않습니다. 따라서 `model.Location.Warehouse.Alignment` 데이터 소스의 수식을 사용하여 레이블 중앙에 바코드를 정렬합니다. 이 공식은 창고 제목의 문자 수를 기반으로 바코드의 왼쪽 오프셋을 계산합니다.

## <a name="prepare-your-environment-for-previewing-generated-labels"></a>생성된 레이블을 미리 볼 수 있도록 환경 준비

다음 예시에서는 ZPL 라벨용 프린터 에뮬레이터 애플리케이션을 사용하여 생성된 라벨의 미리보기를 화면에 표시합니다. 이 옵션을 활성화하려면 다음 단계를 따르십시오.

1. **창고 위치 레이블** ER 형식에 대한 [프린터](er-destination-type-print.md) ER 대상을 추가하고 생성된 레이블을 재무에서 [DRA(문서 라우팅 에이전트)](install-document-routing-agent.md)로 보내도록 구성합니다.
2. 재무에서 생성된 레이블을 현재 워크스테이션에서 액세스할 수 있는 로컬 프린터로 라우팅하도록 DRA를 설치하고 구성합니다.
3. 현재 워크스테이션에 대한 로컬 프린터를 추가하고 생성된 레이블을 DRA에서 프린터 에뮬레이터 애플리케이션으로 전달하도록 구성합니다.
4. Chrome 웹 브라우저의 확장으로 프린터 에뮬레이터 애플리케이션을 설치하고 생성된 레이블을 렌더링하고 미리 보기를 위해 프린터 에뮬레이터로 반환하는 웹 서비스로 생성된 레이블을 로컬 프린터에서 전달하도록 구성합니다.

<table>
<tbody>
<tr align="center">
<td>
<p>Finance</p>
<p>응급실 보고</p>
<p>프린터 대상</p>
</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from Finance to the DRA."></td>
<td>문서 라우팅 에이전트</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from the DRA to a local printer."></td>
<td>로컬 프린터</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from a local printer to a printer emulator."></td>
<td>프린터 에뮬레이터</td>
<td><img src="./media/er-design-zpl-labels-flow2.png" alt="Data flow direction: from a printer emulator to a rendering web service and then back to the printer emulator."></td>
<td>렌더링 웹 서비스</td>
</td>
</tr>
</tbody>
</table>

### <a name="install-and-configure-a-printer-emulator-application"></a>프린터 에뮬레이터 애플리케이션 설치 및 구성

Chrome 웹 브라우저에 ZPL 렌더링 엔진용 프린터 에뮬레이터 애플리케이션을 추가합니다. 이 예시에서는 [Labelary ZPL 웹 서비스](http://labelary.com/service.html)를 기반으로 하는 [Zpl 프린터](https://chrome.google.com/webstore/detail/zpl-printer/phoidlklenidapnijkabnfdgmadlcmjo) 에뮬레이터를 사용합니다. 프린터 에뮬레이터 애플리케이션은 로컬 프린터에서 웹 서비스로 ZPL 형식으로 생성된 레이블을 전달한 다음 미리보기를 위해 레이블을 PDF 또는 PNG 파일로 반환합니다.

1. Chrome 웹 스토어에서 사용하려는 프린터 에뮬레이터 애플리케이션을 찾아 선택합니다. 이후 **Chrome에 추가** 를 선택하여 Chrome 웹 브라우저에 추가합니다.

    ![Chrome 웹 스토어에서 Chrome 웹 브라우저에 프린터 에뮬레이터 애플리케이션을 추가합니다.](./media/er-design-zpl-labels-add-app.png)

2. **앱 실행** 을 선택하여 Chrome 웹 브라우저에서 프린터 에뮬레이터 애플리케이션을 실행합니다.

    ![Chrome 웹 브라우저에서 프린터 에뮬레이터 애플리케이션을 실행합니다.](./media/er-design-zpl-labels-run-app.png)

3. 실행 중인 애플리케이션을 구성합니다.

    1. 애플리케이션을 끕니다.
    2. 프린터 설정에서 호스트를 **127.0.0.1** 로 설정합니다.
    3. 포트를 **9100** 으로 설정합니다.

        ![프린터 에뮬레이터 애플리케이션 구성.](./media/er-design-zpl-labels-configure-app.png)

    4. 애플리케이션을 다시 켜십시오. 프린터가 지정된 호스트 및 포트에서 시작되었다는 메시지를 받아야 합니다.

        ![프린터 에뮬레이터 애플리케이션이 다시 켜졌습니다.](./media/er-design-zpl-labels-turn-on-app.png)

> [!NOTE]
> 이 예시에서 사용되는 프린터 에뮬레이터 애플리케이션은 웹 서비스에 의존하여 레이블을 렌더링하므로 보안 설정에서 서비스와 통신할 수 있는지 확인하십시오. 그렇지 않으면 애플리케이션이 렌더링된 레이블을 수신하지 않으며 해당 레이블의 미리보기를 사용할 수 없습니다.

### <a name="add-and-configure-a-local-printer"></a>로컬 프린터 추가 및 구성

현재 장치에서 생성된 레이블을 DRA에서 프린터 에뮬레이터 애플리케이션으로 전달하는 데 사용할 수 있는 [새 로컬 프린터를 추가](https://support.microsoft.com/windows/install-a-printer-in-windows-10-cc0724cf-793e-3542-d1ff-727e4978638b)합니다.

1. Windows에서 **시작** \> **설정** \> **장치** \> **프린터 \& 스캐너** 를 선택합니다.
2. **프린터 \& 스캐너** 설정을 선택합니다.
3. **프린터 또는 스캐너 추가** 에서 **장치 추가** 를 선택합니다.
4. **원하는 프린터가 목록** 에 없으면 **수동으로 추가** 를 선택합니다.
5. **다른 옵션으로 프린터 찾기** 필드에서 **수동 설정으로 로컬 프린터 또는 네트워크 프린터 추가** 를 선택합니다.
6. **프린터 포트 선택** 필드에서 **새 포트 만들기** 를 선택한 후 다음 단계를 따릅니다.

    1. **포트 유형** 필드에서 **표준 TCP/IP 포트** 를 선택합니다.
    2. **호스트 이름 또는 IP 주소** 필드에 **127.0.0.1** 을 입력합니다.
    3. **포트 이름** 필드에 **ZPL** 을 입력합니다.
    4. **TCP/IP 포트 감지** 작업이 완료될 때까지 기다리십시오.
    5. **장치 유형** 필드에서 **사용자 지정** 을 선택한 다음 **설정** 을 선택합니다.
    6. 다음 포트 설정이 지정되었는지 확인하십시오.

        - **포트 이름:** ZPL
        - **프린터 이름 또는 IP 주소:** 127.0.0.1
        - **규약:** 날것의
        - **포트 번호:** 9100

7. **프린터 드라이버 설치** 필드에서 **일반/텍스트만** 선택합니다.
8. **프린터 이름** 필드에 **ZebraPrinter를** 입력합니다.

![현재 장치에 대한 로컬 프린터를 추가하는 중입니다.](./media/er-design-zpl-labels-configure-printer.png)

### <a name="install-and-configure-the-dra"></a>DRA 설치 및 구성

재무에서 생성된 레이블을 구성된 로컬 프린터로 전달하도록 DRA를 준비합니다.

1. [DRA를 설치합니다](install-document-routing-agent.md#install-the-document-routing-agent).
2. [DRA를 구성합니다](install-document-routing-agent.md#configure-the-document-routing-agent).
3. [DRA에 로컬 프린터를 등록합니다](install-document-routing-agent.md#register-network-printers).
4. 재무 환경에서 [로컬 프린터를 활성화](install-document-routing-agent.md#administer-network-printers)합니다.

![생성된 레이블을 인쇄하기 위해 DRA를 준비합니다.](./media/er-design-zpl-labels-configure-dra.png)

### <a name="configure-the-er-destination"></a>ER 대상 구성

재무에서 DRA로 생성된 레이블을 전달할 ER 대상을 준비합니다.

1. **조직 관리** \> **전자 보고** \> **전자 보고 대상** 으로 이동합니다.
2. **분석 인증서** 페이지의 작업 창에서 **새로 만들기** 를 선택합니다.
3. **참조** 필드에서 **창고 위치 레이블** 을 선택하십시오.
4. **파일 대상** FastTab에서 **새로 만들기** 를 선택합니다.
5. **이름** 필드에 **레이블** 을 입력합니다.
6. **파일 구성 요소** 이름 필드에서 **보고서** 를 선택하십시오.
7. **설정** 을 선택합니다.
8. **대상 설정** 대화 상자의 **프린터** 탭에서 **사용** 옵션을 **예** 로 설정합니다.
9. **프린터 이름** 필드에서 **ZebraPrinter** 를 선택합니다.
10. **문서 라우팅 유형** 필드에서 **ZPL** 을 선택합니다.
11. **확인** 을 선택합니다.

![전자 보고 대상 페이지에서 창고 위치 레이블 형식에 대한 ER 대상 구성.](./media/er-design-zpl-labels-configure-destination.png)

## <a name="review-warehouse-locations"></a>창고 위치 검토

1. **창고 관리** \> **설정** \> **창고** \> **위치** 프로필로 이동하십시오.
2. **위치** 페이지에서 필터링하여 **숫자 확인** 필드에 값이 있는 위치만 봅니다.

![위치 페이지에서 창고 위치를 검토합니다.](./media/er-design-zpl-labels-review-locations.png)

## <a name="print-warehouse-location-labels"></a>창고 위치 라벨 인쇄

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **창고 모델** 을 펼치고 **창고 위치 레이블** 을 선택하십시오.
3. 작업 창에서 **송장** 을 선택합니다.
4. **전자 보고서 매개 변수** 대화 상자의 **포함할 기록** 탭에서 **필터** 를 선택합니다.
5. **범위** 탭에서 **테이블** 필드가 **위치** 로 설정되고 **필드** 필드가 **위치** 로 설정된 행을 찾습니다. **기준** 필드에 **LPEnabled** 를 입력합니다.
6. **확인** 을 선택합니다.
7. **확인** 을 선택합니다. 레이블이 생성되어 프린터 에뮬레이터 애플리케이션의 미리 보기 페이지에 표시됩니다.

![Zpl 프린터 에뮬레이터 애플리케이션의 미리보기 페이지에서 생성된 레이블을 검토합니다.](./media/er-design-zpl-labels-preview-label.png)

## <a name="modify-the-layout-of-a-label"></a>레이블 레이아웃 수정

창고 위치 레이블의 현재 레이아웃을 변경할 수 있습니다. 다음 예는 생성된 레이블에 위치 프로필 ID가 포함되도록 레이아웃을 변경하는 방법을 보여줍니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **초안 상태** [ER 사용자 매개 변수](electronic-reporting-destinations.md#applicability)에 대상 사용을 **예** 로 설정합니다.
3. **구성** 페이지의 구성 트리에서 **창고 모델** 을 펼치고 **창고 위치 레이블** 을 선택하십시오.
4. **디자이너** 를 선택합니다.
5. **형식 디자이너** 페이지의 **매핑** 탭에서 `model.Location.Label` 데이터 원본을 선택합니다.
6. **데이터 원본 속성** 대화 상자에서 **편집** \> **수식 편집** 을 선택합니다.
7. **수식 디자이너** 페이지의 **수식** 필드에서 레이블을 생성하는 데 사용되는 ER 수식을 검토합니다.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^XZ")
    ```

8. 수식을 업데이트하여 생성된 레이블에 위치 프로필 ID를 추가하십시오.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^CF0,40,40^FO0,240^FB800,1,0,C,0^FD",@.ProfileID,"\&^FS",CrLf,
    "^XZ")
    ```

9. **저장** 을 선택합니다.
10. **확인** 을 선택합니다.
11. 작업 창에서 **송장** 을 선택합니다.
12. **전자 보고서 매개 변수** 대화 상자의 **포함할 기록** 탭에서 **필터** 를 선택합니다.
13. **범위** 탭에서 **테이블** 필드가 **위치** 로 설정되고 **필드** 필드가 **위치** 로 설정된 행을 찾습니다. **기준** 필드에 **Bay** 를 입력합니다.
14. **확인** 을 선택합니다.
15. **확인** 을 선택합니다. 레이블이 생성되어 프린터 에뮬레이터 애플리케이션의 미리 보기 페이지에 표시됩니다.

![Zpl 프린터 에뮬레이터 애플리케이션의 미리 보기 페이지에서 위치 프로필 ID를 포함하는 생성된 레이블을 검토합니다.](./media/er-design-zpl-labels-preview-label2.png)

## <a name="encoding"></a>인코딩

> [!NOTE]
> 편집 가능한 ER 형식의 **Common\\File** 구성 요소의 인코딩 설정과 디자인된 레이블의 적절한 설정을 동기화해야 합니다. **Common\\File** 구성 요소의 **[Encoding](er-suppress-bom-characters.md)** 필드 값은 레이블의 인코딩(예: `^CI` 명령)을 제어하는 데 사용되는 ZPL 명령과 모순되지 않아야 합니다. ER은 이러한 설정이 동기화되었는지 확인하지 않습니다.

## <a name="additional-resources"></a>추가 리소스

[프린터 대상](er-destination-type-print.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
