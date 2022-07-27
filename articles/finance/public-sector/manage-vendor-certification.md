---
title: 공급업체 인증 유지
description: 이 항목에서는 공급업체가 공급업체 공동 작업 영역을 사용하여 인증을 유지 관리하는 데 사용할 수 있는 단계에 관해 설명합니다.
author: v-kiarnd
ms.date: 04/27/2021
ms.topic: article
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 932b8bc2982a7c38404ff4203fce7fb65c1182d4490d2aad5a6d78fd809ec768
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450349"
---
# <a name="maintain-vendor-certification"></a>공급업체 인증 유지

[!include [banner](../includes/banner.md)]

이 항목에서는 공급업체가 **공급업체 공동 작업 영역** 을 사용하여 인증을 유지 관리하는 데 사용할 수 있는 단계에 관해 설명합니다. 인증의 예로는 WBE(Women Business Enterprise) 또는 LEED(Leadership in Energy and Environment Design) 회사가 포함될 수 있습니다. 공급업체는 **공급업체 정보** 작업 영역에 인증 정보를 입력해야 합니다. 여기에서 공급업체는 **자세한 내용** 을 선택한 다음 **인증** 을 선택합니다.

## <a name="turn-on-the-vendor-certification-feature"></a>공급업체 인증 기능 켜기

이 기능을 사용하려면 먼저 시스템에서 켜져 있어야 합니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 페이지를 사용하여 기능의 상태를 확인하고 필요한 경우 활성화할 수 있습니다. **기능 관리** 작업 영역에서 기능은 다음과 같은 방식으로 나열됩니다.

- **모듈** - *지급 계정*
- **기능 이름** - *공급업체 공동 작업 인증 관리 활성화*

## <a name="add-a-new-certification"></a>새 인증 추가

새 인증을 추가하려면 **공급업체 정보** 작업 영역의 **인증** 그리드 위에 있는 **추가** 버튼을 선택합니다. 다음 정보를 입력합니다.

- 인증 번호
- 인증 유형
- 인증 기관
- 인증 날짜
- 부채 금액(해당하는 경우)
- 적용 날짜
- 만료 날짜
- 설명(선택 사항)

특정 인증과 관련된 문서가 있는 경우 **문서** 버튼을 선택하여 첨부할 수 있습니다.

이 페이지에 공급업체가 입력한 인증에 "공급업체" 원본이 할당됩니다. 공급업체 은행 계좌에서 공급업체를 대신하여 인증서 정보를 입력할 수 있습니다. 정보가 여기에 표시되고 출처가 **고객** 으로 표시됩니다.

공급업체는 필요에 따라 인증을 편집하거나 삭제할 수 있습니다.

## <a name="vendor-collaboration-generated-certification-records"></a>공급업체 공동 작업 생성 인증 기록

공급업체에서 인증 정보를 추가한 후에는 **공급업체 공동 작업 생성 인증** 페이지에 해당 정보가 표시됩니다. 페이지를 열려면 **지급 계정 > 문의 > 공급업체 보고서 > 공급업체 공동 작업 생성 인증** 으로 이동합니다. 기본적으로 모든 신규 또는 수정된 인증 레코드가 표시됩니다. 지급 계정 사무원은 확인 절차를 통해 변경 사항을 보고 정보를 확인할 수 있습니다. 정보가 확인되면 페이지에 나열된 인증 기록을 선택하여 검토됨으로 표시할 수 있습니다. 레코드를 검토됨으로 표시하면 기본 목록에서 제거됩니다.

모든 인증 변경 사항은 **공급업체 공동 작업 생성 인증** 페이지에 표시됩니다. 페이지에 변경 사항이 표시되지 않으면 공급업체 계정, 적용 날짜 범위에 대한 필터를 조정하거나 검토된 인증 변경 사항에 대한 정보를 포함할지를 선택하여 변경할 수 있습니다.

