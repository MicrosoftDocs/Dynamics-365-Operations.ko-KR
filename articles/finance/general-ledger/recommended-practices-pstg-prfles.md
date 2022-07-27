---
title: 게시 프로필 권장 사례
description: 이 항목에서는 게시 프로필을 구성하는 권장 방법에 대해 설명합니다.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, MainAccount, SysDatabaseLogSetup, CustGroup, VendGroup, InventItemGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 097d1c6d1fbe64dadc69cdb275a0aef38922036d
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2022
ms.locfileid: "8451483"
---
# <a name="recommended-practices-for-posting-profiles"></a>게시 프로필 권장 사례

시스템 전체에서 게시 프로필을 구성할 때 따라야 하는 몇 가지 권장 사례가 있습니다. 이 항목에서는 다양한 시나리오와 해당 권장 사례에 대해 설명합니다.

## <a name="setting-the-do-not-allow-manual-entry-flag"></a>수동 입력 허용 안 함 플래그 설정

**주 계정** 페이지에서 게시 프로필에 사용되는 주 계정에 대해 **수동 입력 허용 안 함** 확인란을 선택해야 합니다. 이 설정을 사용하면 사용자가 수동으로 주 계정에 저널 항목을 게시할 수 없습니다. 따라서, 그것은 부원장이 총계정원장과 균형을 유지하도록 보장하고 조정 과정을 더 쉽게 하는 데 도움이 됩니다.

시스템에 의해 제어되고 자동으로 게시되는 계정에 대한 조정이 필요한 경우 다음 방법 중 하나를 사용할 수 있습니다.

- 조정을 게시할 수 있는 보조 주 계정을 만듭니다. 그런 다음 재무 보고서의 총 계정 또는 특수 행을 사용하여 계정을 그룹화하고 합계를 구합니다.
- 적절한 부원장에서 원래 트랜잭션을 역순으로 수정한 다음 동일한 부원장을 통해 트랜잭션을 다시 게시합니다.

## <a name="changing-posting-profiles-after-transactions-exist"></a>트랜잭션 후 게시 프로필 변경

트랜잭션이 후 게시 프로필을 변경하면 조정이 실패하고 부장과 원장의 잔액이 부족해질 수 있습니다. 일반적으로 트랜잭션 후에는 게시 프로필을 변경하지 **않는** 것이 좋습니다.

변경이 필요한 경우 다음 지침에 따라 시스템의 무결성을 확인합니다.

- 마감 기간 동안 변경합니다.
- 시스템에서 다른 트랜잭션이 발생하지 않을 때 변경합니다.
- 변경 전후에 원장의 유효성을 검사하고 원장을 부원장으로 조정합니다.
- 게시 프로필을 변경하면 게시된 트랜잭션이 업데이트되지 않습니다. 변경에 항목 조정이 필요한지 신중하게 고려합니다.
- 재고 게시 프로필을 변경하는 경우 변경 사항이 재고 및 장부 잔액에 어떤 영향을 미칠지 고려합니다. 일부 변경 사항의 경우 재고를 0으로 설정하고 재고를 닫은 다음 변경한 후 재고를 다시 가져와야 할 수 있습니다.
- 운영 환경에서 변경 사항을 적용하기 전에 항상 비운영 환경에서 변경 사항을 테스트합니다.

## <a name="using-database-logging-to-audit-changes-to-posting-profiles"></a>데이터베이스 로깅을 사용하여 게시 프로필 변경 감사

각 게시 프로필 및 게시를 제어하는 매개 변수 테이블에 대한 데이터베이스 로깅 설정을 고려합니다. 그런 다음 매개 변수 또는 프로필이 변경된 경우 변경된 값, 변경된 사용자, 변경된 시기 및 이전 값이 무엇인지에 대한 전체 감사 레코드가 생성됩니다. 이 정보는 조정 프로세스 중에 중요할 수 있으며 감사인에게 지원 문서가 필요할 수 있습니다.

자세한 내용은 [데이터베이스 로깅 구성](../../fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log.md)을 참조하십시오.

다음 표를 게시 프로필 및 관련 게시 매개 변수와 관련된 일반 테이블 이름에 대한 참조로 사용하십시오.

