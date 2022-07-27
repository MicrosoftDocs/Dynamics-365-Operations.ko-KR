---
title: 날짜 및 시간 필드 이해
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources에서 날짜 및 시간 필드를 사용할 때 예상되는 사항을 설명합니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7c81155f0c5150af44982f224c8eca2026a78ee7
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451999"
---
# <a name="understand-date-and-time-fields"></a>날짜 및 시간 필드 이해

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



**날짜 및 시간** 필드는 Microsoft Dynamics 365 Human Resources의 기본 개념입니다. 페이지, Dataverse 및 외부 원본에서 **날짜 및 시간** 데이터로 작업하는 방법을 이해하는 것이 중요합니다.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>날짜와 날짜 및 시간 필드 데이터 형식의 차이점 이해

**날짜 및 시간** 필드에는 표준 시간대 정보가 포함되지만 **날짜** 필드는 그렇지 않습니다. **날짜** 필드는 모든 위치에서 같은 정보를 표시합니다. **날짜** 필드에 날짜를 입력하면 같은 날짜가 데이터베이스에 기록됩니다.

**날짜 및 시간** 필드에 데이터가 표시될 때는 **사용자 옵션** 페이지(**공통 \> 설정 \> 사용자 옵션**)에서 선택한 사용자의 표준 시간대를 기준으로 날짜 및 시간이 조정됩니다. 필드에 입력하는 날짜 및 시간 정보는 데이터베이스에 기록된 정보와 같지 않을 수 있습니다.

[![사용자 옵션 페이지.](./media/Useroptionsform.png)](./media/Useroptionsform.png)

## <a name="understanding-date-and-time-fields-on-pages"></a>페이지의 날짜 및 시간 필드 이해 

사용자의 표준 시간대가 협정 세계시(UTC)로 설정되지 않은 경우 화면에 표시되는 **날짜 및 시간** 데이터는 데이터베이스에 저장된 데이터와 같지 않습니다. **날짜와 시간** 필드의 데이터는 항상 UTC로 저장됩니다.

[![작업자 페이지 UTC.](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>데이터베이스의 날짜 및 시간 필드 이해 

**날짜 및 시간** 값이 데이터베이스에 기록될 때 데이터는 UTC로 저장됩니다. 따라서 사용자는 사용자 옵션에 정의된 표준 시간대와 관련된 모든 **날짜 및 시간** 데이터를 볼 수 있습니다.
 
위의 예에서 시작 시간은 특정 날짜가 아니라 특정 시점입니다. 로그인한 사용자의 시간대를 GMT +12:00에서 GMT UTC로 변경하면 같은 레코드에 2019-05-01 12:00:00 대신 2019-04-30 12:00:00이 표시됩니다.

아래 예에서 000724 직원의 고용은 표준 시간대와 관계없이 동시에 활성화됩니다. 직원은 GMT 표준 시간대로 2019-04-30에 활동하며 이는 GMT+12:00 표준 시간대의 2019-05-01과 동일합니다. 둘 다 특정 날짜가 아니라 동일한 시점을 나타냅니다. 

[![작업자 페이지 GMT.](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>Data Management Framework, Excel, Dataverse 및 Power BI의 날짜 및 시간 데이터 

DMF(Data Management Framework), Excel 추가 기능, Dataverse 및 Power BI 보고는 모두 데이터베이스 수준에서 직접 데이터와 상호 작용하도록 설계되었습니다. **날짜 및 시간** 데이터를 사용자의 표준 시간대에 맞게 조정할 클라이언트가 없기 때문에 모든 **날짜 및 시간** 값이 UTC로 되어 있어 데이터를 입력하거나 볼 때 오해할 수 있습니다.
 
**날짜 및 시간** 데이터가 DMF, Excel 또는 Dataverse를 통해 제출되면 데이터베이스는 해당 데이터가 UTC 기준이라고 가정합니다. 그러나 데이터를 보는 사용자의 사용자 표준 시간대가 UTC로 설정되어 있지 않으면 제출된 **날짜 및 시간** 값이 예상대로 표시되지 않고 사용자가 혼동할 수 있습니다. 
 
데이터를 내보낼 때도 역으로 같은 일이 발생할 수 있습니다. 내보낸 DMF 엔터티의 **날짜 및 시간** 데이터는 Dynamics 클라이언트에 표시되는 것과 다를 수 있습니다. 
 
DMF와 같은 외부 소스를 사용하여 데이터를 보거나 작성하는 경우 **날짜 및 시간** 값은 사용자 컴퓨터의 표준 시간대 또는 현재 사용자 표준 시간대 설정과 관계없이 기본적으로 UTC로 간주됩니다. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>다른 제품 영역에 표시되는 같은 레코드의 예 

**사용자 시간대가 UTC로 설정된 Human Resources**

[![작업자 페이지가 UTC로 설정됨.](./media/worker-form3.png)](./media/worker-form3.png)

**사용자 시간대가 GMT +12:00으로 설정된 Human Resources** 

[![작업자 페이지가 GMT로 설정됨.](./media/worker-form4.png)](./media/worker-form4.png)

**OData를 통한 엑셀**

[![OData를 통한 엑셀.](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**DMF 스테이징**

[![DMF 스테이징.](./media/DMFStaging.png)](./media/DMFStaging.png)

**DMF 내보내기**

[![DMF 내보내기.](./media/DMFExport.png)](./media/DMFExport.png)

**Dataverse를 통한 Excel**

[![Dataverse를 통한 Excel.](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>참고 항목

[날짜 및 시간 데이터](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[사용자 기본 표준 시간대](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
