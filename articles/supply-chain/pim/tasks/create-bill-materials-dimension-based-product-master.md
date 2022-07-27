---
title: 치수 기반 제품 기준에 대한 자재 명세서 생성
description: 이 절차를 수행하려면 이 8개의 녹음 시퀀스에서 이전 4개의 가이드를 완료해야 합니다.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f86625821f8a01a6d4949f9dca538a279f52ce9c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447838"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>치수 기반 제품 기준에 대한 자재 명세서 생성

[!include [banner](../../includes/banner.md)]

이 절차를 수행하려면 이 8개의 녹음 시퀀스에서 이전 4개의 가이드를 완료해야 합니다. 처음 4개의 녹음은 이 절차를 완료하는 데 필요한 데이터를 설정합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 작업은 일반적으로 제품 디자이너가 처리합니다.

## <a name="select-the-product"></a>제품 선택

1. **제품 정보 관리 \> 제품 \> 릴리스된 제품** 으로 이동합니다.
1. 목록에서 선택한 행을 표시합니다.
    * 이 순서의 첫 번째 작업 가이드에서 생성한 차원 기반 구성 기술을 사용하여 출시된 제품 마스터를 찾습니다.  
1. 작업 창에서 **엔지니어** 를 선택합니다.
1. **BOM 버전** 을 선택합니다.

## <a name="create-new-bom-and-bom-version"></a>새 BOM 및 BOM 버전 생성

1. **새로 만들기** 를 선택합니다.
1. **BOM 및 BOM 버전** 을 선택합니다.
1. **이름** 필드에 값을 입력합니다.
    * 사이트 설정  
    * 이 절차에서는 BOM에 대한 특정 사이트를 설정하지 않습니다.  
1. **확인** 을 선택합니다.
1. **새로 만들기** 를 선택합니다.
    * 이 절차에서는 BOM에 네 줄을 추가합니다. 두 줄은 케이블 옵션을 나타내고 두 줄은 캐비닛 옵션을 나타냅니다.  
1. 목록에서 선택한 행을 표시합니다.
1. **품목 번호** 필드에서 값을 입력하거나 선택합니다.
    * 품목 번호 A0001, HDMI 6' 케이블을 선택합니다.  
1. **구성 그룹** 필드에 값을 입력하거나 선택합니다.
    * 이 순서대로 가이드 4에서 생성한 케이블 구성 그룹을 선택합니다.  
1. **새로 만들기** 를 선택합니다.
    * 품목 번호 A0002, HDMI 12' 케이블을 선택합니다.  
1. 목록에서 선택한 행을 표시합니다.
1. **품목 번호** 필드에서 값을 입력하거나 선택합니다.
1. **구성 그룹** 필드에 값을 입력하거나 선택합니다.
    * 케이블 구성 그룹을 다시 선택합니다.  
1. **새로 만들기** 를 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **품목 번호** 필드에서 값을 입력하거나 선택합니다.
    * 품목 번호 D0002 캐비닛을 선택합니다.  
1. **구성 그룹** 필드에 값을 입력하거나 선택합니다.
    * 이 BOM 라인에 대한 캐비닛 구성 그룹을 선택합니다.  
1. **새로 만들기** 를 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **품목 번호** 필드에서 값을 입력하거나 선택합니다.
    * 마지막 BOM 라인으로 품목 번호 M0007 StandardCabinet을 선택합니다.  
1. **구성 그룹** 필드에 값을 입력하거나 선택합니다.
    * 마지막 BOM 라인에 대한 캐비닛 구성 그룹을 선택합니다.  

## <a name="approve-and-activate"></a>승인 및 활성화

1. 페이지를 닫습니다.
1. **승인** 을 선택합니다.
1. **승인자** 필드에서 값을 입력하거나 선택합니다.
1. **BOM도 승인하시겠습니까?** 필드에서 *예* 를 선택합니다.
1. **확인** 을 선택합니다.
1. **활성화** 를 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]