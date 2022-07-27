---
title: 서비스 템플릿
description: 서비스 계약을 템플릿으로 정의하고 템플릿 라인을 나중에 다른 서비스 계약이나 서비스 주문에 복사할 수 있습니다.
author: kamaybac
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 82a19dbee91f13eb3ef56dfd67a775930170b8e7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448894"
---
# <a name="service-templates"></a>서비스 템플릿

[!include [banner](../includes/banner.md)]

서비스 계약을 템플릿으로 정의하고 템플릿 라인을 나중에 다른 서비스 계약이나 서비스 주문에 복사할 수 있습니다.

## <a name="example"></a>예

서비스를 제공하는 고객은 5개의 다른 위치에 동일한 서비스 엘리베이터를 가지고 있습니다.

고객에 대해 사이트당 하나씩 5개의 서비스 계약을 설정하려고 합니다.
반복적인 설정 작업을 제한하고 서비스 계약의 설정 정보가 동일한지 확인하기 위해 서비스 계약을 생성하고 이를 엘리베이터 서비스 작업의 템플릿으로 지정합니다.

이제 템플릿 라인을 5개의 새 서비스 계약에 복사하여 각 서비스 계약이 템플릿의 라인으로 채워지도록 할 수 있습니다.

## <a name="create-a-template"></a>템플릿 만들기

서비스 템플릿을 생성할 때 서비스 계약을 생성하고 이에 필요한 라인을 생성하고 서비스 계약을 서비스 템플릿 그룹에 첨부합니다.

> [!NOTE]
> 서비스 계약은 첨부된 서비스 주문이 없는 경우에만 템플릿으로 정의할 수 있습니다. 또한 템플릿으로 정의된 서비스 계약에서 서비스 주문을 생성할 수 없습니다.

## <a name="copy-template-lines"></a>템플릿 라인 복사

서비스 템플릿의 템플릿 라인을 다른 서비스 계약이나 서비스 주문으로 복사할 수 있습니다.

템플릿 라인을 서비스 주문 또는 서비스 계약에 복사하면 템플릿 그룹이 각 그룹을 확장할 수 있는 트리 보기에 표시됩니다. 이 디스플레이를 통해 각 템플릿과 템플릿 라인을 볼 수 있습니다.

템플릿 사용을 반영하는 이름으로 템플릿을 그룹화한 경우 복사할 서비스 템플릿 행을 결정하는 것이 더 쉽습니다.

## <a name="related-topics"></a>관련 토픽

[서비스 템플릿 라인 복사](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]