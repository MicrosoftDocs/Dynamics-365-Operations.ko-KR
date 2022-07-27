---
title: 서비스 계약 만들기
description: 이 토픽에서는 서비스 관리 및 프로젝트 관리 및 회계 모듈의 기능을 사용하여 서비스 계약을 생성하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: c9a5d580b0bb146bf5d445823b37f607e507f7eb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448186"
---
# <a name="create-service-agreements"></a>서비스 계약 만들기

[!include [banner](../includes/banner.md)]

이 토픽에서는 서비스 관리 및 프로젝트 관리 및 회계 모듈의 기능을 사용하여 서비스 계약을 생성하는 방법에 대해 설명합니다.

## <a name="create-a-service-agreement-from-service-management"></a>서비스 관리에서 서비스 계약 만들기

1. **서비스 관리** 로 이동합니다.
2. **서비스 계약** 을 선택하여 페이지 헤더에 새 서비스 계약 라인을 생성합니다. 
3. **새로 만들기** 를 선택합니다. 설명을 입력하고 **프로젝트 ID** 필드에서 프로젝트에 대한 참조를 선택한 다음 서비스 계약의 나머지 필드와 행을 채웁니다. **저장** 을 선택합니다.
4. **관계** 탭에서 **서비스 개체** 또는 **서비스 작업** 을 선택하여 서비스 계약에 대한 서비스 개체 관계 또는 서비스 작업 관계를 생성합니다. 관계를 생성한 서비스 개체 및 작업은 서비스 계약 라인에 첨부할 수 있습니다.
5. 페이지 하단에서 서비스 템플릿, 다른 서비스 계약의 라인을 복사하거나 서비스 계약 라인을 수동으로 생성하여 서비스 계약 라인을 생성합니다.

> [!NOTE]
> 다른 서비스 계약에서 서비스 계약으로 라인을 복사하는 경우 서비스 개체 및 서비스 태스크 관계도 복사할지 여부를 표시할 수 있습니다. 이러한 관계를 복사하면 서비스 계약의 기존 관계에 추가됩니다. 서비스 템플릿에서 서비스 계약 라인을 복사하면 서비스 개체 및 서비스 작업 관계가 새 서비스 계약 라인에서 서비스 개체 관계 및 서비스 작업 관계로 자동 복사됩니다.

## <a name="create-service-agreement-lines-manually"></a>수동으로 서비스 계약 라인 만들기

1. **서비스 계약** 페이지에서 라인 그리드에 서비스 계약 라인을 추가합니다. 
2. 서비스 계약 라인에 대한 적절한 정보를 입력합니다. 
3. **저장** 을 선택하여 라인을 저장한 다음 페이지를 닫습니다.

## <a name="create-a-service-agreement-from-project"></a>프로젝트에서 서비스 계약 만들기

1. **프로젝트 관리 및 회계** 를 선택합니다.
2. **모두 선택** 을 선택합니다.
3. 목록에서 프로젝트를 선택합니다.
4. **작업 창** 에서 **관리** 를 선택합니다. **새** 작업 그룹에서 **서비스** 를 선택하고 **서비스 계약** 을 선택합니다.
5. 프로젝트 참조를 입력하려면 이 항목의 앞부분에서 설명한 대로 **서비스 계약 만드기** 섹션의 단계를 따르세요.


## <a name="related-topics"></a>관련 토픽

[서비스 계약 개요 개발 및 설정](service-agreements.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]