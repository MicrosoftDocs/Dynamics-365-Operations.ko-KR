---
title: Warehouse Management 모바일 앱에서 카메라를 사용하여 바코드 스캔
description: 이 주제에서는 모바일 디바이스의 카메라를 사용하여 바코드를 스캔하도록 Warehouse Management 모바일 앱을 설정하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: cc58d88865fea17e0e27463b25e2ba815ee1a5b1
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449521"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a>Warehouse Management 모바일 앱에서 카메라를 사용하여 바코드 스캔

[!include [banner](../includes/banner.md)]

이 주제에서는 모바일 디바이스의 카메라를 사용하여 바코드를 스캔하도록 Warehouse Management 모바일 앱을 설정하는 방법에 대해 설명합니다.

## <a name="setup"></a>설정

Warehouse Management 모바일 앱의 디스플레이 설정에서 바코드 스캔에 카메라를 사용할지 여부를 선택할 수 있습니다. **카메라를 스캐너로 사용** 을 설정하면 기본 입력 모드가 **스캐닝** 으로 설정된 모든 입력 필드에서 카메라를 사용할 수 있습니다.

입력 필드를 스캔할 수 있는지 여부를 제어하려면 **창고 앱 필드 이름** 페이지에서 **기본 입력 모드** 를 **스캐닝** 으로 설정합니다. 이 옵션을 선택하면 Warehouse Management 모바일 앱에서 카메라를 사용하여 스캔할 수 있습니다. 자세한 정보는 [Warehouse Management 모바일 앱의 필드 구성](configure-app-field-names-priorities-warehouse.md)을 참조하세요.

## <a name="supported-bar-code-formats"></a>지원되는 바코드 형식

Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A 및 QR 코드를 포함하여 가장 일반적인 바코드 형식이 지원됩니다.

## <a name="navigation"></a>탐색

카메라 페이지는 입력 필드의 **기본 입력 모드** 가 *스캐닝* 으로 설정된 각 페이지에서 시작됩니다. 카메라 페이지에 있을 때 다음 옵션을 사용하여 탐색합니다.

- 뒤로 단추를 선택하여 **작업 및 세부 정보** 페이지로 돌아갑니다.
- **작업 및 세부 정보** 페이지에서 연필을 선택하면 수동으로 입력할 수 있는 페이지로 이동합니다.
- **작업 및 세부 정보** 페이지에서 카메라를 선택하여 카메라 페이지로 돌아갑니다.

카메라 페이지에서 카메라 단추를 선택하면 바코드를 식별하는 동안 흐리게 표시됩니다. 5초 이내에 바코드가 식별되지 않으면 프로세스가 시간 초과되고 카메라 단추를 다시 사용할 수 있게 됩니다. 그러면 바코드 스캔을 다시 시도할 수 있습니다.

카메라를 바코드에 조준할 때 최상의 결과를 얻으려면 바코드를 브래킷 안에 정렬된 상태로 유지하세요. 바코드가 성공적으로 스캔되면 결과가 처리되고 다음 단계로 이동합니다. 다음 단계에 기본 입력 모드가 스캐닝으로 설정된 다른 입력 필드가 포함되어 있으면 카메라 페이지가 다시 시작됩니다. 다음 단계가 스캐닝 필드가 아니면 카메라 페이지가 시작되지 않습니다.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]