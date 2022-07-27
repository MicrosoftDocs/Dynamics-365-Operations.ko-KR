---
title: 서비스 개체 관계 만들기
description: 이 토픽에서는 서비스 계약 및 서비스 주문에 대한 서비스 개체 관계를 만드는 방법에 대해 설명합니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a558d513ba97d7df72ee785704b84dd38a5929b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448183"
---
# <a name="create-service-object-relations"></a>서비스 개체 관계 만들기 

[!include [banner](../includes/banner.md)]


이 토픽에서는 서비스 계약 및 서비스 주문에 대한 서비스 개체 관계를 만드는 방법에 대해 설명합니다. 서비스 개체 관계를 만들 때 서비스 개체를 서비스 계약 또는 서비스 주문에 연결합니다. 고객이 서비스 개체인 항목에 대한 서비스를 요청하면 서비스 개체 관계 목록에서 서비스 개체를 선택할 수 있습니다.

## <a name="create-a-service-object-relation-for-a-service-agreement"></a>서비스 계약에 대한 서비스 개체 관계 만들기

서비스 계약에 대한 서비스 개체 관계를 생성하려면 다음 단계를 따르세요.

1.  **서비스 관리** \> **공통** \> **서비스 계약** \> **서비스 계약** 을 클릭합니다.

2.  **서비스 계약** 목록에서 기존 서비스 계약을 선택하거나 **새로 만들기** 를 클릭하여 새 서비스 계약을 만듭니다.

3.  **서비스 계약** 양식의 **작업** 창에 있는 **서비스 계약** 탭에 있는 **관계** 그룹에서 **서비스 개체** 를 클릭합니다.

4.  **서비스 개체** 양식에서 **새로 만들기** 를 클릭한 다음 이 서비스 계약에 대한 서비스 개체를 선택합니다.

5.  템플릿 BOM(자재 명세서)을 서비스 계약에 할당하려면 **기능** 을 클릭한 다음 **템플릿 BOM 첨부** 를 선택합니다. **템플릿 BOM 선택** 양식의 **템플릿 BOM** 필드에서 템플릿을 선택합니다. 

## <a name="create-a-service-object-relation-for-a-service-order"></a>서비스 주문에 대한 서비스 개체 관계 만들기

서비스 주문에 대한 서비스 개체 관계를 생성하려면 다음 단계를 따르세요.

1.  **서비스 관리** \> **공통** \> **서비스 주문** \> **서비스 주문** 을 클릭합니다.

2.  **서비스 주문** 목록에서 기존 서비스 주문을 선택하거나 새 서비스 주문을 생성합니다.

3.  **서비스 주문** 양식의 **작업** 창에 있는 **서비스 주문** 탭에 있는 **관계** 그룹에서 **서비스 개체** 를 클릭합니다.

4.  **서비스 개체** 양식에서 **새로 만들기** 를 클릭한 다음 이 서비스 주문에 대한 서비스 개체를 선택합니다.

5.  템플릿 BOM을 서비스 계약에 할당하려면 **기능** 을 클릭한 다음 **템플릿 BOM 첨부** 를 선택합니다. **템플릿 BOM 선택** 양식의 **템플릿 BOM** 필드에서 템플릿을 선택합니다. 


## <a name="see-also"></a>참고 항목

[서비스 개체 개요](service-objects.md)

[서비스 개체 관계](service-object-relations.md)

[템플릿 BOM](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]