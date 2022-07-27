---
title: 파생 장부
description: 이 문서에서는 파생 장부 기능의 개요를 설명합니다.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32abfce013d0daa208138cf698b2abd1f96462f6
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451063"
---
# <a name="derived-books"></a>파생 장부

[!include [banner](../includes/banner.md)]

이 문서에서는 파생 장부 기능의 개요를 설명합니다.

파생 장부의 목적은 정기적 간격으로 계획된 고정 자산 장부 트랜잭션의 게시를 간소화하는 것입니다.  주 장부로 하나의 장부를 선택합니다. 이는 일반적으로 회계 감가상각에 사용되는 장부입니다. 그런 다음 주 장부와 동일한 간격으로 트랜잭션을 게시하도록 설정된 다른 장부를 이 장부에 첨부합니다. 세금 감가상각 장부는 파생 장부로 설정되는 경우가 많습니다. 

파생 장부에 게시하기 위해 설정하는 가장 일반적인 트랜잭션은 인수, 인수 조정, 폐기입니다. 

## <a name="example"></a>예

장부 B와 장부 C가 취득 트랜잭션 유형의 장부 A에 대한 파생 장부로 설정됩니다. 장부 A에 자산 123에 대한 1,500.00의 취득 트랜잭션을 입력합니다. 

트랜잭션이 게시되면 취득 트랜잭션이 생성되어 자산 123의 장부 B와 자산 123의 장부 C에 1,500.00이 게시됩니다. 고정 자산 분개장에 게시하기 위해 주 분개장의 트랜잭션을 준비할 때 파생 장부의 트랜잭션을 보고 수정할 수도 있습니다. 주 장부 트랜잭션을 다른 분개장에 준비하는 경우 파생된 값의 트랜잭션은 표시되지 않습니다. 그러나 주 장부 트랜잭션을 게시할 때 해당 계정과 게시 계층에 게시됩니다.

> [!NOTE]                                                                                                                               
> 주 장부 간격 이외의 간격으로 트랜잭션을 게시하도록 설정된 장부는 파생 장부가 아닌 별도의 장부로 고정 자산에 첨부해야 합니다.  

자세한 내용은 [파생 장부로 게시](post-derived-value-models.md)를 참조하십시오.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
