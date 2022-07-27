---
title: 공급업체 요청 구성
description: 이 토픽에서는 새 공급업체 요청에 채워야 하는 필드에 대해 설명합니다.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 1d34a9974da41b7abb40bb2cf046a15432c249eb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448294"
---
# <a name="vendor-request-configurations"></a>공급업체 요청 구성
[!include [banner](../includes/banner.md)]

공급업체 요청을 완료하려면 공급업체 담당자가 예상 공급업체 등록 마법사를 완료해야 합니다.

**공급업체 요청 구성** 양식에서 예상 공급업체 등록 마법사의 필수 필드 및 표시되는 필드를 지정하는 프로필을 생성할 수 있습니다.

공급업체 등록 마법사는 예상 공급업체 사용자에게 공급업체가 사업을 하고 있는 국가/지역을 묻는 것으로 시작됩니다. 이 정보는 적용 가능한 구성을 결정합니다. 국가/지역에 대해 특정 구성이 정의되지 않은 경우 기본 구성이 사용됩니다.

### <a name="set-up-a-vendor-request-configuration"></a>공급업체 요청 구성 설정

기본적으로 공급업체 요청 구성 양식에 사용 가능한 공급업체 구성이 있습니다.

기본 구성에 대해 국가/지역을 선택할 수 없으므로 **국가/지역** 섹션을 변경할 수 없습니다.

1. **조달 및 소싱** > **설정** > **공급업체** 를 클릭한 다음 **공급업체 요청 구성** 을 클릭합니다.
2. **필드** 탭을 클릭하여 나열된 필드의 상태를 설정합니다.
3. 숨김(보이지 않음)
4. 표시됨(표시되지만 필수는 아님)
5. 필수(표시 및 필수)
6. **콘텐츠** 탭을 클릭하여 마법사에 텍스트를 표시할지 여부와 예상 공급업체 사용자가 마법사의 다음 단계로 이동하기 전에 이를 수락해야 한다는 승인이 있어야 하는지 여부를 지정합니다. 계속하기 위해 사용자가 수락해야 하는 모든 이용 약관에 대한 승인이 요청됩니다.

마법사가 완료될 때 표시될 확인 메시지를 입력하고 하나 이상의 질문을 추가할 수도 있습니다.

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a>특정 국가/지역에 대한 공급업체 구성 만들기
1.  **조달 및 소싱** > **설정** > **공급업체** 를 클릭한 다음 **공급업체 요청 구성** 을 클릭합니다.
2.  **새로 만들기** 를 클릭하여 새 구성을 만들고 구성 이름을 제공합니다.
3.  **저장** 을 클릭합니다.
4.  **국가/지역** 탭을 열어 구성을 사용해야 하는 국가/지역을 선택합니다.
5.  기본 구성에 대한 지침에 따라 구성을 완료합니다.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]