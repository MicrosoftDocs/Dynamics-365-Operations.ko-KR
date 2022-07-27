---
title: 부서를 만들고 부서 계층 구조에 포함
description: 부서는 조직의 범주 또는 기능 영역을 나타내는 운영 단위입니다. 부서는 영업, 회계 또는 인사와 같은 조직의 특정 영역을 담당합니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HierarchyDesigner, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 8571b254a3dcdeaf562a97f165b8124f04ae7e6d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452494"
---
# <a name="create-departments-and-include-them-in-the-department-hierarchy"></a>부서를 만들고 부서 계층 구조에 포함


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

부서는 조직의 범주 또는 기능 영역을 나타내는 운영 단위입니다. 부서는 영업, 회계 또는 인사와 같은 조직의 특정 영역을 담당합니다. 부서를 사용하여 기능 영역에 대해 보고할 수 있습니다. 부서에는 손익 책임이 있을 수 있습니다.

부서에는 비용 센터 그룹이 포함될 수 있습니다. 직위가 부서에 할당될 수 있습니다. 부서를 만들려면 **Human Resources** &gt; **부서** &gt; **부서** 를 클릭합니다. 다음 표에서는 사용 가능한 필드에 대해 설명합니다.

| 필드               | 설명                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **이름**                | 부서 이름을 입력합니다.                                                                                                                                                                                  |
| **부서 번호**   | **번호 시퀀스** 페이지의 **조직 번호** 참조에 번호 시퀀스 코드가 할당된 경우 기본값이 자동으로 생성될 수 있습니다.                                                 |
| **검색 이름**         | 부서를 검색하는 데 사용할 수 있는 이름이나 약어를 입력합니다.                                                                                                                                            |
| **메모**                | 추가 정보가 있으면 여기에 입력합니다.                                                                                                                                                                            |
| **계층 구조에 포함**        | 확인란이 선택되면 해당 부서가 부서 계층에 포함되어 있음을 나타냅니다. 부서 계층 구조에 부서를 추가하는 방법에 대한 자세한 내용은 이 문서 뒷부분의 정보를 참조하세요. |
| **DUNS 번호**         | DUNS는 데이터 범용 번호 시스템을 의미합니다. Dun & Bradstreet에서 발행한 9자리 숫자입니다.                                                                                                     |
| **관리자**             | 부서를 관리하는 가상 사용자를 입력합니다.                                                                                                                                                                    |
| **주소**           | 부서의 주소 정보를 추가합니다. 예를 들어 부서가 위치한 건물의 우편 주소를 추가합니다.                                                                          |
| **연락처 정보** | 부서의 연락처 정보를 추가합니다. 예를 들어 부서의 서비스 데스크 전화번호를 추가합니다.                                                                                           |

부서 계층에 부서를 추가하려면 다음 단계를 따릅니다.

1.  **Human Resources** &gt; **부서** &gt; **부서 계층** 을 클릭합니다.
2.  **편집** 을 클릭한 다음 해당 부서가 속한 조직을 선택합니다.
3.  **삽입** 을 클릭하고 목록에서 **부서** 를 선택합니다.
4.  표시되는 부서 목록에서 계층에 추가할 부서를 선택합니다.
5.  변경 사항을 저장합니다. 계층 구조의 초안 버전이 생성되었다는 메시지를 받습니다.
6.  준비되면 계층 디자이너에서 **게시** 를 클릭합니다. 계층이 게시되어야 하는 시기를 나타내는 적용 날짜를 입력할 수 있습니다. 예를 들어 다음 역년 초에 새 부서를 추가하려면 적용 날짜를 새 역년의 1월 1일로 설정합니다. 계층 구조에 대한 변경 사항이 해당 날짜에 적용됩니다.

## <a name="steps-for-creating-a-department"></a>부서를 만드는 단계
새 부서를 만드는 단계별 절차는 [새 부서 정의](./hr-personnel-define-departments.md) 문서를 참조하세요. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
