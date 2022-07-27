---
title: 시스템 요구 사항
description: 이 항목에는 Microsoft Dynamics 365 Human Resources의 시스템 요구 사항이 나열되어 있습니다.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 15770595a0639c03df1138ec25010ca8168bd9a8
ms.sourcegitcommit: 49f7528d3268abe15e40f719956e1ec8696a6f4e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2021
ms.locfileid: "8451936"
---
# <a name="system-requirements"></a>시스템 요구 사항

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에는 Microsoft Dynamics 365 Human Resources의 시스템 요구 사항이 나열되어 있습니다. 또한 Human Resources을 사용할 수 있는 국가 및 지역과 Human Resources 데이터의 언어 및 현지화에 대한 정보를 간략하게 설명합니다.

## <a name="supported-web-browsers"></a>지원되는 웹 브라우저

사용자는 지정된 운영 체제에서 실행되는 다음 웹 브라우저를 사용하여 Microsoft Dynamics 365 Human Resources에 액세스할 수 있습니다. 

*   Windows 10에서 Microsoft Edge(공개적으로 사용 가능한 최신 버전)
*   Windows 10, Windows 8.1 또는 Windows 7에서 Internet Explorer 11
*   Google Chrome(공개적으로 사용 가능한 최신 버전)
*   Apple Safari(공개적으로 사용 가능한 최신 버전)

각 웹 브라우저의 최신 릴리스를 찾으려면 소프트웨어 제조업체의 웹 사이트로 이동하세요. 

## <a name="special-considerations"></a>특수한 고려 사항

* 작업 레코더가 스크린샷을 캡처하고 생성된 Microsoft Word 문서에 포함할 수 있게 하려면 시험판 Chrome 확장을 설치해야 합니다.
* 워크플로 편집기는 ClickOnce 애플리케이션으로 시작됩니다. Microsoft Edge 및 Internet Explorer만(Microsoft Windows의 지원되는 버전에서) ClickOnce 애플리케이션을 지원합니다. 워크플로 편집기 ClickOnce 애플리케이션에는 64비트 호환 운영 체제가 필요합니다.
* PDF 파일을 미리 보려면 Windows 10에서 Microsoft Edge(공개적으로 사용 가능한 최신 버전) 또는 Windows 10, Windows 8.1, Windows 8, Windows 7 또는 Google Nexus 10 태블릿에서 Google Chrome(공개적으로 사용 가능한 최신 버전)과 같은 최신 브라우저를 사용하는 것이 좋습니다.

## <a name="network-requirements"></a>네트워크 요구 사항

* Human Resources는 대기 시간이 250~300 밀리초(ms) 이하인 네트워크에 맞게 설계되었습니다. 이는 브라우저 클라이언트에서 인적 자원을 호스팅하는 Microsoft Azure 데이터 센터까지의 대기 시간입니다. [www.azurespeed.com](https://www.azurespeed.com "Azure 대기 시간 테스트")에서 네트워크 대기 시간을 테스트하는 것이 좋습니다.
* Human Resources의 대역폭 요구 사항은 시나리오에 따라 다릅니다. 일반적인 시나리오에는 50KBps(초당 킬로바이트) 이상의 대역폭이 필요합니다.
 
> [!WARNING]
> 클라이언트 위치에서 사용자 수에 최소 대역폭 요구 사항을 곱하여 대역폭 요구 사항을 계산하지 마세요. 주어진 위치의 동시 사용량은 계산하기가 매우 어렵습니다. 대역폭 요구 사항에 대해 우려하는 고객의 경우 Human Resources 평가판을 사용하세요.

## <a name="supported-microsoft-office-applications"></a>지원되는 Microsoft Office 애플리케이션

* Microsoft Excel 및 Word 추가 기능을 실행하려면 Windows 또는 Mac용 Microsoft Office 2016을 설치해야 합니다. 버전 요구 사항에 대한 자세한 내용은 [Office 통합 문제 해결](../fin-ops-core/dev-itpro/office-integration/office-integration-troubleshooting.md "Office 통합 문제 해결")을 참조하세요.
* Excel로 내보내기 또는 Word로 내보내기 기능으로 생성된 문서를 보려면 Microsoft Office 2007 이상이 설치되어 있어야 합니다.

## <a name="regional-availability-languages-and-localization"></a>지역별 가용성, 언어 및 현지화

[Microsoft Dynamics 365의 국제 가용성](/dynamics365/get-started/availability)에서 Human Resources가 지원하는 국가, 지역 및 언어의 PDF 파일을 다운로드할 수 있습니다. 

> [!NOTE]
> 사용자 인터페이스가 다른 언어로 현지화되지만 모든 사용자 데이터는 입력된 언어로 저장됩니다. 이메일과 템플릿은 다른 언어로 만들 수 있지만 일정 정보와 같은 데이터는 현재 영어로만 제공됩니다.

국가 또는 지역별 사용자 지정을 만드는 데 관심이 있거나 현재 Microsoft에서 지원하지 않는 국가 또는 지역에 대한 솔루션을 만드는 데 관심이 있는 개발자는 [세계화](/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region)를 참조하세요.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
