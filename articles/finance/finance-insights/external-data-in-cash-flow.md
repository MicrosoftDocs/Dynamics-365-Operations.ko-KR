---
title: 현금 흐름 예측의 외부 데이터
description: 이 항목에서는 현금 흐름 예측에 외부 데이터를 입력하거나 가져오기 위해 완료해야 하는 설정 단계를 설명합니다.
author: rcarlson
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 23342114c25cd1b59d47aa7ce63f09de029fa690
ms.sourcegitcommit: 465c84eb5cdc211692e2ae09b45d1400f9a315ee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8451618"
---
# <a name="external-data-in-cash-flow-forecasts"></a>현금 흐름 예측의 외부 데이터

[!include [banner](../includes/banner.md)]

현금 흐름 예측에 외부 데이터를 입력하거나 가져올 수 있습니다. 이 항목에서는 외부 데이터를 사용하기 위한 설정 단계를 설명하여 외부 데이터를 현금 흐름 예측에 포함할 수 있도록 합니다.

## <a name="external-data-setup"></a>외부 데이터 설정

현금 흐름 예측에서 외부 데이터 사용을 지원하는 설정을 입력하려면 **현금 흐름 예측 설정** 페이지(**현금 및 은행 관리 \> 현금 흐름 예측 \> 현금 흐름 예측 설정**)의 **외부 소스** 탭을 사용합니다.

현금 흐름 예측에 외부 데이터를 입력하거나 가져올 수 있습니다. 외부 데이터를 입력하거나 가져오기 전에 외부 원본을 설정해야 합니다. **외부 원본** 탭에서 외부 현금 흐름 범주를 설정합니다. 범주는 **발신** 또는 **수신** 일 수 있습니다. **유동성** 은 전기 유형으로 선택해야 합니다. **법인 설정** 그리드에서 외부 현금 흐름 범주가 적용되는 법인 및 해당 주 계정을 선택합니다.

현금 흐름 예측 설정 방법에 대한 자세한 내용은 [현금 흐름 예측](../cash-bank-management/cash-flow-forecasting.md)을 참조하십시오.

## <a name="enter-external-data"></a>외부 데이터 입력

현금 흐름 예측을 위해 외부 데이터를 입력하고 수정하려면 **Excel에서 열기** 환경을 사용할 수 있습니다. **현금 흐름 예측** 작업 영역 페이지에서 **외부 데이터** 버튼을 선택한 다음 **외부 데이터 추가** 또는 **기존 외부 데이터 편집** 을 선택합니다. Microsoft Excel 파일이 열리면 다음 필드에 정보를 입력할 수 있습니다.

- **항목 ID**(고유)
- **설명**(선택 사항)
- **외부 소스 이름** – Finance insights를 설정할 때 정의한 목록의 값 중 하나를 선택합니다.
- **법인**
- **날짜**
- **거래 통화 금액**
- **통화 코드**
- **기본 차원**(선택 사항)
- **문서 번호**(선택 사항)
- **계정 번호**(선택 사항)
- **계정 이름**(선택 사항)

## <a name="importing-external-data-by-using-the-data-management-framework"></a>데이터 관리 프레임워크를 사용하여 외부 데이터 가져오기

**데이터 관리** 작업 영역과 **현금 흐름 예측 외부 소스 항목** 이라는 엔터티를 사용하여 현금 흐름 예측을 위한 외부 데이터를 가져올 수 있습니다.

또한 한 환경에서 다른 환경으로 설정 데이터를 이동해야 하는 경우 필요한 설정 테이블에 다음 엔티티 영역을 사용할 수 있습니다.

- 현금 흐름 예측 외부 소스 설정
- 현금 흐름 예측 외부 소스 법인 설정

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
