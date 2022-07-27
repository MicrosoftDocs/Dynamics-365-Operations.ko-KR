---
title: 선호하는 기술자 설정
description: 서비스 계약 또는 서비스 주문에 대한 기본 기술자로 모든 작업자를 선택할 수 있습니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dac9af5b0b83875d362f1a9db60c99436d1bb699
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448777"
---
# <a name="set-up-a-preferred-technician"></a>선호하는 기술자 설정 

[!include [banner](../includes/banner.md)]


서비스 계약 또는 서비스 주문에 대한 기본 기술자로 모든 작업자를 선택할 수 있습니다. 단, **디스패치 보드** 에 해당 작업자가 포함되도록 해당 디스패치 팀에 작업자를 추가하는 것이 좋습니다.

## <a name="assign-employee-to-a-dispatch-team"></a>디스패치 팀에 직원 할당

1.  **인적 자원** \> **공통** \> **작업자** \> **작업자** 를 클릭합니다. 작업자를 두 번 클릭하여 작업자 세부 정보 페이지를 엽니다. **작업 창** 에서 **설정** \> **디스패치 팀** 을 클릭하여 **디스패치 작업자** 양식을 엽니다.

2.  **디스패치 팀** 필드에서 작업자를 할당할 팀을 선택합니다.

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a>서비스 계약에 선호하는 기술자 지정

1.  **서비스 관리** \> **공통** \> **서비스 계약** \> **서비스 계약** 을 클릭합니다. 서비스 계약을 두 번 클릭하여 세부 정보 양식을 엽니다.

2.  **일반** 탭에서 **기본 기술자** 필드를 선택한 다음 해당 디스패치 팀의 구성원을 서비스 계약에 대한 기본 기술자로 선택합니다.

## <a name="assign-a-preferred-technician-to-a-service-order"></a>서비스 주문에 선호하는 기술자 지정

1.  **서비스 관리** \> **정기** \> **디스패치 보드** 를 클릭합니다.
    

    > [!NOTE]
    > <P><STRONG>디스패치 보드</STRONG> 양식에서 볼 디스패치 활동의 날짜 범위를 지정합니다. 또한 닫힌 활동을 표시할지 여부와 디스패치 활동 목록을 귀하가 속하거나 모니터링할 권한이 있는 팀으로 제한할지 여부를 지정합니다. <STRONG>확인</STRONG>을 클릭하여 <STRONG>디스패치 보드</STRONG>를 엽니다.</P>



2.  수정할 서비스 활동 라인을 선택합니다.

3.  **관련** 탭에서 **작업자** 목록을 사용하여 해당 디스패치 팀의 구성원을 서비스 호출에 대한 기본 기술자로 지정합니다.

## <a name="see-also"></a>참고 항목

[서비스 계약 개요 개발 및 설정](service-agreements.md)

[수동으로 서비스 주문 만들기](create-service-orders-manually.md)

[서비스 계약(양식)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]