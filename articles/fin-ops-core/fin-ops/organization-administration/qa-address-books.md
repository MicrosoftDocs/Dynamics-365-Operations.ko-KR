---
title: 주소록 FAQ
description: 이 항목에서는 주소록과 관련된 자주 묻는 질문에 대한 답변을 제공합니다.
author: msftbrking
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirPartyCheckDuplicate, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23601
ms.assetid: b177fa0f-ac9a-415e-9498-15438e132f60
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d429639f52c745a737567419b6012884ab20d43d
ms.sourcegitcommit: b294840b8e12aaa2775dd73b2ba9481ecc3d91d5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2021
ms.locfileid: "8460952"
---
# <a name="address-books-faq"></a>주소록 FAQ

[!include [banner](../includes/banner.md)]

## <a name="how-do-i-check-for-duplicate-records"></a>중복 기록은 어떻게 확인합니까?

**전체 주소록** 목폭 페이지에서 직접 중복 기록을 확인할 수 있습니다. 작업 창에서 **파티** 탭의 **유지 관리** 그룹에서 **중복 확인** 을 클릭합니다. 그런 다음 중복 검사에 포함할 값을 선택합니다.

## <a name="can-i-bulk-add-or-delete-party-records-from-an-address-book"></a>주소록에서 당사자 기록을 일괄 추가하거나 삭제할 수 있습니까?

예, 주소록에 여러 당사자 레코드를 추가하고 여러 당사자 레코드를 제거할 수도 있습니다.

- 주소록에 여러 당사자 기록을 추가하려면 **전체 주소록** 목록 페이지의 목록에서 당사자를 선택합니다. 그런 다음 작업 창에서 **파티** 탭의 **유지 관리** 그룹에서 **파티 할당** 을 클릭합니다. 선택한 당사자 기록을 추가할 주소록을 선택한 다음 **확인** 을 클릭합니다. 선택한 모든 당사자 기록이 선택한 주소록에 추가됩니다.
- 주소록에서 여러 당사자 기록을 제거하려면 **전체 주소록** 목록 페이지의 목록에서 당사자를 선택합니다. 그런 다음 작업 창에서 **파티** 탭의 **유지 관리** 그룹에서 **파티 제거** 를 클릭합니다. 상대방을 제거할 주소록을 선택한 다음 **확인** 을 클릭합니다. 선택한 모든 당사자 기록이 선택한 주소록에서 제거됩니다.

## <a name="can-i-change-the-party-type-of-a-record-or-do-i-have-to-delete-the-old-record-and-create-a-new-one"></a>레코드의 당사자 유형을 변경할 수 있습니까? 아니면 이전 레코드를 삭제하고 새 레코드를 생성해야 합니까?

경우에 따라 레코드의 당사자 유형을 개인에서 조직으로 또는 조직에서 개인으로 변경해야 할 수 있습니다. 예를 들어 Nancy는 Fabrikam UK의 영업 팀 구성원입니다. 런던의 무역 박람회에서 그녀는 여섯 명의 새로운 유망주를 만난다. Nancy는 각 잠재 고객에 대한 잠재 고객 당사자 레코드를 생성합니다. Nancy가 레코드를 저장하면 각 레코드가 전체 주소록에도 생성됩니다. Fabrikam은 기본 당사자 유형을 조직으로 설정했지만 새 잠재 고객 중 2명은 레코드 유형의 사람이어야 합니다. 따라서 Nancy가 무역 박람회에서 돌아올 때 두 개의 잠재 고객 레코드의 파티 유형을 변경해야 합니다. 한 당사자 유형에서 다른 당사자 유형으로 당사자 레코드를 변경하려면 먼저 전체 주소록에 올바른 유형의 새 당사자 레코드를 생성해야 합니다. 그런 다음 이전 당사자 레코드를 이 새 레코드와 연결합니다. 새 당사자 연결을 만든 후 레코드 유형이 잘못된 원래 당사자 레코드를 삭제합니다.

## <a name="how-do-i-change-the-name-or-address-of-a-party-record"></a>파티 기록의 이름이나 주소는 어떻게 변경합니까?

당사자 레코드의 이름과 해당 레코드와 연결된 주소를 언제든지 업데이트할 수 있습니다.

- 당사자 레코드의 이름을 업데이트하려면 당사자 레코드를 연 다음 작업 창에서 **편집** 을 클릭합니다. **일반** 빠른 탭에서 파티의 새 이름을 입력한 다음 레코드를 저장합니다.
- 당사자 기록의 주소를 업데이트하려면 당사자 기록을 연 다음 **주소** 빠른 탭에서 업데이트할 주소를 선택합니다. **편집** 을 클릭한 다음 **주소 수정** 페이지에서 주소 또는 주소 매개변수에 필요한 변경을 수행합니다.

## <a name="can-i-merge-two-or-more-party-records-into-one-record"></a>둘 이상의 당사자 레코드를 하나의 레코드로 병합할 수 있습니까?

