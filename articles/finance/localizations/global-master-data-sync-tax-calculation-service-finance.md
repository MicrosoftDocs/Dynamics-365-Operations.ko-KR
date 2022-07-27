---
title: 세금 계산 서비스의 세금 설정을 Dynamics 365 Finance로 동기화
description: 이 항목에서는 세금 계산 서비스의 세금 설정 마스터 데이터를 Microsoft Dynamics 365 Finance로 동기화하는 방법을 설명합니다.
author: wangchen
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegration, TaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: d5d994934014a146f825431cb53dfbef8fe20bc8
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2022
ms.locfileid: "8451339"
---
# <a name="sync-the-tax-setup-from-the-tax-calculation-service-to-dynamics-365-finance"></a>세금 계산 서비스의 세금 설정을 Dynamics 365 Finance로 동기화

[!include [banner](../includes/banner.md)]

이 항목에서는 세금 계산 서비스의 세금 설정 마스터 데이터를 Microsoft Dynamics 365 Finance로 동기화하는 방법을 설명합니다.

[세금 계산 시작](global-get-started-with-tax-calculation-service.md)에서 필수 설정 단계를 완료하면 다음 세금 설정 데이터가 세금 계산 서비스에서 Finance로 자동 동기화됩니다.

## <a name="sales-tax-code"></a>판매세 코드

| 세금 계산 서비스           | Finance                             |
| --------------------------------- | ----------------------------------- |
| 세금 코드                          | 판매세 코드                      |
| 설명                       | 이름                                |
| 사용자 입력                        | 정산 기간                   |
| 사용자 입력                        | 원장 기장 그룹                |
| 사용자 입력                        | 판매세 통화                  |
| 음수 세율이 구성됨 | 음수 판매세 비율 허용 |

## <a name="tax-value"></a>세금 가치

| 세금 계산 서비스 | Finance                   |
| ----------------------- | ------------------------- |
| 시작 거래일   | 시작일                 |
| 종료 거래일     | 종료일                   |
| 최소 금액          | 최소 한도             |
| 최대 금액          | 최대 한도             |
| 세율                | 값                     |
| 공제 불가 비율     | 공제 불가 백분율 |

## <a name="tax-limits"></a>세금 한도

| 세금 계산 서비스 | Finance           |
| ----------------------- | ----------------- |
| 시작 거래일   | 시작일         |
| 종료 거래일     | 종료일           |
| 최소 세액      | 최소 판매세 |
| 최대 세액      | 최대 판매세 |

## <a name="sales-tax-group"></a>판매세 그룹

| 세금 계산 서비스                         | Finance                                    |
| ----------------------------------------------- | ------------------------------------------ |
| 세금 그룹                                       | 판매세 그룹                            |
| 이 세금 그룹의 세금 코드                  | 이 판매세 그룹의 판매세 코드 |
| 세금 코드는 **면세** 로 표시됨         | 면제                                     |
| 세금 코드는 **면세** 로 표시됨         | 면세 코드                                |
| 세금 코드는 **수신인 부담** 으로 표시됨 | 수신인 부담                             |
| 세금 코드는 **사용세** 로 표시됨        | 사용세                                    |

## <a name="item-sales-tax-group"></a>품목 판매세 그룹

| 세금 계산 서비스             | Finance                                         |
| ----------------------------------- | ----------------------------------------------- |
| 품목 세금 그룹                      | 품목 판매세 그룹                            |
| 이 품목 세금 그룹의 세금 코드 | 이 품목 판매세 그룹의 판매세 코드 |

동기화가 완료된 후 게시 및 보고 목적으로 Finance의 나머지 매개 변수를 계속 유지 관리합니다.

> [!NOTE]
> Finance에서 세금 계산 서비스로의 세금 설정 동기화는 지원되지 않습니다. 기존 Finance 환경의 경우 먼저 세금 계산 서비스에서 세금 설정을 생성합니다. 그런 다음 설정 데이터를 Finance 환경에 다시 동기화합니다.
