---
title: 포지티브 페이 개요
description: 이 문서는 은행에 제시할 수 있는 전자 수표 목록을 생성하는 데 사용되는 포지티브 페이에 대한 정보를 제공합니다.
author: panolte
ms.date: 08/22/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "88463"
- intro-internal
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 5f36230b68986cffc985353a7130ba429dabd10e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451426"
---
# <a name="positive-pay-overview"></a>포지티브 페이 개요

[!include [banner](../includes/banner.md)]

이 문서는 은행에 제시할 수 있는 전자 수표 목록을 생성하는 데 사용되는 포지티브 페이에 대한 정보를 제공합니다. 

포지티브 페이는 은행에 제시할 수 있는 수표의 전자 목록을 생성하는 데 사용됩니다. 포지티브 페이 파일은 은행이 수표 사기를 예방하는 데 도움이 될 수 있습니다. 수표가 인쇄될 때마다 전자 수표 목록을 생성하도록 포지티브 페이를 설정합니다. 그런 다음 은행에 수표가 제시되면 은행은 수표를 이전에 제출한 수표 목록과 비교합니다. 이 수표가 목록의 수표와 일치하면 은행이 해당 수표를 지웁니다. 수표가 목록의 수표와 일치하지 않으면 은행은 검토를 위해 수표를 보관합니다.

포지티브 페이는 SafePay라고도 합니다. 

포지티브 페이 파일에는 수취인 및 수표 금액에 대한 중요한 정보가 포함될 수 있습니다. 따라서 파일이 생성된 시점부터 은행에서 파일을 받을 때까지 적절한 보안 조치를 사용해야 합니다. 포지티브 페이 파일은 웹 브라우저의 다운로드 지침에 따라 다운로드됩니다. 

포지티브 페이 파일은 데이터 엔터티를 사용하여 생성됩니다. 포지티브 페이 파일을 생성하기 전에 데이터를 은행이 사용할 수 있는 형식으로 변환하는 XML의 변환 형식을 설정해야 합니다. 

포지티브 페이 정보를 생성하려는 각 은행 계정에 포지티브 페이 형식을 할당해야 합니다. 지급을 생성한 후에는 단일 법인 및 단일 은행 계좌에 대한 포지티브 페이 파일을 생성할 수 있습니다. 또는 여러 법인 및 은행 계좌에 대해 동시에 포지티브 페이 파일을 생성할 수 있습니다. 

포지티브 페이 파일에 나열된 수표가 지불되면 은행으로부터 확인 번호를 받게 됩니다. 그런 다음 시스템에서 포지티브 페이 파일을 확인할 수 있습니다. 

포지티브 페이 파일을 변경해야 하는 경우 리콜할 수 있습니다. 그런 다음 포지티브 페이 파일의 각 수표에 대해 해당 수표가 포지티브 페이 파일에 포함되었는지 여부를 나타내는 필드가 재설정됩니다.

자세한 내용은 [포지티브 페이 파일 설정 및 생성](set-up-generate-positive-pay-files.md)을 참조하십시오.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]