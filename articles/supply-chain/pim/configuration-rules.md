---
title: 구성 규칙
description: 이 문서에서는 구성 규칙에 대한 일반 정보를 제공합니다. 구성 규칙은 치수 기반 구성 기술을 사용하는 제품의 BOM(자재 명세서) 항목 간의 관계를 정의합니다.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ddc74777ae0cde5367667f93eb29ffb21531e02
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448345"
---
# <a name="configuration-rules"></a>구성 규칙

[!include [banner](../includes/banner.md)]

이 문서에서는 구성 규칙에 대한 일반 정보를 제공합니다. 구성 규칙은 치수 기반 구성 기술을 사용하는 제품의 BOM(자재 명세서) 항목 간의 관계를 정의합니다.

차원 기반 구성 모델을 정의할 때 구성 규칙을 사용할 수 있습니다. 구성 규칙은 BOM(자재 명세서)에서 특정 항목 조합을 시행하거나 금지하는 데 사용됩니다. BOM이 생성되고 관련 항목이 해당 구성 그룹에 할당되면 하나 이상의 구성 규칙을 정의할 수 있습니다. 두 항목이 함께 속하는 경우 **선택** 연산자는 포함을 확인하는 데 사용됩니다. 두 항목이 상호 배타적일 경우, **선택 해제** 연산자는 제외를 확인하는 데 사용됩니다.  

**메모:** 이 정보는 차원 기반 구성 기술을 사용하는 제품 마스터에만 적용됩니다.  

기존 구성은 구성 규칙에 대한 후속 변경의 영향을 받지 않습니다. 그러나 새 구성을 정의하기 전에 규칙을 설정하고 규칙이 변경되었다고 생각되면 확인하는 것이 중요합니다.  

**메모:** **선택** 메서드의 경우 파생 구성 그룹, 품목 번호 및 구성이 자동으로 선택됩니다. **선택 취소** 메서드의 경우 파생 구성 그룹, 품목 번호 및 구성을 선택할 수 없습니다.

## <a name="additional-resources"></a>추가 리소스

[차원 기반 제품 구성 개요](dimension-based-product-configuration.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]