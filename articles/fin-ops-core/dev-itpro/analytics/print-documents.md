---
title: 문서 인쇄 개요
description: 로컬 프린터 또는 네트워크에 연결된 장치를 사용하여 문서를 인쇄할 수 있습니다. 이 문서에서는 문서 인쇄 방법에 대한 개요를 제공합니다.
author: RichdiMSFT
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: IT Pro, Application User
ms.reviewer: kfend
ms.custom:
- "69161"
- intro-internal
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b9105ef39e411ac33043f1941d4e1dd32b758e5
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460826"
---
# <a name="document-printing-overview"></a>문서 인쇄 개요

[!include [banner](../includes/banner.md)]

로컬 프린터 또는 네트워크에 연결된 장치를 사용하여 문서를 인쇄할 수 있습니다. 이 문서에서는 문서 인쇄 방법에 대한 개요를 제공합니다.

## <a name="printing-overview"></a>인쇄 개요

이 응용 프로그램은 비즈니스 활동을 지원하는 문서를 쉽게 생성, 저장 및 배포할 수 있도록 하는 통합 서비스 및 클라이언트 응용 프로그램을 제공합니다. 로컬 프린터 또는 네트워크에 연결된 장치를 사용하여 문서를 인쇄할 수 있습니다. 또한 클라이언트에서 직접 페이지와 보고서를 PDF 파일 또는 Microsoft Office 문서로 내보낼 수 있습니다. 마지막으로 분산 워크로드를 사용하면 네트워크 리소스를 사용하여 모바일 장치에서 직접 비즈니스 문서를 인쇄할 수 있습니다. 인쇄 요구 사항은 다를 수 있지만 모든 산업 분야에서는 일반적으로 응용 프로그램을 사용하여 비즈니스 문서의 하드 카피를 만들어야 합니다. 호스트된 응용 프로그램에서 네트워크 장치의 문서를 인쇄하는 것은 고유한 문제 세트를 나타냅니다. 여기 예시들이 있습니다 :

- 사용자의 장치에서 인쇄 드라이버를 사용하지 못할 수 있습니다.
- 사용자의 장치가 회사 네트워크에 연결되어 있지 않을 수 있습니다.

전용 호스트를 사용하고 몇 가지 간단한 단계를 따르면 시스템 관리자는 사용자가 네트워크 장치의 비즈니스 응용 프로그램에서 직접 인쇄할 수 있도록 배포를 구성할 수 있습니다.

### <a name="application-printing-scenarios"></a>애플리케이션 인쇄 시나리오 

다음 표에서는 세 가지 기본 인쇄 시나리오에 대해 설명합니다.

| 시나리오                        | 목표                                                      | 해결 방법 |
|---------------------------------|-----------------------------------------------------------|----------|
| 1. 보이는 대로 인쇄하기        | 현재 브라우저에 표시된 내용을 인쇄합니다.             | 브라우저에 대해 "인쇄용" 버전의 웹 페이지가 생성됩니다. |
| 2. 인터랙티브 프린팅         | 로컬로 연결된 장치에서 정밀 문서를 인쇄합니다. | 보고서의 PDF 버전을 내보내고 브라우저로 다운로드할 수 있습니다. |
| 3. 네트워크 장치에서 인쇄 | 정밀 문서를 도메인 프린터 장치로 보냅니다.     | 정밀 문서는 고객의 도메인에서 호스팅되는 서버에서 실행되는 클라이언트 응용 프로그램으로 전송됩니다. |

솔루션이 시나리오에 따라 다르기 때문에 애플리케이션은 사용자가 목표를 달성하는 데 도움이 되는 기본 제공 서비스와 도구를 제공합니다.

- **시나리오 1** 은 HTML5 클라이언트의 브라우저 렌더링에서 지원됩니다.
- **시나리오 2** 는 클라이언트 응용 프로그램 및 Microsoft 365 서비스를 사용합니다.
- **시나리오 3** 은 클라이언트 응용 프로그램 및 Microsoft Azure에서 호스팅되는 서비스의 지원이 필요합니다.

Azure 구독에 배포된 플랫폼 외에도 재무 및 운영 애플리케이션은 고객에게 도메인 호스팅 장치를 사용하여 문서를 보다 쉽게 인쇄할 수 있도록 지원하는 통합된 자사 Azure 애플리케이션을 제공합니다.

## <a name="service-overview"></a>서비스 개요
호스팅된 애플리케이션에서 생성된 문서는 네트워크 연결 장치에서 인쇄되기를 기다리는 동안 Azure Blob Storage에 저장됩니다. [네트워크 인쇄를 활성화하려면 Document Routing Agent 설치](install-document-routing-agent.md)는 Azure 인증을 사용하여 Azure 서비스에 대한 보안 채널을 설정합니다.

**실행 시퀀스**

1. 보고서는 Microsoft SQL Server Reporting Services(SSRS)에서 생성되며 Azure Blob Storage에 저장됩니다. 첨부된 프린터 설정은 문서와 함께 저장됩니다.
2. 문서 라우팅 에이전트는 활성 작업에 대해 Azure Service Bus 큐를 쿼리합니다.
3. 문서는 Document Routing Agent에 의해 다운로드되고 네트워크 프린터로 스풀링됩니다.

클라이언트 기반 솔루션을 통해 고객은 인쇄 요구 사항의 규모를 관리할 수 있습니다. 대량 인쇄 작업이 있는 고객은 많은 Document Routing Agent를 설치하여 동시 인쇄 작업 수를 늘릴 수 있습니다. 또는 일부 고객은 예상되는 인쇄 요구 사항을 처리하기 위해 Document Routing Agent를 거의 설치하지 않아도 됩니다.

### <a name="service-components-for-network-printing"></a>네트워크 인쇄용 서비스 구성 요소

다음 다이어그램은 네트워크 인쇄 작업을 지원하는 기본 구성 요소를 보여줍니다.

[![service-components-for-network-printing\_2016.](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)

단일 프린터를 여러 Document Routing Agent에 등록할 수 있습니다. 프린터 기본 설정을 해결하기 위해 호스트된 서비스는 모든 네트워크 프린터를 고유하게 식별하는 네트워크 경로를 사용합니다. 따라서 여러 클라이언트에서 프린터를 등록한 경우에도 응용 프로그램에서 사용할 수 있는 프린터 목록에서 단일 선택 항목으로 나타납니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]