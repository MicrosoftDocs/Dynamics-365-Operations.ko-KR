---
title: 서비스 계약 및 프로젝트를 위한 통합
description: 서비스 계약 및 서비스 계약 라인으로 작업할 때 프로젝트 관리 및 회계 영역에서 설정된 데이터를 사용합니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a43a8bab6a5e5ea527f4a062feea79b4313cb56f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449146"
---
# <a name="integration-for-service-agreements-and-projects"></a>서비스 계약 및 프로젝트를 위한 통합 

[!include [banner](../includes/banner.md)]


서비스 계약 및 서비스 계약 라인으로 작업할 때 **프로젝트 관리 및 회계** 의 다음 영역에 설정된 데이터를 사용합니다.

## <a name="project-prices"></a>프로젝트 가격

서비스 계약 트랜잭션의 원가 및 판매 가격은 서비스 계약에 첨부된 프로젝트에 적용되는 원가 가격 설정에서 파생됩니다. 프로젝트별, 사원별, 카테고리별로 원가 및 판매가를 설정할 수 있습니다. 

## <a name="project-validation"></a>프로젝트 검증

서비스 계약 라인에서 선택할 수 있는 프로젝트, 직원 및 범주는 **프로젝트 관리 및 회계** 의 검증 설정에 의해 제한될 수 있습니다. 유효성 검사 설정을 사용하여 액세스를 제어하기 위해 직원, 프로젝트 및 범주를 결합할 수 있습니다. 

## <a name="project-line-properties"></a>프로젝트 라인 속성

서비스 계약 라인에 대해 라인 속성이 자동으로 입력됩니다.

라인 속성은 **프로젝트 관리 및 회계** 의 **라인 속성** 양식에서 생성됩니다. 서비스 계약에 입력된 라인 속성은 서비스 계약에 대해 선택되고 이후에 서비스 계약 라인에 상속되는 프로젝트에 첨부됩니다. 

## <a name="default-offset-accounts"></a>기본 상쇄 계정

경비 거래를 입력하면 거래에 대해 기본 경비 상계 계정이 자동으로 선택됩니다. 기본 비용 계정은 현재 서비스 계약에 첨부된 프로젝트에 대해 설정됩니다.

## <a name="project-categories"></a>프로젝트 범주

서비스 계약 라인에 사용할 수 있는 범주는 **프로젝트 관리 및 회계** 의 **프로젝트 범주** 양식에서 설정됩니다. 

> [!NOTE]
> <P><STRONG>프로젝트 카테고리</STRONG> 양식의 <STRONG>프로젝트</STRONG> 탭에서 <STRONG>활성 분개장</STRONG> 확인란이 선택된 카테고리를 선택할 수 있습니다. 그러나 <STRONG>프로젝트 관리 및 회계 매개 변수</STRONG> 양식의 <STRONG>분개</STRONG> 탭에서 <STRONG>비활성 범주</STRONG> 확인란을 선택한 경우 모든 범주를 선택할 수 있습니다.</P>

## <a name="project-parameters"></a>프로젝트 매개 변수

**프로젝트 관리 및 회계 매개 변수** 양식의 **분개** 탭에 있는 **퇴직 근로자** 필드를 선택한 경우 **서비스 계약** 및 **서비스 주문** 양식에서 비활성 직원과 활성 직원을 선택할 수 있습니다.

또한 **서비스 주문** 양식의 **프로젝트** 탭에서 **시작 시간** 및 **종료 시간** 필드를 활성화하여 서비스 주문 라인에 시작 및 종료 시간을 입력할 수 있습니다.

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a>서비스 주문에 대한 시작 및 종료 시간 기능 활성화

1.  **프로젝트 관리 및 회계** \> **설정** \> **프로젝트 관리 및 회계 매개 변수** 를 클릭합니다.

2.  **분개장** 탭을 클릭한 다음 **시작/종료 시간 표시** 확인란을 선택합니다.

3.  **프로젝트 관리 및 회계** \> **설정** \> **분개장** \> **분개장 이름** 을 클릭합니다.

4.  서비스 주문에 첨부된 분개 이름을 선택합니다.

5.  **일반** 탭을 클릭한 다음 **시작/종료 시간 표시** 확인란을 선택합니다.


> [!NOTE]
> <P><STRONG>서비스 관리 매개 변수</STRONG> 양식의 저널 탭에 있는 <STRONG>시간</STRONG> 필드에서 서비스 주문에 대한 <STRONG>분개장</STRONG> 이름을 선택합니다.</P>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]