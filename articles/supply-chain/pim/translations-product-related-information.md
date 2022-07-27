---
title: 제품 관련 번역 FAQ
description: 이 토픽에서는 제품, 제품 차원 값 및 제품 특성에 대한 번역을 관리하는 방법에 대해 설명합니다.
author: t-benebo
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysTranslationDetail, SysTranslationLanguage, SysTranslationList, EcoResProductListPage, EcoResProductVariants, EcoResProductDetailsExtended, EcoResProductCreate, EcoResProductDetails, RetailSizeGroupTable, RetailStyleGroupTable, RetailColorGroupTable, PCTranslationLanguageLookup, EcoResProductCategory
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201853
ms.assetid: c0286bba-f54b-42de-904c-81fd796bdd1d
ms.search.region: global
ms.search.industry: Product information
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24a341973b8648b1a697c8c07b6ecbc808e0e504
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448318"
---
# <a name="product-related-translations-faq"></a>제품 관련 번역 FAQ

[!include [banner](../includes/banner.md)]

이 토픽에서는 제품, 제품 차원 값 및 제품 특성에 대한 번역을 관리하는 방법에 대해 설명합니다. 

## <a name="what-product-related-data-can-be-translated"></a>어떤 제품 관련 데이터를 번역할 수 있습니까?

다음 제품 관련 정보에 대한 번역을 생성할 수 있습니다.
-   제품의 이름과 설명.
-   제품 특성 값의 설명, 식별 이름 및 도움말 텍스트.
-   제품 차원 값의 이름 및 설명.

제품 관련 정보를 **텍스트 번역** 페이지에서 사용할 수 있는 모든 언어로 번역할 수 있습니다. 자세한 내용은 **제품 관련 정보에 대한 번역을 어떻게 생성합니까** 섹션을 참조하세요.

## <a name="where-can-i-view-the-translated-information"></a>번역된 정보는 어디에서 볼 수 있나요?
번역이 가능한 언어를 사용하는 송장과 같은 외부 소스 문서에서 제품 관련 정보의 번역을 볼 수 있습니다.

## <a name="how-do-i-create-translations-for-product-related-information"></a>제품 관련 정보에 대한 번역은 어떻게 만듭니까?
제품에 대한 번역을 생성하려면 다음 단계를 따르세요.
1.  **제품 정보 관리** &gt; **공통** &gt; **출시된 제품** 을 클릭합니다.
2.  제품을 선택하고 작업 창의 **언어** 그룹에서 **번역** 을 클릭합니다.
3.  **텍스트 번역** 페이지의 **언어** 필드에서 언어를 선택합니다. 더 많은 언어를 추가하려면 **언어** 필드를 확장한 다음 **확인** 을 클릭합니다.
4.  **번역된 텍스트** 그룹에서 **설명** 및 **제품 이름** 필드에 번역을 입력합니다.

제품 특성에 대한 번역을 생성하려면 다음 단계를 따르세요.
1.  **제품 정보 관리** &gt; **공통** &gt; **출시된 제품** 을 클릭합니다.
2.  **설정** 에서 **특성** 을 클릭한 다음 **특성** 을 클릭합니다.
3.  **특성** 페이지에서 **번역** 을 클릭합니다.
4.  **텍스트 번역** 페이지의 **언어** 필드에서 언어를 선택합니다. 더 많은 언어를 추가하려면 **언어** 필드를 확장한 다음 **확인** 을 클릭합니다.
5.  **번역된 텍스트** 그룹에서 **설명**, **식별 이름** 및 **도움말 텍스트** 필드에 번역을 입력합니다.

제품 크기 값에 대한 번역을 생성하려면 다음 단계를 따르세요.
1.  **제품 정보 관리** &gt; **공통** &gt; **출시된 제품** 을 클릭합니다.
2.  제품을 선택하고 **제품 크기** 를 클릭합니다.
3.  제품 크기에 대한 링크(**구성**, **크기**, **색상** 또는 **스타일**) 중 하나를 선택합니다.
4.  차원 값을 선택한 다음 **번역** 을 클릭합니다.
5.  **텍스트 번역** 페이지의 **언어** 필드에서 언어를 선택합니다. 더 많은 언어를 추가하려면 **언어** 필드를 확장한 다음 **확인** 을 클릭합니다.
6.  **번역된 텍스트** 그룹에서 **이름** 및 **설명** 필드에 번역을 입력합니다.

