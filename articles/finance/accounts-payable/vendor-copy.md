---
title: 공유 숫자 시퀀스를 사용하여 공급업체 복사
description: 이 항목에서는 공유 숫자 시퀀스를 사용하여 공급업체를 다른 법인에 복사하지만 공급업체 ID는 그대로 유지하는 방법에 대해 설명합니다.
author: sunfzam
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 4cea8269082b39e2374ffb3c3dc82def8ce35679
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2022
ms.locfileid: "8452962"
---
# <a name="copy-vendors-by-using-shared-number-sequences"></a>공유 숫자 시퀀스를 사용하여 공급업체 복사

[!include [banner](../includes/banner.md)]

공유 숫자 시퀀스를 사용하여 공급업체 ID를 할당할 수 있습니다. 또한 공유 숫자 시퀀스를 사용하면 한 법인에서 다른 법인으로 공급업체를 복사하되 두 법인에서 동일한 공급업체 ID를 사용할 수 있습니다.

## <a name="setup"></a>설정

이 기능은 공유 숫자 시퀀스를 사용하여 공급업체 ID를 할당할 때 활성화됩니다. 공급업체를 복사할 모든 법인에서 동일한 숫자 시퀀스를 사용해야 합니다. 각 법인의 **지급 계정 매개 변수** 페이지에서 공급업체 숫자 시퀀스를 변경할 수 있습니다. **지급 계정** \> **설정** \> **지급 계정 매개 변수** 를 선택하고 **숫자 시퀀스** 탭을 선택합니다.

각 공급업체 그룹의 공급업체 숫자 시퀀스를 설정할 수도 있습니다. 이러한 숫자 시퀀스도 공유해야 합니다. 공급업체 그룹의 숫자 시퀀스를 가장 먼저 사용합니다. 공급업체 그룹의 숫자 시퀀스가 지정되지 않았다면 **지급 계정 매개 변수** 페이지에 지정된 숫자 시퀀스를 사용합니다.

수동 공급업체 ID를 사용하는 경우에는 법인 간에 공급업체를 복사할 수도 있습니다. 그러나 공급업체 ID가 이미 있는 법인에 공급업체를 복사하면 복사 프로세스가 시작되지 않습니다.

## <a name="copy-a-vendor"></a>공급업체 복사

공급업체를 복사하려면 **모든 공급업체** 목록 페이지에서 **새로 만들기** 를 선택해 **모든 벤더, 새 레코드** 페이지를 엽니다. 새 공급업체 ID는 바로 할당되지 않습니다. 이 동작은 이전 버전의 동작과 다릅니다. 아직 공급업체 그룹을 선택하지 않았으므로 사용할 올바른 숫자 시퀀스를 결정할 수 없습니다. 또한 사용자가 새 공급업체를 만들려 하는지 공급업체를 복사하려 하는지도 결정하지 못합니다. 따라서 공급업체 ID가 할당되려면 먼저 페이지 하단의 **저장** 단추를 선택해야 합니다.

새 공급업체를 생성하는 경우에는 평소처럼 모든 필드를 채우면 됩니다. 작성이 끝난 후 **저장** 을 선택하면 공급업체 ID가 자동으로 할당됩니다. 수동 숫자 시퀀스의 경우에는 수동 공급업체 ID가 사용되었음을 확인할 수 있습니다.

공급업체를 복사하려면 **이름** 필드에 찾으려는 공급업체를 나타내는 문자를 하나 이상 입력합니다. 찾으려는 공급업체에 해당할 수 있는 당사자 목록이 검색 대화 상자에 표시됩니다. 당사자 중 하나를 선택하면 대화 상자 오른쪽에 추가 정보가 나타납니다.

- **일반** 탭에 당사자의 전화 번호와 주소가 표시됩니다.
- **역할** 탭에 선택한 당사자가 맡을 수 있는 역할과 각 역할이 있는 법인이 표시됩니다.
- **사업자 등록 ID** 탭에 당사자에게 할당된 사업자 등록 ID가 표시됩니다.

당사자에게 공급업체 역할이 있고 현재 법인이 아닌 다른 법인에 이 역할이 있는 경우에만 당사자를 복사할 수 있습니다. 이러한 기준을 충족하는 당사자를 찾으면 다음 단계를 따르세요.

1. **공급업체 복사** 옵션이 표시됩니다. 기본적으로 이 옵션은 **아니요** 로 설정됩니다. 공급업체를 현재 법인으로 복사하려면 옵션을 **예** 로 설정합니다. 
2. **법인** 필드가 나타납니다. 공급업체를 복사할 법인을 선택합니다. 공급업체가 단일 법인에만 존재한다면 필드는 기본적으로 해당 법인으로 설정됩니다.
3. **선택** 을 선택합니다. 새 공급업체가 생성됩니다.

## <a name="validation"></a>유효성 검사

공급업체를 복사하면 새 공급업체 정보가 저장됩니다. 복사된 데이터가 양호한지 확인하기 위해 유효성 검사가 실행됩니다. 유효성 검사가 실패할 때마다 오류 메시지가 나타납니다. 오류 메시지는 업데이트해야 하는 정보를 설명합니다. 공급업체 사본을 저장하려면 먼저 모든 유효성 검사 오류를 수정해야 합니다.

## <a name="copy-a-vendor-by-using-the-tax-exempt-number-search-feature"></a>면세 번호 검색 기능을 사용하여 공급업체 복사

**모든 공급업체** 페이지의 작업 창에 있는 **공급업체** 탭의 **등록** 그룹에서 제공하는 **면세 번호** 검색 기능을 이용해 공급업체를 복사할 수도 있습니다. 표시되는 **면세 번호 조회** 대화 상자에서 면세 번호, 공급업체 ID, 공급업체 이름, 면세 ID를 사용하는 법인을 확인할 수 있습니다. 공급업체가 현재 법인이 아닌 다른 법인에 속한 경우에만 복사할 수 있습니다. 이 기준을 충족하는 공급업체를 선택한 후 다음 단계를 따르세요.

1. **공급업체 복사** 옵션이 표시됩니다. 기본적으로 이 옵션은 **아니요** 로 설정됩니다. 공급업체를 현재 법인으로 복사하려면 옵션을 **예** 로 설정합니다.
2. **선택** 을 선택합니다. 새 공급업체가 생성됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]