| 페이지 이름 | 탐색 경로 | 테이블 이름 |
|-----------|-----------------|------------|
| 지급 계정 매개 변수 | 지급 계정 &gt; 설정 &gt; 지급 계정 매개 변수 | VendParm |
| 공급업체 게시 프로필 | 지급 계정 &gt; 설정 &gt; 공급업체 게시 프로필 | VendPosting |
| 요금 코드 | 지급 계정 &gt; 요금 설정 &gt; 요금 코드 또는 수취 계정 &gt; 요금 설정 &gt; 요금 코드 | MarkupTable |
| 결제 방법 | 지급 계정 &gt; 결제 설정 &gt; 지급 방법 | VendPaymMode |
| 현금 할인 | 지급 계정 &gt; 결제 설정 &gt; 현금 할인 또는 수취 계정 &gt; 결제 설정 &gt; 현금 할인 | CashDisc |
| 결제 수수료(공급업체) | 지급 계정 &gt; 결제 설정 &gt; 결제 수수료 | VendPaymFee |
| 수취 계정 매개 변수 | 수취 계정 &gt; 설정 &gt; 수취 계정 매개 변수 | CustParm |
| 고객 게시 프로필 | 수취 계정 &gt; 설정 &gt; 고객 게시 프로필 | CustPosting |
| 결제 방법 | 수취 계정 &gt; 결제 설정 &gt; 결제 방법 | CustPaymMode |
| 결제 수수료(고객) | 수취 계정 &gt; 결제 설정 &gt; 결제 방법 | CustPaymFee |
| 자산 임대 매개 변수 | 자산 임대 &gt; 설정 &gt; 자산 임대 매개 변수 | AssetLeasePostingAccounts<br>AssetLeaseJournalParameters<br>AssetLeaseExecutoryCostPostingAccounts |
| 은행 계정 | 현금 및 은행 관리 &gt; 은행 계정 &gt; 은행 계정 | BankAccountsTable |
| 은행 거래 유형 | 현금 및 은행 관리 &gt; 설정 &gt; 은행 트랜잭션 유형 | BankTransType |
| 소거 규칙 | 통합 &gt; 설정 &gt; 소거 규칙 | LedgerEliminationRule<br>LedgerEliminationRuleLines |
| 경비 범주 | 경비 관리 &gt; 설정 &gt; 일반 &gt; 경비 범주 | ProjCategories |
| 고정 자산 매개 변수 | 고정 자산 &gt; 설정 &gt; 고정 자산 매개 변수 | AssetParameters |
| 고정 자산 게시 프로필 | 고정 자산 &gt; 설정 &gt; 고정 자산 게시 프로필 | AssetLedgerAccounts<br>AssetDisposalParameters |
| 통화 재평가 계정 | 총계정원장 &gt; 통화 &gt; 통화 재평가 계정 | CurrencyLedgerGainLossAccount |
| 자동 트랜잭션을 위한 계정 | 총계정원장 &gt; 게시 설정 &gt; 자동 트랜잭션용 계정 | LedgerSystemAccounts |
| 회사 간 회계 | 총계정원장 &gt; 게시 설정 &gt; 회사 간 계정 | LedgerIntercompany |
| 트랜잭션 게시 정의 | 총계정원장 &gt; 게시 설정 &gt; 트랜잭션 게시 정의 | JournalizingDefinitionTrans |
| 게시 정의 | 총계정원장 &gt; 게시 설정 &gt; 게시 정의 | JournalizingDefintion |
| 게시(재고) | 재고 관리 &gt; 설정 &gt; 게시 &gt; 게시 | InventPosting |
| 비용 유형 코드 | 하역 비용 &gt; 비용 설정 &gt; 비용 유형 코드 | ITMCostTypeTable |
| 리소스 | 생산 제어 &gt; 설정 &gt; 리소스 &gt; 리소스 | WrkCtrTable |
| 리소스 그룹 | 생산 제어 &gt; 설정 &gt; 리소스 &gt; 리소스 그룹 | WrkCtrResourceGroup |
| 생산 그룹 | 생산 제어 &gt; 설정 &gt; 생산 &gt; 생산 그룹 | ProdGroup |
| 비용 범주 | 생산 제어 &gt; 설정 &gt; 경로 &gt; 비용 범주 | ProjCategory |
| 프로젝트 그룹 | 프로젝트 관리 및 회계 &gt; 설정 &gt; 게시 &gt; 프로젝트 그룹 | ProjGroup |
| 원장 게시 설정(프로젝트) | 프로젝트 관리 및 회계 &gt; 설정 &gt; 게시 &gt; 원장 게시 설정 | ProjPosting |
| 경비에 대한 기본 상쇄 계정 | 프로젝트 관리 및 회계 &gt; 설정 &gt; 게시 &gt; 경비에 대한 기본 상쇄 계정 | ProjDefaultOffsetSetup |
| 리베이트 관리 게시 프로필 | 리베이트 관리 &gt; 리베이트 관리 게시 설정 &gt; 리베이트 관리 게시 프로필 | TAMRebatePosting |
| 원장 게시 그룹(세금) | 세금 &gt; 설정 &gt; 판매세 &gt; 원장 게시 그룹 | TaxAccountGroup |

