---
title: 전자 송장 발행을 위한 Azure 리소스 설정
description: 이 항목에서는 전자 송장을 위한 Microsoft Azure 리소스를 설정하는 프로세스에 대한 개요를 제공합니다.
author: dkalyuzh
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: cb1fcddce1054aebf9ef70ba69eb7aca98093cbe
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451696"
---
# <a name="set-up-azure-resources-for-electronic-invoicing"></a>전자 송장 발행을 위한 Azure 리소스 설정

[!include [banner](../includes/banner.md)]

전자 송장을 위한 Microsoft Azure 리소스를 설정하는 프로세스에는 세 가지 단계가 있습니다. 처음 두 단계인 "Azure 포털에서 Azure 키 볼트 생성"과 "Azure 포털에서 Azure 스토리지 계정 생성"은 필수 사항입니다. 세 번째 단계인 "SharePoint 연결 구성"은 선택 사항입니다.

## <a name="create-an-azure-key-vault-in-the-azure-portal"></a>Azure Portal에서 Azure 키 자격 증명 모음 만들기

Azure 구독에 키 볼트를 만듭니다. 전자 송장 발행에 대해 별도의 키 자격 증명 모음을 만들고 비밀을 다른 애플리케이션과 결합하지 않는 것이 좋습니다. 전자 문서의 시나리오에 필요한 만큼의 비밀과 인증서를 만듭니다. 다음 단계에서 만들 Azure 저장소 계정의 SAS(공유 액세스 서명) 토큰을 저장하려면 하나 이상의 비밀을 만들어야 합니다.

이 단계를 완료하는 방법에 대한 자세한 내용은 [Azure 포털에서 Azure 키 볼트 생성](e-invoicing-create-azure-key-vault-azure-portal.md)을 참조하십시오.

## <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Azure 포털에서 Azure 스토리지 계정 생성

귀하는 전자 송장 서비스에 의해 생성되거나 서비스에 진입하는 모든 전자 문서 및 파일을 소유합니다. 이러한 문서 및 파일은 Azure 구독에서 만드는 Azure Storage 계정에 저장됩니다. 서비스는 Key Vault 비밀에서 가져온 SAS 토큰을 사용하여 스토리지 계정에 액세스합니다.

이 단계를 완료하는 방법에 대한 자세한 내용은 [Azure 포털에서 Azure 스토리지 계정 생성](e-invoicing-create-azure-storage-account-azure-portal.md)을 참조하십시오.

## <a name="configure-a-sharepoint-connection"></a>SharePoint 연결 구성

일부 시나리오에서는 전자 파일을 SharePoint에 저장하고 SharePoint에서 검색해야 할 수 있습니다. 전자 송장 서비스가 SharePoint 폴더에 액세스할 수 있도록 하려면 SharePoint 액세스를 구성하십시오.

이 단계를 완료하는 방법에 대한 자세한 내용은 [SharePoint 연결 구성](e-invoicing-create-sharepoint-connection.md)을 참조하십시오.
