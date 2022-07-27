---
title: 서비스 개체 그룹
description: 개체 그룹은 보고서 및 통계용 개체에 대한 데이터를 정렬하고 필터링하는 데 유용합니다.
author: kamaybac
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bfee8bacbf9c62950ff45b90d19258516ec20b20
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448165"
---
# <a name="service-object-groups"></a>서비스 개체 그룹

[!include [banner](../includes/banner.md)]

개체 그룹은 보고서 및 통계용 개체에 대한 데이터를 정렬하고 필터링하는 데 유용합니다. 예를 들어 지리적 위치나 유형별로 개체를 그룹화할 수 있습니다.

## <a name="group-by-geographical-location"></a>지리적 위치별로 그룹화

이 그룹화 방법을 사용하여 회사 서비스의 다양한 다양한 개체가 있는 위치를 표시할 수 있습니다. 예를 들어 회사가 특정 국가/지역에서 이미 서비스를 제공하고 있는 개체를 식별해야 하는 경우 지리적 위치별로 개체를 그룹화하는 것도 유용할 수 있습니다.

## <a name="example-of-grouping-by-geographical-location"></a>지리적 위치별 그룹화의 예

벨기에의 한 고객이 서비스 센터에 전화를 걸어 ABC 개체에 대한 서비스 계약을 생성하려고 합니다. 벨기에에서 서비스되는 모든 개체에 지리적 위치(벨기에)에 대한 개체 그룹을 연결했습니다. 이 그룹을 필터로 사용하면 프로그램에 ABC에 대한 레코드가 이미 있는지 또는 새 개체를 설정해야 하는지 여부를 빠르게 검색할 수 있습니다.

## <a name="group-by-type"></a>유형별 그룹화

이 그룹화 방법을 사용하여 회사에서 서비스하는 개체 유형을 표시할 수 있습니다. 유형별로 개체를 그룹화하는 것은 예를 들어 프로그램에 이미 존재하는 유사한 개체를 기반으로 새 개체를 생성하려는 경우에도 유용할 수 있습니다.

## <a name="example-of-grouping-by-type"></a>유형별 그룹화 예

고객이 전화를 걸어 에어컨 기계 HIJ에 대한 서비스 계약을 설정하려고 합니다. 이 컴퓨터에 대한 레코드가 아직 없습니다. 그러나 Air Conditioners라는 개체 그룹을 설정했으며 이 그룹을 모든 에어컨 개체에 연결했습니다. 따라서 다른 모든 공조 기계를 빠르게 검색 및 식별하고 이러한 개체의 템플릿 정보를 사용하여 HIJ에 대한 서비스 계약 라인을 생성할 수 있습니다. 이러한 방식으로 개체 그룹을 사용하면 새 개체를 빠르게 설정하고 해당 개체에 대해 수행해야 하는 서비스 작업을 결정할 수 있습니다.

## <a name="create-service-object-groups"></a>서비스 개체 그룹 만들기

서비스 개체를 할당할 수 있는 그룹을 만듭니다. 서비스 개체는 서비스가 수행되는 재고 항목 및 기타 제품입니다. 서비스 개체를 그룹화하여 유사하고 관련된 서비스 개체에 대한 보고서를 생성할 수 있습니다. 예를 들어, 서비스 개체 그룹은 두 개의 서비스 개체로 구성될 수 있습니다. 하나의 서비스 개체는 키트이고 두 번째 서비스 개체는 키트를 설치하는 서비스입니다.

서비스 개체 그룹을 만들려면 다음 단계를 따르세요.

1. **서비스 관리 > 설정 > 서비스 개체 > 서비스 개체 그룹** 을 클릭합니다.

2. **새로 만들기** 를 클릭하여 새 서비스 개체 그룹을 만듭니다.

3. 서비스 개체 그룹의 고유 이름을 입력하고 선택적으로 설명을 입력합니다.

**서비스 개체** 양식을 사용하여 서비스 개체를 그룹에 할당할 수 있습니다. 

## <a name="see-also"></a>참고 항목

[서비스 개체 생성](create-service-objects.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]