## <a name="changing-groups-after-transactions-exist"></a>트랜잭션 후 그룹 변경

마스터 데이터의 그룹을 변경할 때는 주의하십시오. 게시 프로필을 정의하기 위해 그룹을 사용하는 경우, 마스터 레코드의 그룹을 변경하면 원장과 부원장을 조정하는 기능에 부정적인 영향을 미칠 수 있습니다. 예를 들어, 각 항목 그룹에 대해 다른 수익 계정이 사용되도록 구매 주문 수익에 대한 재고 게시 프로필을 구성할 수 있습니다. 트랜잭션 후 항목에 할당된 항목 그룹을 변경하면 새 트랜잭션에 대한 수익이 업데이트된 계정에 게시됩니다. 그러나 변경 전에 게시한 수익은 원래 계정에 남아 있습니다.

## <a name="testing-posting-profiles"></a>게시 프로필 테스트

실제 환경에서 실행하기 전에 게시 프로필이나 관련 매개 변수를 변경하거나 추가한 후에는 각 시나리오를 테스트해야 합니다. 최소한 각 게시 유형을 테스트하여 게시가 올바르게 작동하는지 확인해야 합니다. 그러나 권장되는 방식은 각 게시 프로필 트랜잭션과 조합을 테스트하는 것입니다.

예를 들어, 두 개의 고객 게시 프로필이 있으며, 각 프로필에는 고객 그룹별 레코드가 세 개 있습니다. 이 경우 각 트랜잭션 유형을 테스트해야 합니다.

**게시 프로필:**

- **GEN** – 직원용 그룹, 고객용 그룹 및 회사 간 그룹을 포함하는 일반 게시 프로필입니다. 각 그룹은 다른 수취 계정 거래 계정을 가리킵니다.
- **PRE** – 고객 선불 계정을 가리키는 모든 선불에 대해 하나의 기록이 있는 선불 게시 프로필입니다.

### <a name="testing-scenarios"></a>테스트 시나리오

- **GEN** 게시 프로필을 사용하는 **직원** 그룹의 고객에 대한 자유 텍스트 송장
- **PRE** 게시 프로필을 사용하는 **직원** 그룹의 고객에 대한 자유 텍스트 송장
- **GEN** 게시 프로필을 사용하는 **직원** 그룹의 고객에 대한 판매 주문 송장
- **PRE** 게시 프로필을 사용하는 **직원** 그룹의 고객에 대한 판매 주문 송장
- **GEN** 게시 프로필을 사용하는 **직원** 그룹의 고객에 대한 고객 결제 저널
- **PRE** 게시 프로필을 사용하는 **직원** 그룹의 고객에 대한 고객 결제 저널

위의 예에서는 각 고객 그룹에 대해 하나의 테스트 시나리오를 반복하고 추가 트랜잭션 유형별로 각 테스트 시나리오 그룹(예: 프로젝트 송장 및 서비스 관리)을 반복합니다.

## <a name="reconciling-the-ledger-to-the-subledger"></a>원장을 부원장으로 조정

원장은 매 기간마다 부원장과 조정되어야 합니다. 대부분의 모듈에는 이러한 조정을 수행하는 데 사용할 수 있는 기본 제공 보고서가 포함되어 있습니다. 그러나 지역별 요구 사항에 따라 사용자 정의 보고서를 개발하거나 기존 보고서를 확장하여 보고 요구 사항에 맞춰야 할 수도 있습니다.

실제 사용을 시작하기 전에 모의 기간을 종료하고 각 부원장을 원장에 맞추는 것이 좋습니다. 또한 초기 실행 전에 모든 미결 잔액 및 미결 트랜잭션의 모의 컷오버를 수행하는 것이 좋습니다. 이 프로세스의 일부로 잔액 마이그레이션 및 열린 트랜잭션이 기존 시스템과 균형을 이루는지, 모든 부원장이 새 트랜잭션을 생성하기 전에 원장과 균형을 이루는지 확인하기 위해 완전한 조정을 실행해야 합니다.
