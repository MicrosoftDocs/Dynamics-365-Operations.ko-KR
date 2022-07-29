---
title: 아카이브 ER 대상 유형
description: 이번에는 전자 보고(ER) 형식의 각 FOLDER 또는 FILE 구성 요소에 대한 아카이브 대상을 구성하는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: e2566fc5115df8b47277fc6b6d7f4698cea0a00bea83bcb17e9d7a9e9b765b65
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460860"
---
# <a name="archive-er-destination-type"></a>아카이브 ER 대상 유형

[!include [banner](../includes/banner.md)]

아웃바운드 문서를 생성하도록 구성된 전자 보고(ER) 형식의 각 **폴더** 또는 **파일** 구성 요소에 대한 아카이브 대상을 구성할 수 있습니다. 대상 설정에 따라 생성된 문서는 ER 작업 목록 기록의 첨부 파일로 저장됩니다. 결과를 보려면 **조직 관리** \> **전자 보고** \> **전자 보고 작업** 으로 이동하십시오.

이 옵션을 사용하여 생성된 문서를 Microsoft SharePoint 폴더 또는 Microsoft Azure 저장소로 보낼 수 있습니다. 선택한 문서 유형으로 정의된 대상으로 출력을 보내려면 **사용** 을 **예** 로 설정합니다. 그룹이 **파일** 로 설정된 문서 유형만 선택할 수 있습니다. **조직 관리** \> **문서 관리** \> **문서 유형** 에서 문서 [유형](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types)을 정의합니다. ER 대상에 대한 구성은 문서 관리 시스템에 대한 구성과 동일합니다.

[![문서 유형 페이지.](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

위치는 파일이 저장되는 위치를 결정합니다. **아카이브** 대상이 활성화되면 결과를 작업 아카이브에 저장할 수 있습니다. **조직관리** \> **전자보고** \> **전자보고 아카이브 작업** 에서 결과를 볼 수 있습니다.

> [!NOTE]
> **조직 관리** \> **작업 공간** \> **전자 보고** \> **전자 보고 매개 변수** 로 이동하여 작업 아카이브에 대한 문서 유형을 선택합니다. 자세한 내용은 [전자 보고(ER) 프레임워크](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup) 구성을 참조하십시오.

## <a name="sharepoint"></a>SharePoint

지정된 SharePoint 폴더에 파일을 저장할 수 있습니다. 기본 SharePoint 서버를 정의하려면 **조직 관리** \> **문서 관리** \> **문서 관리 매개 변수** 로 이동하십시오. **SharePoint** 탭에서 SharePoint 폴더를 구성합니다. 이후 ER 출력이 저장될 폴더로 선택할 수 있습니다. 이 문서 유형에서 **SharePoint** 위치를 선택해야 합니다.

[![SharePoint 폴더 선택.](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Azure 저장소

문서 유형 위치가 **Azure 저장소** 로 설정되면 파일을 Azure 저장소에 저장할 수 있습니다.

> [!NOTE] 
> ER 프레임워크는 처리해야 하는 문서에 대해 7일 보존 정책을 적용하는 데이터 관리 프레임워크와 달리 Azure Blob Storage에 파일을 영구적으로 저장합니다. 자세한 내용은 [메시지 상태 가져오기 API](../data-entities/recurring-integrations.md#api-for-getting-message-status) 및 [상태 확인 API](../data-entities/data-management-api.md#status-check-api)를 참조하십시오. ER 관련 파일은 필요한 만큼 Azure Blob Storage에 애플리케이션 테이블 기록의 첨부 파일로 저장됩니다. 단일 파일은 이 파일이 연결된 애플리케이션 테이블 기록와 함께 Azure Blob Storage에서 삭제됩니다.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고(ER) 개요](general-electronic-reporting.md)
- [전자 보고(ER) 대상](electronic-reporting-destinations.md)
- [문서 관리 구성](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]