경우에 따라 둘 이상의 당사자 레코드를 단일 레코드로 병합할 수 있습니다. 이것은 고의로 또는 의도하지 않게 하나 이상의 중복 당사자 레코드를 생성하는 경우에 발생할 수 있습니다. 당사자 기록을 병합할 때 유지할 기록 하나를 선택합니다. 그런 다음 다른 레코드의 정보가 이 레코드에 병합됩니다. 예를 들어 Fabrikam에 대한 정보가 A, B 및 C의 세 당사자 레코드에 저장되어 있음을 발견했습니다. 당사자 레코드 A를 유지하기로 결정했습니다. 따라서 당사자 레코드 B 및 C에 저장된 정보는 당사자 레코드로 병합됩니다. 당사자 기록을 병합할 수 없는 몇 가지 상황이 있습니다.

- 동일한 법인에서 고객 또는 공급업체와 같은 동일한 당사자 역할과 연결된 당사자 레코드를 병합할 수 없습니다. 예를 들어 당사자 A는 법인 123의 고객과 연결되고 당사자 B는 법인 123의 다른 고객과 연결됩니다. 이러한 당사자 레코드는 병합할 수 없습니다. 병합된 경우 병합된 당사자 레코드가 동일한 법인의 여러 고객과 연결되어 허용되지 않기 때문입니다. 그러나 당사자 B가 법인 123의 공급업체 또는 다른 법인의 고객과 연결된 경우 레코드를 병합할 수 있습니다.
- 동일한 법인, 팀 또는 운영 단위에서 내부 당사자 조직 레코드를 병합할 수 없습니다.

## <a name="should-i-create-a-party-record-in-the-global-address-book-or-in-another-place-such-as-the-customer-or-vendor-page"></a>전체 주소록이나 고객 또는 공급업체 페이지와 같은 다른 위치에 당사자 기록을 생성해야 합니까?

전체 주소록이나 해당 엔터티 페이지에 당사자 레코드를 입력할 수 있습니다. 한 위치에 레코드를 추가하면 항상 같은 레코드가 다른 위치에 추가됩니다. 예를 들어, 전체 주소록에 고객의 당사자 레코드를 추가하면 해당 레코드도 **고객** 페이지에 추가됩니다. 마찬가지로 **고객** 페이지에서 고객의 당사자 레코드를 추가하면 해당 레코드도 전체 주소록에 추가됩니다. 다음 지침을 사용하여 새 당사자 레코드를 입력해야 하는 위치를 결정합니다.

- **엔터티 유형을 모르는 경우 당사자 레코드 만들기** – 당사자 레코드를 생성해야 하지만 엔터티 유형을 모르는 경우(예: 엔터티가 고객인지 기회인지 모름) 전체 주소록에 레코드를 생성합니다. 나중에 엔터티 유형을 선택할 수 있습니다.
- **엔터티 유형을 알고 있는 경우 당사자 레코드 만들기** – 당사자의 엔터티 유형을 알고 있는 경우 해당 유형에 대한 해당 페이지에서 레코드를 생성할 수 있습니다. 예를 들어 **고객** 페이지에 고객의 레코드를 만듭니다. 적절한 엔터티 페이지를 사용하여 레코드를 만들고 저장하면 전체 주소록에 자동으로 레코드가 만들어집니다.

## <a name="can-i-translate-address-information-for-party-records"></a>당사자 기록에 대한 주소 정보를 번역할 수 있습니까?

주소 정보의 번역을 설정하여 정보가 프로그램에서는 사용자 언어(시스템 언어)로 표시되지만 판매 주문과 같은 문서에서는 다른 언어로 표시되도록 설정할 수 있습니다. 국가/지역 이름, 주소 용도 및 이름 시퀀스에 대한 번역을 입력할 수 있습니다. 예를 들어, 시스템 언어가 덴마크어이고 프랑스 고객에 대한 판매 주문을 생성합니다. 이 경우 프로그램에서 덴마크어로 된 고객 레코드를 볼 수 있지만 인쇄된 판매 오더에는 프랑스어로 주소 정보를 표시할 수 있습니다. 번역을 설정할 때 목록의 모든 항목에 대한 번역을 입력해야 합니다. 번역을 입력하지 않은 항목은 시스템 언어로 표시됩니다. 예를 들어, 시스템 언어가 덴마크어이고 스페인 고객에게 문서를 보냅니다. 주소 정보에 대해 스페인어(ESP) 번역을 입력하지 않은 경우 해당 정보는 프로그램과 인쇄된 문서 모두에 덴마크어로 표시됩니다.

## <a name="after-i-import-addresses-why-cant-i-edit-the-records"></a>주소를 가져온 후 레코드를 편집할 수 없는 이유는 무엇입니까?

주소를 가져올 때 이름이 **IsLocationOwner** 인 필드가 있습니다. 이 필드는 위치(주소)와 연관된 당사자가 주소의 소유자인지 여부를 나타냅니다. 당사자가 주소의 소유자인 경우 전체 주소록 또는 마스터 레코드 페이지(예: 고객, 공급업체 또는 작업자)에서 당사자를 사용할 때 주소를 편집할 수 있습니다. 당사자가 주소의 소유자가 아닌 경우 레코드를 편집할 수 없습니다. 

주소를 가져올 때 연결된 당사자를 사용하여 주소를 편집할 수 있도록 하려는 경우 **IsLocationOwner** 필드는 **네** 로 설정되어야 합니다. 이 필드를 잘못 가져오면 전체 주소록에서 위치 소유자를 업데이트할 수 있습니다.

가져온 주소의 위치 소유자를 변경하는 방법에 대한 자세한 내용은 [위치 소유자 관리](./global-address-book-location-owner.md)를 참조하세요.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
