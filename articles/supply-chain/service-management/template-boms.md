---
title: 템플릿 BOM
description: 템플릿 BOM(자재 명세서)은 정기적으로 서비스되는 서비스 개체에 대한 구성 요소의 표준화된 목록을 제공합니다.
author: kamaybac
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d34502d74590595f26ba5aae78158ed893a095df
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448402"
---
# <a name="template-boms"></a>템플릿 BOM

[!include [banner](../includes/banner.md)]

템플릿 BOM(자재 명세서)은 정기적으로 서비스되는 서비스 개체에 대한 구성 요소의 표준화된 목록을 제공합니다. 템플릿 BOM에 나열된 구성 요소는 서비스 개체의 개별 하위 구성 요소를 나타냅니다. 템플릿 BOM을 서비스 개체에 적용하면 서비스 개체에서 교체된 하위 구성 요소의 기록을 유지할 수 있습니다.

템플릿 BOM을 서비스 계약 또는 서비스 주문에 적용하려면 서비스 개체 관계에 첨부합니다.

> [!NOTE]
> 하나의 템플릿 BOM만 서비스 개체에 적용할 수 있습니다.

## <a name="create-a-template-bom"></a>템플릿 BOM 만들기

다음 표에는 템플릿 BOM을 작성하는 데 사용할 수 있는 다양한 방법에 대한 정보가 포함되어 있습니다.

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>메서드</p></th>
<th><p>설명</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>생산</p></td>
<td><p>템플릿 BOM은 생산 주문을 기반으로 합니다. 이 옵션은 프로덕션 환경에서 작업하는 경우에만 적용할 수 있습니다. 이점은 항목을 구성하는 구성 요소의 최신 세부 목록이 있다는 것입니다.</p></td>
</tr>
<tr class="even">
<td><p>항목 BOM</p></td>
<td><p>템플릿 BOM은 항목 BOM을 기반으로 합니다. 품목 BOM은 생산 BOM과 달리 품목을 구성하는 구성요소의 정적 목록입니다.</p></td>
</tr>
<tr class="odd">
<td><p>기존 템플릿</p></td>
<td><p>템플릿은 기존 템플릿 BOM을 기반으로 합니다.</p></td>
</tr>
<tr class="even">
<td><p>수동</p></td>
<td><p>서비스 개체에서 일반적으로 교체되는 예비 부품을 알고 있는 경우 템플릿 BOM을 수동으로 생성할 수 있습니다. 이 방법은 템플릿에 포함된 구성 요소가 작업장의 실제 요구 사항을 반영하는지 확인하는 데 도움이 됩니다.</p></td>
</tr>
</tbody>
</table>

## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a>서비스 계약 또는 서비스 주문에 템플릿 BOM 적용

템플릿 BOM을 서비스 계약, 서비스 주문 또는 둘 다에 적용할 수 있습니다. 서비스 계약은 일반적으로 고객과의 장기적인 관계를 다룹니다. 서비스 BOM에 기록된 교체 이력은 서비스 계약에 유용한 데이터입니다.

템플릿 BOM을 서비스 주문에 적용하여 서비스 개체에 대해 수행된 서비스 기록을 기록할 수도 있습니다.

## <a name="copy-the-history-of-a-service-bom"></a>서비스 BOM 내역 복사

한 서비스 계약에서 다른 서비스 계약으로 서비스 BOM 라인의 내역을 복사할 수 있습니다. 서비스 계약 간의 서비스 내역을 복사하여 항목에 대한 교체 기록을 보존할 수 있습니다.

### <a name="example"></a>예

고객의 자동차에 대해 3년 서비스 계약을 체결했습니다. 그 기간 동안 고객은 회사가 제공하는 좋은 서비스에 익숙해집니다. 따라서 계약이 만료된 후 고객은 새 계약을 설정하기를 원합니다. 이제 회사에 더 유리한 계약을 협상할 수 있습니다. 교체된 구성요소의 기록은 나중에 유용할 수 있으므로 서비스 BOM의 기록을 새 계약에 복사합니다.

## <a name="modify-the-template-bom"></a>템플릿 BOM 수정

템플릿 BOM이 서비스 개체에 첨부되지 않은 경우 그 안의 라인을 수정하거나 삭제할 수 있습니다. 템플릿 BOM이 서비스 개체에 첨부된 후에는 BOM의 로컬 버전만 수정할 수 있습니다. 템플릿 BOM의 로컬 버전 설정을 복제하려는 경우 로컬 버전을 기반으로 새 템플릿 BOM을 생성할 수 있습니다. 자세한 내용은 [서비스 BOM 수정](modify-service-bom.md)을 참조하세요.

BOM에서 항목을 교체하는 경우 BOM 디자이너의 BOM 라인에 교체를 등록할 수 있습니다. 선택적으로 대체 개체에 대한 서비스 주문 라인을 생성할 수 있습니다. 서비스 주문 라인을 생성하는 경우 대체 품목에 대한 송장을 발행할 수 있습니다. 교체에 대한 서비스 주문 라인을 생성하지 않으면 교체 등록이 유지되어 서비스 개체의 내역을 추적합니다.

## <a name="change-how-information-on-the-bom-line-is-displayed"></a>BOM 라인의 정보 표시 방식 변경

모든 템플릿 및 서비스 BOM에 대해 BOM 라인의 정보가 표시되는 방식을 변경할 수 있습니다. 변경 사항은 모든 템플릿 BOM 및 서비스 BOM에 적용됩니다. 여기에는 서비스 개체에 연결된 개체가 포함됩니다.

## <a name="set-up-number-sequences-for-template-boms"></a>템플릿 BOM에 대한 번호 시퀀스 설정

템플릿 BOM을 사용하려면 두 개의 번호 시퀀스를 설정해야 합니다. 템플릿 BOM에 대해 하나의 번호 시퀀스를 설정하고 BOM 내역 라인 번호에 대해 하나를 설정합니다.

> [!NOTE]
> 번호 시퀀스는 식별자를 필요로 하는 레코드에 식별자를 할당하는 데 사용됩니다. 템플릿 BOM 또는 BOM 히스토리 라인 번호에 일련번호를 지정하려면 먼저 일련번호 코드를 설정해야 합니다.

## <a name="set-up-number-sequences"></a>숫자 시퀀스 설정

1. **번호 시퀀스** 목록 페이지에서 템플릿 BOM 및 BOM 히스토리 라인 번호에 대한 번호 시퀀스를 생성합니다.
1. **서비스 관리** \> **설정** \> **서비스 관리 매개 변수** 를 선택합니다.
1. **번호 시퀀스** 를 선택한 다음 **번호 시퀀스** 양식에서 생성한 번호 시퀀스 참조에 대한 번호 시퀀스 코드를 선택합니다.
1. 변경 내용을 저장하려면 양식을 닫으세요.

> [!NOTE]
> BOM 내역 라인 번호는 시스템에서 BOM 내역의 트랜잭션을 서비스 계약 또는 서비스 주문과 연결하는 데 사용됩니다. 번호는 사용자 인터페이스에 표시되지 않습니다.

## <a name="see-also"></a>참고 항목

[템플릿 BOM 만들기](create-template-bom.md)

[개체 관계에 대한 템플릿 BOM 관리](manage-template-boms-on-object-relations.md)

[서비스 BOM 수정](modify-service-bom.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