## <a name="can-the-names-of-product-variants-be-translated"></a>제품 변형의 이름을 번역할 수 있습니까?
제품 변형은 출시된 제품의 치수를 기반으로 합니다. 제품 변형 이름은 차원 값의 조합을 기반으로 합니다. 제품 변형과 연결된 차원 값이 번역되면 제품 변형의 이름이 번역된 버전에 나타납니다.  

**예**  

제품은 다양한 크기와 색상으로 제공되는 티셔츠이며 변형 이름은 다음 세부 정보를 기반으로 합니다.
-   제품 번호: \#3
-   치수: 크기 및 색상
-   크기 차원 값: 스몰, 미디엄, 라지
-   색상 차원 값: 빨강, 녹색, 검정

스몰 및 빨강 차원 값을 기반으로 하는 제품 변형의 이름은 **\#3:Small:Red** 입니다.  

고객이 스몰 빨간색 티셔츠를 사고 싶어 하며 티셔츠 이름이 송장에 프랑스어로 표시되어야 합니다. 치수 값인 스몰 및 빨강을 프랑스어로 번역하고 제품 변형 이름은 **\#3:Petit:Rouge** 입니다.
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>팁</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>고객이 선호하는 언어를 설정하려면 다음 단계를 따르세요.
<ol><br/><li><strong>영업 및 마케팅</strong> &gt; <strong>공통</strong> &gt; <strong>고객</strong> &gt; <strong>모든</strong> <strong>고객</strong>을 클릭합니다.</li>
<li>고객을 두 번 클릭하여 <strong>고객</strong> 페이지를 엽니다. <strong>일반</strong> 탭의 <strong>언어</strong> 필드에서 <strong>언어</strong>를 선택합니다.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>고객에게 번역이 제공되지 않는 기본 언어가 있는 경우 어떻게 됩니까?
고객이 선호하는 언어로 번역을 사용할 수 없는 경우 이름과 설명은 귀사의 글로벌 언어로 표시됩니다.

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>일련의 차원 값에 대한 번역을 동시에 관리할 수 있습니까?
차원 값은 제품에 따라 다르며 각 제품의 차원 값에 대한 변환을 관리할 수 있습니다. 그러나 차원 값 그룹을 생성하고 값 그룹의 값에 대한 번역을 생성하면 번역을 관리하기가 더 쉽습니다.   

**예**  

회사에서는 다양한 스타일의 티셔츠를 생산하며 각 스타일은 스몰, 미디엄, 라지 사이즈로 제공됩니다. 크기는 하나의 차원 값 그룹에 수집됩니다. 새 티셔츠 스타일이 추가되면 크기에 사용되는 치수 값 그룹과 연결하여 제품에 모든 크기를 사용할 수 있습니다. 또한 언제든지 치수 값 그룹의 크기에 대한 변환을 추가하거나 변경할 수 있습니다.  

차원 변형 그룹을 통해 제품과 연결된 차원 값은 제품 변형 그룹에서 유지되어야 합니다.   
차원 값 그룹을 생성하려면 다음 단계를 따르세요.
1.  **제품 정보 관리** &gt; **설정** &gt; **변형 그룹** 을 클릭합니다.
2.  **크기** **그룹**, **색상 그룹** 또는 **스타일 그룹** 을 선택합니다.
3.  **새로 만들기** 를 클릭한 다음 **크기** **그룹**, **색상 그룹** 또는 **스타일 그룹** 필드에 그룹 이름을 입력합니다. **크기**, **색상** 또는 **스타일** 을 클릭하여 그룹에 대한 라인을 만듭니다.
4.  **크기** **그룹** 라인, **색상** **그룹** **라인** 또는 **스타일 그룹 라인** 페이지에서 **새로 만들기** 를 클릭한 다음 그룹의 크기, 색상 및 스타일을 만듭니다.

차원 값 그룹의 값에 대한 변환을 관리하려면 다음 단계를 따르세요.
1.  차원 값 그룹을 만드는 이전 절차의 단계에 따라 **크기 그룹 라인**, **색상 그룹 라인** 또는 **스타일 그룹 라인** 페이지를 엽니다.
2.  **텍스트 번역** 을 클릭합니다. **텍스트 번역** 페이지의 **번역된 텍스트** 그룹에서 **이름** 및 **설명** 필드에 번역을 입력합니다.

## <a name="when-can-translations-of-product-related-information-be-managed"></a>제품 관련 정보의 번역은 언제 관리할 수 있습니까?
제품 관련 정보의 번역은 언제든지 관리할 수 있습니다. 제품과 연결된 차원 값에 대한 번역이 업데이트되면 제품에 트랜잭션이 있는지 여부에 관계없이 제품 정보가 업데이트됩니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]