---
title: 공백 상태인 수표 생성
description: 이 문서에서는 은행 계좌에 대한 백지 수표를 생성하는 방법에 대해 설명합니다.
author: angelad116
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 8d3f3857fe5261c1c95d02f3b7c7aaf9db7c096f
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151585"
---
# <a name="create-checks-that-have-blank-status"></a>공백 상태인 수표 생성

[!include [banner](../includes/banner.md)]

이 문서에서는 백지 수표를 만드는 방법에 대해 설명합니다. 예를 들어 손상되어 결제에 사용할 수 없는 수표를 기록하는 용도로 백지 수표를 만들 수 있습니다.

**수표** 페이지에서는 수표 관련 유지 관리 작업을 수행합니다. 예를 들어 새 수표 번호를 만들고 수표를 삭제할 수 있습니다. **백지** 상태인 수표를 만들 수도 있습니다. 생성한 백지 수표는 시스템에서 삭제하거나 재사용할 수 없습니다.

> [!NOTE]
> 이 기능은 **기능 관리** 페이지에서 **수표 페이지에서 백지 상태인 수표 만들기** 기능을 켰을 때만 **수표** 페이지에서 사용할 수 있습니다. 이 기능을 꺼져 있다면 **백지** 상태인 수표는 지급 계정의 결제 생성 프로세스 중에 **수표로 결제** 대화상자를 통해서만 만들 수 있습니다.

**수표** 페이지를 열려면 **현금 및 은행 관리 \> 은행 계좌 \> 은행 계좌** 로 이동한 다음 작업 창의 **결제 관리** 탭에 있는 **관련 정보** 그룹에서 **수표** 를 선택합니다. 또는 **현금 및 은행 관리 \> 문의 및 신고 \> 수표** 로 이동합니다.

그런 다음 **백지** 상태인 수표를 만들기 위해 작업 창에서 **은행 수표 만들기** 를 선택합니다. 시스템에서 백지 수표를 생성하는 동안에는 연결된 은행 계좌가 일시적으로 비활성화됩니다. 이 동작은 결제와 백지 수표가 동시에 생성될 위험을 줄입니다. 처리가 완료되면 연결된 은행 계좌가 다시 활성화됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
