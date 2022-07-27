---
title: 고객 에이징 데이터 스토리지
description: 이 항목에서는 고객 에이징 데이터에 외부 스토리지를 사용하는 프로세스에 대해 설명합니다. 고객 에이징 데이터 저장 프로세스를 실행하여 출력을 외부 시스템으로 내보낼 수 있도록 할 수 있습니다.
author: JodiChristiansen
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ecd4f5359019e3c4778e21cc4946b9998cd519f
ms.sourcegitcommit: 9f8da0ae3dcf3861e8ece2c2df4f693490563d5e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2021
ms.locfileid: "8451195"
---
# <a name="customer-aging-data-storage"></a>고객 에이징 데이터 스토리지

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

이 항목에서는 고객 에이징 데이터에 외부 스토리지를 사용하는 프로세스에 대해 설명합니다. Microsoft Dynamics 365 Finance에서 고객 에이징 데이터 저장 프로세스를 실행하여 출력을 외부 시스템으로 내보낼 수 있도록 할 수 있습니다. 프로세스를 실행할 때 시스템에서 사용 가능한 동일한 에이징 보고서 옵션을 외부 시스템에서도 사용할 수 있습니다. 내보낸 데이터에는 항상 세부 정보가 포함됩니다.

출력에 많은 고객 및/또는 많은 거래가 포함된 경우 저장을 위해 외부 시스템에서 고객 에이징 데이터를 사용할 수 있도록 하는 것이 도움이 될 수 있습니다. 기존 **고객 에이징** 보고서에 인쇄할 데이터가 너무 많아 시간이 초과된 경우 이 기능은 동일한 데이터를 가져올 수 있는 대체 방법을 제공합니다.

## <a name="enable-the-customer-aging-data-storage-feature"></a>고객 에이징 데이터 스토리지 기능 활성화

이 기능을 사용하려면 먼저 시스템에서 활성화해야 합니다. 관리자는 기능 관리 설정을 사용하여 기능의 상태를 확인하고 필요한 경우 활성화할 수 있습니다. **기능 관리** 작업 영역에서 기능은 다음과 같은 방식으로 나열됩니다.

- **모듈:** 신용 및 수금
- **기능 이름:** 고객 에이징 데이터 스토리지

## <a name="run-the-customer-aging-data-storage-process"></a>고객 에이징 데이터 스토리지 프로세스 실행

1. **신용 및 수금 \> 문의 및 보고 \> 고객 \> 고객 에이징 데이터 스토리지** 로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **이름** 필드에 프로세스 이름을 입력합니다.
4. 필요에 따라 나머지 매개 변수를 설정합니다.

    > [!NOTE]
    > 거래 세부 정보가 항상 포함되며 처리는 항상 배치 작업으로 수행됩니다.

5. **확인** 을 선택합니다.
6. **고객 에이징 데이터 스토리지** 페이지를 새로 고쳐 **처리 상태** 값과 함께 표시되는 **배치 이름** 및 **배치 실행 시간** 값을 확인합니다. 배치 작업이 완료되면 **처리 상태** 필드가 **종료** 로 설정되고 **에이징 라인 수** 필드가 설정됩니다. 배치 작업이 반복되는 경우 **처리 상태** 필드가 **대기 중** 으로 설정됩니다.
7. **에이징 라인 수** 필드 옆에 있는 **필터** 버튼을 선택하여 배치 작업에 추가된 필터를 검토합니다.

**고객 에이징 데이터 스토리지** 페이지에 결과가 포함되어 있지 않습니다. 그러나 **고객 에이징 데이터 스토리지** 데이터 엔터티를 사용하면 데이터 관리가 지원하는 모든 형식으로 출력을 내보낼 수 있습니다.

> [!NOTE]
> 내보내기를 수행하기 전에 필터를 추가하여 내보낸 결과를 가장 최근의 에이징으로 제한합니다. 예를 들어 가장 최근의 배치 실행을 반환하려면 다음 기준을 추가합니다.
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchName())
>
> 또는 현재 사용자에 대한 가장 최근의 배치 실행을 반환하려면 다음 기준을 추가합니다.
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchNameForCurrentUser())
