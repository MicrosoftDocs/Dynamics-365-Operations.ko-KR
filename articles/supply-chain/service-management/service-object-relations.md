---
title: 서비스 개체 관계
description: 서비스 개체와 서비스 계약 또는 서비스 주문 간에 서비스 개체 관계를 만들 수 있습니다.
author: kamaybac
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7eb5b185ca2ef5903eb1739edfdd7b60749babd4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448900"
---
# <a name="service-object-relations"></a>서비스 개체 관계 

[!include [banner](../includes/banner.md)]

서비스 개체와 서비스 계약 또는 서비스 주문 간에 서비스 개체 관계를 만들 수 있습니다. 관계를 생성할 때 서비스 개체를 서비스 계약 또는 서비스 주문에 첨부합니다.

관계가 생성된 후 서비스 계약 또는 서비스 주문의 모든 라인에 서비스 개체를 첨부할 수 있습니다.

## <a name="template-boms"></a>템플릿 BOM

개체 관계에 대한 템플릿 BOM을 지정할 수도 있습니다. 템플릿 BOM은 서비스를 수행하는 개체에 대한 자재 명세서입니다. 서비스 방문 중에 서비스 개체의 구성 요소 부분을 교체하는 경우 서비스 개체 양식을 사용하여 서비스 BOM에 이 변경 사항을 등록할 수 있습니다.

## <a name="example"></a>예

고객 사이트에서 두 대의 엘리베이터를 서비스하기 위한 서비스 계약을 생성합니다.
서비스 계약의 식별자 ID는 SAL-001입니다.

엘리베이터는 서비스 개체 형태로 개체, EL-S/1000 및 EL-L/1000으로 설정됩니다.

서비스 개체 EL-S/1000 및 EL-L/1000을 서비스 계약에 첨부합니다.

개체의 구성 요소 부분을 교체할 때 서비스 개체의 BOM에 변경 사항을 등록하려고 하므로 다음 표에 설명된 대로 서비스 개체 관계에 서비스 BOM을 첨부합니다.

| 서비스 개체 | 관계 – 서비스 계약 | 서비스 BOM   |
|----------------|------------------------------|---------------|
| EL-S/1000      | ID SAL-001                   | BOM-EL-S/1000 |
| EL-L/1000      | ID SAL-001                   | BOM-EL-L/1000 |

계약에 대한 서비스 개체 관계가 있으므로 이제 다음 표와 같이 이러한 개체로 서비스 계약 라인을 생성할 수 있습니다.

| 트랜잭션 유형 | 카테고리           | 서비스 개체 |
|------------------|--------------------|----------------|
| 시간             | 검사         | EL-S/1000      |
| 시간             | 기어박스 청소  | EL-S/1000      |
| 항목             | 청소 재료 | EL-S/1000      |
| 시간             | 검사         | EL-L/1000      |
| 시간             | 기어박스 청소   | EL-L/1000      |
| 항목             | 청소 재료 | EL-L/1000      |

서비스 방문 시 엘리베이터 EL-S/1000의 기어박스를 교체해야 합니다. 개체의 구성 요소 부분을 교체하려면 현재 서비스 계약에 대해 설정한 서비스 개체 관계를 사용하여 BOM 디자이너에 액세스할 수 있습니다.

서비스 개체 관계를 사용하여 BOM 디자이너에 액세스

1. 서비스 계약
2. 서비스 계약을 두 번 클릭하거나 서비스 계약을 클릭하여 서비스 계약을 생성합니다.
3. 설정 탭을 클릭합니다.
4. 서비스 개체를 클릭하여 템플릿 BOM을 서비스 계약에 첨부합니다.
5. 서비스 개체 양식에서 디자이너를 클릭하여 템플릿 BOM을 수정할 디자이너 양식을 엽니다.

## <a name="automatically-created-service-orders"></a>자동으로 생성된 서비스 주문

서비스 계약에 대한 서비스 주문을 자동으로 생성하는 경우 계약의 서비스 개체 관계도 서비스 주문에 생성됩니다.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]