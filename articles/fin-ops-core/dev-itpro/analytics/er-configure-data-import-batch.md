---
title: 배치 모드에서 수동으로 선택한 파일에서 데이터 가져오기
description: 이번에는 배치 모드에서 수동으로 선택한 파일에서 데이터를 가져오는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.openlocfilehash: 8615b5a0623fd696c64f4ec03e481a2bcb16c0ac
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8461042"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>배치 모드에서 수동으로 선택한 파일에서 데이터 가져오기

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

[전자 보고(ER)](general-electronic-reporting.md) 프레임워크를 사용하여 수동으로 선택한 인바운드 파일의 데이터를 일괄 처리 모드로 가져오려면 가져오기를 지원하는 ER [형식](er-overview-components.md#format-component)을 구성하십시오. 이후 해당 형식을 데이터 원본으로 사용하는 **대상** 유형의 [모델 매핑](er-overview-components.md#model-mapping-component)을 실행합니다. 데이터를 가져오려면 가져올 파일을 찾아 수동으로 선택합니다. 

배치 모드에서 데이터 가져오기를 지원하는 새로운 ER 기능을 통해 이 프로세스를 무인으로 구성할 수 있습니다. ER 구성을 사용하여 ER UI(사용자 인터페이스)에서 새 일괄 작업을 예약하여 데이터 가져오기를 수행할 수 있습니다.

이번에는 배치 모드에서 수동으로 선택한 파일에서 데이터 가져오기를 완료하는 방법에 대해 설명합니다. 이 예시에서는 공급 업체 트랜잭션을 비즈니스 데이터로 사용합니다. 이러한 예의 단계는 **USMF** 회사에서 완료할 수 있습니다. 코딩이 필요하지 않습니다.

## <a name="prerequisites"></a>전제 조건

이 주제의 예를 완료하려면 다음 액세스 권한이 있어야 합니다.

- 다음 역할 중 하나:

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

- 1099 지급을 위한 ER 형식 및 모델 구성

### <a name="create-the-required-er-configurations"></a>필요한 ER 구성 생성

필요한 ER 구성을 생성하고 다른 전제 조건을 얻으려면 다음 단계 중 하나를 따르십시오.

- **7.5.4.3 IT 서비스/솔루션 구성 요소 획득/개발(10677)** 비즈니스 프로세스의 일부인 **Microsoft Excel 파일 작업 가이드에서 ER 가져오기** 데이터를 재생합니다. 이 작업 가이드는 Microsoft Excel 파일에서 공급 업체 트랜잭션을 대화식으로 가져오는 ER 구성을 설계하고 사용하는 프로세스를 안내합니다. 자세한 내용은 [Excel 형식으로 수신 문서 구문 분석](parse-incoming-documents-excel.md)을 참조하십시오.
- [SharePoint에서 데이터 가져오기 구성](er-configure-data-import-sharepoint.md)의 예를 완료하십시오. 이 예시는 SharePoint 폴더에 저장된 Excel 파일에서 공급 업체 트랜잭션을 대화식으로 가져오는 ER 구성을 설계하고 사용하는 과정을 안내합니다.

### <a name="download-the-required-er-configurations"></a>필요한 ER 구성 다운로드

1. 다음 ER 구성을 다운로드하고 로컬에 저장합니다.

    | 콘텐츠 설명 | 파일 |
    |---------------------|------|
    | **1099 지급 모델** ER 데이터 모델 구성 | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | **공급 업체 거래(Excel)** ER 형식 구성 가져오기 | [1099format-import-from-excel.xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. [XML 파일 ER에서 로드](er-defer-sequence-element.md#import-the-sample-er-configurations) 옵션을 사용하여 다운로드한 ER 구성을 다음 순서로 Dynamics 365 Finance 인스턴스로 가져옵니다.

    1. ER 데이터 모델 구성
    2. ER 형식 구성

### <a name="download-the-required-excel-files"></a>필요한 엑셀 파일 다운로드

- 다음 샘플 데이터 세트를 다운로드하고 로컬에 저장합니다.

    | 콘텐츠 설명 | 파일 |
    |---------------------|------|
    | 가져올 샘플 데이터가 포함된 인바운드 **1099import-data.xlsx** 파일 | [1099가져오기-데이터.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>전제 조건 검토

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 배치 모드로 데이터 가져오기를 위해 준비된 ER 솔루션을 검토합니다.
3. **공급 업체 트랜잭션 가져오기(Excel)** 형식 구성을 검토합니다.

    - 이 구성의 형식 구성 요소는 인바운드 Excel 파일을 구문 분석하도록 설계되었습니다.
    - 이 구성의 모델 매핑 구성 요소는 구문 분석된 Excel 파일의 데이터를 사용하여 기본 데이터 모델을 채우는 데 사용됩니다.

    ![ER UI에서 일괄 모드로 데이터를 가져오기 위한 ER 형식 구성입니다.](./media/er-configure-data-import-batch-configurations-1.png)

4. **1099 지급 모델** 데이터 모델 구성을 검토하십시오.

    - 이 구성의 모델 구성 요소는 실행 중인 ER 구성 요소 간에 데이터를 전달하는 데 사용되는 데이터 모델의 구조를 나타냅니다.
    - 이 구성의 모델 매핑 구성 요소는 실행된 형식 구성 요소에서 데이터를 가져온 다음 애플리케이션 테이블을 업데이트하는 데 사용됩니다.

    ![ER UI에서 일괄 모드로 데이터를 가져오기 위한 ER 데이터 모델 구성입니다.](./media/er-configure-data-import-batch-configurations-2.png)

5. Excel에서 **1099import-data.xlsx** 파일을 엽니다.

    ![배치 모드에서 가져올 데이터가 포함된 샘플 Excel 파일입니다.](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>UI에서 ER에 대한 일괄 데이터 가져오기 활성화

1. **시스템 관리** \> **작업 공간** \> **기능 관리** 로 이동합니다.
2. **기능 관리** 작업 영역에서 **수동으로 업로드한 문서의 일괄 가져오기 실행** 기능을 선택한 다음 **지금 활성화** 를 선택합니다.

## <a name="import-data-from-manually-selected-excel-files"></a>수동으로 선택한 Excel 파일에서 데이터 가져오기

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 **1099 지급 모델** 데이터 모델 구성을 선택하십시오.
3. **구성 구성 요소** FastTab에서 **1099 수동 트랜잭션 가져오기** 링크를 선택합니다.
4. **모델 대 데이터 소스 매핑** 페이지에서 **1099 수동 트랜잭션 가져오기** 모델 매핑이 미리 선택되어 있습니다. **실행** 을 선택합니다.
5. **매개 변수** 탭에서 **찾아보기** 를 선택합니다. **1099import-data.xlsx** 파일을 찾아 선택한 다음 **확인** 을 선택합니다.
6. **바우처 ID 입력** 필드에 **V-00001** 을 입력합니다.
7. **백그라운드에서 실행** 탭에서 **일괄 처리** 옵션을 **예** 로 설정합니다.

    **작업 설명** 필드가 **'1099 수동 트랜잭션 가져오기의 경우' 매핑 실행, '1099 지급 모델' 구성** 으로 설정되어 있습니다. 이 값은 선택한 모델 매핑의 실행이 새 일괄 작업으로 예약됨을 나타냅니다.

    ![전자 보고서 매개 변수 대화 상자에서 일괄 모드로 데이터 가져오기에 대한 세부 정보 지정.](./media/er-configure-data-import-batch-execution-parameters.png)

8. **확인** 을 선택합니다. 새 일괄 작업이 예약되었음을 알리는 메시지가 표시됩니다.

    ![모델에서 데이터 소스로의 매핑 페이지에서 예약된 새 일괄 작업에 대한 메시지입니다.](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>일괄 작업 페이지에서 데이터 가져오기 결과 검토

1. **일반** \> **문의** \> **일괄 작업** \> **내 일괄 작업** 으로 이동합니다.
2. **일괄 작업** 페이지에서 일괄 작업 목록을 필터링하여 예약된 일괄 처리를 찾은 다음 선택합니다.
3. 작업 세부 정보를 검토하려면 **작업 ID** 링크를 선택합니다.
4. **일괄 작업** FastTab에서 **로그** 를 선택합니다.

    ![일괄 작업 페이지의 로그 버튼.](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. 실행 세부 정보를 검토합니다.

    ![일괄 작업 페이지에서 예약된 일괄 작업의 실행 로그입니다.](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>데이터 가져오기 매개 변수 변경

배치가 예약된 후 아직 실행되지 않은 동안 예약된 데이터 가져오기의 매개 변수를 변경할 수 있습니다.

1. **일반** \> **문의** \> **일괄 작업** \> **내 일괄 작업** 으로 이동합니다.
2. **일괄 작업** 페이지에서 일괄 작업 목록을 필터링하여 예약된 일괄 처리를 찾은 다음 선택합니다.
3. **상태 변경** 을 선택합니다.
4. **새 상태 선택** 대화 상자에서 **보류** 를 선택한 다음 **확인** 을 선택합니다.
5. 작업 세부 정보에 액세스하려면 **작업 ID** 링크를 선택합니다.
6. **일괄 작업** FastTab에서 **매개 변수** 를 선택합니다.
7. **전자 보고서 매개 변수** 대화 상자에서 다음 단계를 따르십시오.

    1. **찾아보기** 를 선택하여 데이터 가져오기를 위한 대체 파일을 선택합니다.
    2. 공급 업체 거래를 가져오기 위한 바우처 번호를 변경하려면 **바우처 ID 입력** 을 선택합니다.

        ![전자 보고서 매개 변수 대화 상자에서 예약된 배치 작업에 대한 데이터 가져오기 매개 변수 변경.](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. **확인** 을 선택합니다.

8. 배치가 여전히 선택되어 있는지 확인한 다음 **상태 변경** 을 다시 선택합니다.
9. **새 상태 선택** 대화 상자에서 **대기** 를 선택한 다음 **확인** 을 선택합니다.

## <a name="review-the-data-import-results-on-the-er-source-page"></a>ER 소스 페이지에서 데이터 가져오기 결과 검토

1. **조직 관리** \> **전자 보고** \> **전자 보고 소스** 로 이동합니다.
2. 데이터 가져오기 중 자동으로 생성된 가져오기 **공급 업체의 트랜잭션(Excel)** 기록을 선택합니다.

    ![전자 보고 소스 페이지의 수입업체 트랜잭션(Excel) 구성에 대한 기록입니다.](./media/er-configure-data-import-batch-files-source-1.png)

3. **소스에 대한 파일 상태** 를 선택합니다.
4. **가져오기 형식** FastTabs에 대한 **파일 및 소스 로그에서 가져오기** 세부 정보를 검토합니다.
5. **파일** FastTab에서 기록을 선택합니다. 가져온 파일이 이 기록에 첨부되어 있습니다.

    ![소스 페이지에 대한 파일 상태의 기록에 첨부된 가져온 파일입니다.](./media/er-configure-data-import-batch-files-source-2.png)

6. **첨부 파일** 을 선택하여 가져온 파일을 검토합니다.

    ![문서 보기 페이지에서 가져온 파일입니다.](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > 이러한 첨부 파일을 유지하기 위해 ER 프레임워크는 ER 매개 변수의 **기타** 필드에서 현재 회사에 대해 [설정된](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) 문서 유형을 사용합니다.

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>1099s에 대한 Vendor 정산 페이지에서 데이터 가져오기 결과 검토

1. **미지급금으로 이동합니다.** \> **정기 작업** \> **세금 1099** \> **1099에 대한 공급 업체** 정산.
2. **시작 날짜** 필드에 **12/31/2017**(2017년 12월 31일)을 입력합니다.
3. **수동 1099 트랜잭션** 을 선택합니다.

    ![세금 1099 거래 페이지에서 가져온 공급 업체 거래.](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
