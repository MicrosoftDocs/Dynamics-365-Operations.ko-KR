---
title: Dayforce와의 통합 구성
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources와 Ceridian Dayforce 간의 통합에 필요한 필수 구성 단계에 관해 설명합니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7e2043e75aa647e21f3e0816247dcf651be64730
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452305"
---
# <a name="configure-integration-with-dayforce"></a>Dayforce와의 통합 구성


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources와 Ceridian Dayforce 간의 통합을 위해서는 이 항목에서 설명하는 몇 가지 구성 단계를 수행해야 합니다. 급여 실행을 처리하려면 먼저 Human Resources와 Dayforce에서 통합을 구성해야 합니다.

Dayforce와 같은 서비스를 사용하여 급여 실행을 완료하는 경우 Human Resources에서 통합을 활성화해야 합니다. 통합에는 Human Resources의 특정 데이터가 필요합니다. 따라서 Dayforce에 매핑된 데이터가 Human Resources에서 통합을 지원하도록 구성되어 있는지 확인해야 합니다. 통합에서는 다음과 같은 광범위한 데이터 범주를 사용합니다.

- Human Resources 데이터
- 보상 데이터
- 급여 주기, 급여 기간, 소득 코드와 같은 급여 데이터
- 근로자 데이터

이 항목에서는 통합을 활성화하기 위해 따라야 하는 단계를 설명하고 통합에 필요한 데이터 유형 및 구성 세부 정보를 설명합니다.

## <a name="enable-the-integration"></a>통합 활성화

Human Resources에서 통합을 켜고 Dayforce에 연결하기 위한 구성 정보를 입력해야 합니다. 생성된 총계정원장 트랜잭션을 Microsoft Dynamics 365 Finance로 가져오려면 Microsoft Azure Storage 계정도 설정하고 Finance에 Azure Storage 연결 문자열을 입력해야 합니다.

Human Resources에서 통합을 켜려면 다음 단계를 따릅니다.

1. **시스템 관리** 페이지에서 **통합 구성** 을 선택합니다.
2. 보안 FTP(파일 전송 프로토콜) 엔드포인트와 보안 FTP 폴더 경로를 입력합니다.
3. 보안 FTP 엔드포인트 및 폴더 경로에 액세스할 사용자의 사용자 이름과 암호를 입력합니다.
4. 필요에 따라 연결을 테스트하고 **급여 통합 활성화** 옵션을 **예** 로 설정합니다.

통합이 켜져 있으면 데이터 내보내기 패키지 및 파일이 생성되고 빈도가 설정됩니다. 필요에 따라 이 빈도를 변경할 수 있습니다.

Azure Storage 계정 및 Azure Storage 연결 문자열에 대한 자세한 내용은 다음 Azure 항목을 참조하세요.

- [Azure Storage 계정 정보](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [Azure Storage 연결 문자열 구성](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a>급여 통합이 활성화된 경우 기술 세부 정보

급여 통합을 켜면 두 가지 주요 효과가 있습니다.

- "급여 통합 내보내기"라는 데이터 내보내기 프로젝트가 생성됩니다. 이 프로젝트에는 급여 통합에 필요한 엔터티 및 필드가 포함되어 있습니다. 프로젝트를 검토하려면 **시스템 관리** 로 이동하여 **데이터 관리** 타일을 선택한 후 프로젝트 목록에서 데이터 프로젝트를 엽니다.
- 이 일괄 작업은 데이터 내보내기 프로젝트를 실행하고 결과 데이터 패키지를 암호화한 후 데이터 패키지 파일을 **통합 구성** 화면에서 구성된 SFTP 엔드포인트로 전송합니다.

> [!NOTE]
> SFTP 엔드포인트로 전송된 데이터 패키지는 패키지의 고유한 키를 사용하여 암호화됩니다. 키는 Ceridian에서만 액세스할 수 있는 Azure Key Vault에 있습니다. 데이터 패키지의 내용을 해독하고 검사할 수 없습니다. 데이터 패키지의 내용을 검토해야 하는 경우 "급여 통합 내보내기" 데이터 프로젝트를 수동으로 내보내고 다운로드한 후 열어야 합니다. 수동 내보내기는 암호화를 적용하지 않거나 패키지를 전송하지 않습니다.

## <a name="configure-your-data"></a>데이터 구성 

급여를 처리하려면 Human Resources에서 인사 데이터를 구성해야 합니다. 복리후생 및 보상 정보와 함께 직무 및 직위와 같은 조직 데이터를 설정해야 합니다. 이 정보는 직원 급여를 생성하는 데 필요한 고용, 급여 및 공제 정보를 제공합니다.

### <a name="human-resource-data"></a>인사 데이터

#### <a name="benefits"></a>복리후생 

Human Resources는 조직이 근로자를 위해 제공하거나 처리하는 혜택, 공제 및 근로자 보상 계획의 설정 및 유지 관리를 위한 도구를 제공합니다.

복리후생을 만들 때 Dayforce에서 사용되는 다음 데이터 및 구성을 염두에 두세요.

##### <a name="benefit-plans"></a>복리후생 계획

- 계획(필수)
- 유형(필수)
- 급여 영향(필수)
- 연체금 회수
- 공제 방법
- 공제 우선순위
- 한도 기간
- 한도 금액

##### <a name="benefits"></a>복리후생

- 계획(필수)
- 유형(필수)
- 옵션(필수)
- 복리후생 ID(필수)
- 빈도
- 기초
- 금액 또는 비율
- 소득 코드

##### <a name="supported-frequencies"></a>지원 빈도 

- 매주
- 격주
- 반월
- 매월

##### <a name="supported-bases"></a>지원 기반 

- 고정 금액
- 소득 백분율
- 생산 시간

Dayforce는 복리후생 제도에 정의된 급여 영향에 따라 다음 공제를 생성합니다.

| Human Resources의 선택        | Dayforce의 결과                            |
|----------------------------|-----------------------------------------------|
| 없음                       | 공제가 생성되지 않음.                      |
| 공제 전용             | 직원 공제가 생성됨.             |
| 기여도만          | 고용주 공제가 생성됨.             |
| 공제 및 기여 | 직원 및 고용주 공제가 생성됨. |

복리후생 프로그램을 정의하고 관리하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.

- [직원 복리후생 프로그램 제공](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [새로운 혜택 만들기](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [복리후생 자격 규칙 및 정책 정의](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [근로자 복리후생 등록 및 제거](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a>보상 

보상 관리는 기본급 및 포상 지급을 통제하는 데 사용됩니다. 직원의 고정 기본급 및 성과급 인상은 고정 보상 계획을 통해 통제됩니다. 보너스, 성과 포상, 스톡 옵션, 보조금 등 인센티브 지급과 일회성 포상 등은 변동 보상 계획을 통해 관리됩니다.

Dayforce는 보상 정보를 사용하여 직원의 시간당 또는 연간 급여를 계산합니다. 고정 보상 계획 및 지급 비율 환산이 필요합니다. 직원은 고정 보상 계획과 연결되어야 합니다.

보상 계획에 대한 자세한 내용은 다음 항목을 참조하세요.

- [고정 보상 계획 만들기](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [변동 보상 계획 만들기](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [급여/보상 구조 및 계획 수립](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [보상 프로세스](/dynamics365/unified-operations/talent/process-compensation)
- [보상 프로세스 정의 및 결과 계산](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [고정 보상 계획에 직원 등록](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [가변 보상 계획에 직원 등록](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a>직무 

직무는 직무를 수행하는 사람에게 필요한 업무와 책임의 집합체입니다. 자세한 내용은 다음 항목을 참조하세요.

- [직무 구성 요소 설정](/dynamics365/unified-operations/talent/create-job)
- [새 직무 정의](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a>직위

직위는 직무의 개별 인스턴스입니다. 예를 들어, "영업 관리자(동부)" 직위는 "영업 관리자" 직무와 연결된 직위 중 하나입니다. 한 직위는 한 부서에 있습니다. 각 직위에는 한 명의 근로자만 연결할 수 있습니다.

직위를 설정할 때는 다음 데이터와 구성을 고려해야 합니다.

- 직위(필수)
- 설명(필수)
- 직무(필수)
- 부서(필수)
- 직위 유형(필수)
- 정규직 상응
- 연간 정규 시간(필수)
- 법인 지급(필수)
- 급여 주기(필수)
- 기본 재무 차원 – 비용 센터(필수)
- 근로자 할당 – 근로자, 할당 시작, 할당 종료, 이유 코드

동일한 부서의 여러 직위가 동일한 직무와 연결된 경우 Dayforce의 단일 직위로 통합됩니다.

자세한 내용은 다음 항목을 참조하세요.

- [부서, 직무 및 직위를 사용하여 인력 구성](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [직위 설정](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a>부서

부서는 조직의 범주 또는 기능 영역을 나타내는 운영 단위입니다. 부서는 영업, 회계 또는 인사와 같은 조직의 특정 영역을 담당합니다. 부서를 사용하여 기능 영역에 대해 보고할 수 있습니다. 부서에는 손익 책임이 있을 수 있습니다.

자세한 내용은 다음 항목을 참조하세요.

- [부서를 만들고 부서 계층과 연결](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [새 부서 정의](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a>급여 주기 및 급여 기간

급여 주기는 급여가 실행되는 빈도와 근로자에게 지급되는 특정 날짜를 결정합니다. 예를 들어 급여 주기는 매월이고 직원은 매월 말일에 급여를 받을 수 있습니다. 또는 급여 주기가 매주일 수 있으며 직원은 급여 기간이 끝난 후 화요일에 급여를 받을 수 있습니다. 급여 주기는 해당 직위의 근로자에게 급여가 지급되는 시기를 제어하기 위해 직위에 할당됩니다.

급여 주기를 만든 후 각 주기에 대한 급여 기간을 생성할 수 있습니다. 각 지급 기간에는 사용자가 제공한 정보에 기반을 두는 기본 지급 날짜가 포함됩니다. 그러나 지급일이 공휴일인 경우와 같은 예외를 허용하도록 지급 기간의 기본 지급일을 수정할 수 있습니다.

Dayforce에는 다음 정보가 사용됩니다.

- 급여 주기(필수)
- 급여 주기 빈도(필수)
- 기간 시작 날짜(첫 지급 기간 필수)
- 기본 지급 날짜(첫 지급 기간 필수)

이 정보는 급여 그룹으로 Dayforce와 통합되며 각 급여 주기에 따라 국가 또는 지역별로 구분됩니다. 통합하기 전에 하나 이상의 지급 기간을 생성해야 합니다. Dayforce는 첫 번째 급여 기간의 시작 날짜와 Human Resources에 설정된 기본 지급 날짜를 기준으로 급여 그룹 달력과 지급 날짜를 생성합니다.

#### <a name="earning-codes"></a>소득 코드

소득 코드는 근로자가 받는 모든 유형의 소득을 고유하게 식별합니다. 코드에는 회계 규칙, 세법, 보고 요구 사항 및 총합산 기능과 같은 소득과 관련된 다양한 매개 변수가 있습니다.

Dayforce에는 다음 정보가 사용됩니다.

- 소득 코드(필수)
- 설명
- 측정 단위
- 생산

### <a name="worker-data"></a>근로자 데이터

보유한 다양한 유형의 근로자에 대한 기록은 인사 및 급여 시스템에 중요합니다. 입력한 정보는 근로자 및 개인 정보를 추적하는 데 사용될 수 있습니다.

근로자에 대한 다음 정보를 유지할 수 있습니다.

- **기본** – 연락처 정보, 인구 통계 정보, 식별 정보, 가족 정보, 병역 상태, 국외 거주자 정보, 개인 및 비상 연락처와 같은 근로자에 대한 기본 정보를 유지합니다.
- **고용** – 회사 또는 조직 소속, 직위 배정, 시작 및 종료 날짜, 근무 자격, 고용 조건, 연금, 휴가 및 재배치 정보와 같은 근로자의 고용에 대한 정보를 유지합니다.
- **휴가 및 휴무** – 근무 일정, 휴무 거래 및 부재 설정과 같은 근로자 부재에 대한 정보를 유지합니다.
- **보상 및 급여** – 계획 등록, 포상, 성과, 커미션, 세금 정보, 퇴직 및 급여 공제와 같은 근로자 보상 계획 및 급여 정보에 대한 정보를 유지합니다.

근로자 정보를 입력할 때 Dayforce에서 사용되는 다음 데이터 및 구성을 염두에 두세요.

#### <a name="general-information"></a>일반 정보

- 인사 번호(필수)
- 이름(필수)
- 성(필수)
- 중간 이름
- 선임 날짜
- 다음으로 알려짐

#### <a name="personal-information"></a>개인 정보

- 결혼 상태(필수)
- 생년월일(필수)
- 성별(필수)
- 장애인
- 국적 국가 지역(멕시코만 해당)

#### <a name="address-information"></a>주소 정보

- 기본(필수)
- 국가/지역(필수)
- 우편 번호(필수)
- 거리 번호(필수)(멕시코만 해당)
- 건물 주소(멕시코에만 해당)
- 시(필수)
- 주/도(필수)
- 구/군(필수)

#### <a name="contact-information"></a>연락처 정보 

- 기본(필수)
- 연락처 번호(필수)
- 내선 번호

#### <a name="payroll-information-and-earning-codes"></a>급여 정보 및 소득 코드

직원은 지정된 지급 빈도로 특정 수득을 할당받을 수 있고 선호하는 지급 방법을 지정할 수 있습니다. 다음 필드는 Dayforce에서 이러한 기본 설정 및 설정이 사용되도록 보장하기 위해 사용됩니다.

##### <a name="earning-codes"></a>소득 코드

- 직위(필수)
- 소득 코드(필수)
- 빈도(필수)
- 금액(필수)

##### <a name="payroll-information"></a>급여 정보

- 지급 방법
- 경제 지역(필수)
- 직원 복리후생 ID
- 주민등록번호(필수)
- 군번
- 교대 ID(필수)
- 세금 번호(필수)
- 조합 ID(필수)
- 근무일 ID(필수)
- 취업 허가 번호

> [!NOTE]
> 멕시코에서는 결제 수단으로 **현금**, **수표**(회사의 실물 수표), **전자 결제** 를 지원합니다. 결제 수단을 지정하지 않으면 기본적으로 **수표** 가 사용됩니다.

#### <a name="employment-details"></a>고용 세부 정보

고용 세부 정보 내역은 Dayforce에서 직원의 채용, 해고 및 재고용 상태를 파악하기 위한 주요 정보로 사용됩니다. Dayforce는 한 번에 하나의 활성 고용 기록만 지원합니다.

- 고용 시작 날짜(필수)
- 고용 종료 날짜
- 시작 날짜
- 조정된 시작 날짜
- 해고 날짜(해고 시 필수)
- 해고 사유(해고 시 필수)

직원의 주요 날짜는 다음 정보를 사용하여 파생됩니다.

| Human Resources                | Dayforce                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| 가장 최근 채용 날짜 | 현재 종료되지 않은 고용 기록의 고용 시작                                 |
| 종료 날짜      | 현재 종료되지 않은 고용 기록의 종료 날짜                                 |
| 시작 날짜            | 조정된 시작 날짜, 종료 날짜 또는 현재 비활성 고용 기록 레코드의 고용 시작 |
| 원래 채용 날짜    | 가장 빠른 고용 기록의 고용 시작                                               |

#### <a name="compensation"></a>보상

고정 보상 계획은 고용 기간 동안 모든 직원의 기본 직위와 연결되어야 합니다. 이 기간은 직원이 채용된 날짜(또는 고용 시작 날짜)에 시작하여 종료될 때까지 계속됩니다.

- 적용 날짜(필수)
- 만료 날짜
- 급여율(필수)
- 지급 비율 환산(필수)
- 상응 연봉(필수)
- 상응 시급(필수)

시급 직원이 여러 직위를 가지고 있는 경우 기본 직위의 고정 보상을 직원 수준의 기본 요율/급여로 Dayforce로 가져옵니다. 기본 직위가 아닌 경우 시급이 Dayforce의 해당 직위에 저장됩니다.

급여를 받는 직원이 여러 직위를 가지고 있는 경우 모든 활성 직위에 대한 누적 시급과 연봉이 도출되어 직원 수준의 기본 요율/급여로 사용됩니다.

#### <a name="identification-numbers"></a>식별 번호

##### <a name="social-security-identifier"></a>사회 보장 식별자 

모든 직원은 하나의 기본 식별자를 가져야 합니다. 이 식별자는 **SSN** 식별 유형이어야 합니다. Dayforce에서는 채용에 필요한 직원의 사회 보장 식별자로 자동으로 파생됩니다.

- 기본(필수)
- 식별 유형 = "SSN"
- 발급 날짜
- 만료 날짜

직원은 **SSN** 식별 유형의 여러 식별 번호를 선언할 수 있습니다. 그러나 번호의 활성 상태와 만료 여부와 관계없이 **기본** 으로 표시된 레코드만 Dayforce에 통합됩니다.

#### <a name="bank-accounts-and-disbursements"></a>은행 계좌 및 지급

은행 계좌 이체를 통해 급여를 받기로 선택한 직원은 유효한 은행 계좌 정보를 입력해야 합니다.

| Human Resources                         | Dayforce                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| 은행 계좌 번호(필수) |                                                                                                             |
| SWIFT 코드(필수)          | **은행 ID** 필드는 멕시코에서 급여를 처리할 때 사용됩니다.                                                             |
| 지점 번호(필수)       |                                                                                                             |
| 은행 계좌 유형(필수)   | **계좌 유형** 필드는 멕시코에서 급여를 처리할 때 사용됩니다. 지원되는 값에는 **당좌 예금** 및 **급여** 가 있습니다. |

> [!NOTE]
> 은행 계좌 이체를 통해 급여를 받기로 선택한 직원은 기본 주소가 멕시코이고 멕시코 은행의 유효한 은행 계좌와 연결된 법인의 나머지 계좌에 대한 연결을 제공해야 합니다. 나머지 계정이 아닌 다른 모든 계정은 무시됩니다.

#### <a name="address-information"></a>주소 정보

모든 직원은 하나의 기본 위치를 가져야 합니다. Dayforce에서 이 위치는 세금 목적으로 직원의 기본 거주지를 결정하는 데 사용됩니다.

- 기본(필수)
- 국가/지역(필수)
- 우편 번호(필수)
- 거리(필수)
- 거리 번호(필수)
- 건물 주소
- 시(필수)
- 주/도(필수)
- 구/군(필수)

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a>미국 및 캐나다에서 급여를 생성하도록 데이터 구성

미국 및 캐나다에서 직원의 급여를 생성하는 경우 다음 요소를 구성해야 합니다.

- 직위에는 부서가 필요합니다.
- 비용 센터는 재무 차원으로 설정되어야 하며 기본 재무 차원 문자열의 첫 번째 요소여야 합니다.

> [!NOTE] 
> 직위가 부서를 지정하도록 Human Resources를 구성할 수 있습니다. 이를 위해서는 **Human Resources 공유 직위 > 직위 > 직위에 부서 필요** 로 이동합니다. 통합을 위해 이 설정을 적용하는 것이 좋습니다.

### <a name="job-types"></a>직무 유형

작업 유형은 유사한 직무를 범주로 그룹화하는 데 사용됩니다. 미국과 캐나다에서 급여를 처리하려면 직무 유형이 필요합니다. 직무 유형의 예로는 정규직 및 시간제 또는 급여 및 시급이 있습니다. 직무 유형은 직원이 시급인지 급여인지를 나타내는 급여 유형으로 Dayforce에 매핑됩니다.

다음 직무 유형 및 설명이 필요합니다.

| 작업 유형   | 설명 |
|------------|-------------|
| 매시간     | 매시간      |
| 급여   | 급여    |

### <a name="position-types"></a>직위 유형 

직위 유형을 사용하여 직위가 정규직, 시간제 또는 기타인지 설명합니다. 직위 유형은 직원이 정규직인지 또는 시간제인지 나타내는 지급 클래스로 Dayforce에 매핑됩니다.

다음 직위 유형 및 설명이 필요합니다.

| 직책 유형   | 설명        |
|-----------------|--------------------|
| 정규직       | 정규직 직원 |
| 비정규직       | 비정규직 직원 |

### <a name="reason-codes"></a>사유 코드

사유 코드는 직원의 상태에 대한 정보를 제공합니다. 사유 코드는 직원의 직위 또는 고용 상태의 변경 이유를 나타내는 상태 이유로 Dayforce에 매핑됩니다.

다음 사유 코드 및 설명이 필요합니다.

| 사유 코드    | 설명      | 적용 가능한 시나리오 |
|----------------|------------------|----------------------|
| 사직    | 사직      | 근로자 해고     |
| 해고    | 해고      | 근로자 해고     |
| 퇴직     | 퇴직       | 근로자 해고     |
| 기타          | 기타 이유    | 근로자 해고     |
| 사망          | 사망            | 근로자 해고     |
| 휴직 | 휴직 | 근로자 해고     |
| 계약 종료    | 계약 종료  | 근로자 해고     |
| 급여 변경   | 급여 변경 | 보상         |

### <a name="marital-status"></a>결혼 상태

결혼 상태 값은 Dayforce에 매핑되고 통합 시 허용되는 값으로 적절하게 변환됩니다.

다음 표는 결혼 상태 값이 Dayforce에 매핑되는 방법을 보여줍니다.

| Human Resources                 | Dayforce             |
|------------------------|----------------------|
| 결혼                | 결혼              |
| 미혼                 | 미혼               |
| 사별                | 사별              |
| 이혼               | 이혼             |
| 등록된 동반자 관계 | 가정 동반자 |
| 없음                   | 없음                 |
| 동거             | 동거           |

### <a name="gender"></a>성별

성별 지정은 Dayforce에 매핑되고 통합 시 허용되는 값으로 적절하게 변환됩니다.

다음 표는 성별 지정이 Dayforce에 매핑되는 방법을 보여줍니다.

| Human Resources       | Dayforce        |
|--------------|-----------------|
| 남성         | 남성            |
| 여성       | 여성          |
| 미정 | *아직 지원되지 않음* |

### <a name="earning-codes"></a>소득 코드

소득 코드는 근로자가 받는 모든 유형의 소득을 고유하게 식별합니다. 코드는 회계 규칙, 세법, 보고 요구 사항 및 총합산 기능과 같은 소득과 관련된 여러 매개 변수를 처리합니다. 지원되지 않는 빈도를 사용하는 경우 기본적으로 **모든 지급** 빈도가 계산에 사용됩니다.

#### <a name="supported-frequencies"></a>지원 빈도

- 모두
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>주소

특정 국가 또는 지역, 주/도 및 구/군(자치당국) 코드를 식별하려면 Dayforce 및 국내/지역 제공업체가 인식할 수 있는 특정 형식이 필요합니다. 도시 형식은 유연하지만 모든 도시는 주/도와 연결되어야 합니다.

| Human Resources          | Dayforce              |
|-----------------|-----------------------|
| 국가/지역  | 국가 코드          |
| 우편 번호 | 우편 번호           |
| 상태           | 주/도 코드            |
| 시            | 시                  |
| 군/구          | 구/군(자치당국) |
| 주소          | 주소란 1        |

### <a name="tax-regions"></a>과세 지역

과세 지역은 급여 생성 중에 적용해야 하는 적절한 세금을 결정하는 데 사용됩니다. 과세 지역은 위치 주소로 Dayforce에 매핑됩니다. 기본 과세 지역은 근로자의 활성 직위와 연결되어야 합니다. 

- 과세 지역(필수)
- 국가/지역(필수)
- 주/도(필수)
- 군/구 
- 시(필수)

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a>멕시코에서 급여를 생성하도록 데이터 구성

멕시코에서 직원의 급여를 생성하는 경우 다음 요소를 구성해야 합니다.

- 직위에는 부서가 필요합니다.
- 비용 센터는 재무 차원으로 설정되어야 하며 기본 재무 차원 문자열의 첫 번째 요소여야 합니다.

### <a name="job-types"></a>직무 유형

작업 유형은 유사한 직무를 범주로 그룹화하는 데 사용됩니다. 멕시코에서 급여를 처리하려면 직무 유형이 필요합니다. 직무 유형의 예로는 정규직 및 시간제 또는 급여 및 시급이 있습니다. 직무 유형은 직원이 시급인지 급여인지를 나타내는 급여 유형으로 Dayforce에 매핑됩니다.

다음 직무 유형 및 설명이 필요합니다.

| 직무 유형   | 설명 |
|------------|-------------|
| 매시간     | MX 매시간   |
| 급여   | MX 급여 |

### <a name="position-types"></a>직위 유형 

직위 유형을 사용하여 직위가 정규직, 시간제 또는 기타인지 설명합니다. 직위 유형은 직원이 정규직인지 또는 시간제인지 나타내는 지급 클래스로 Dayforce에 매핑됩니다.

다음 직위 유형 및 설명이 필요합니다.

| 직책 유형   | 설명        |
|-----------------|--------------------|
| 정규직       | 정규직 직원 |
| 비정규직       | 비정규직 직원 |

### <a name="reason-codes"></a>사유 코드

사유 코드는 직원의 상태에 대한 정보를 제공합니다. 사유 코드는 직원의 직위 또는 고용 상태의 변경 이유를 나타내는 상태 이유로 Dayforce에 매핑됩니다.

다음 사유 코드 및 설명이 필요합니다.

| 사유 코드            | 설명                    | 적용 가능한 시나리오 |
|------------------------|--------------------------------|----------------------|
| 지급 전 퇴사 | 첫 급여 지급 전 퇴사 | 근로자 해고     |
| 사직            | 사직                    | 근로자 해고     |
| 연금                | 연금                        | 근로자 해고     |
| 해고            | 해고                    | 근로자 해고     |
| 퇴직             | 퇴직                     | 근로자 해고     |
| 부재자               | 부재자                       | 근로자 해고     |
| 기타                  | 기타 이유                  | 근로자 해고     |
| 폐쇄                | 폐업               | 근로자 해고     |
| 사망                  | 사망                          | 근로자 해고     |
| 휴직         | 휴직               | 근로자 해고     |
| 계약 종료            | 계약 종료                | 근로자 해고     |
| 급여 변경           | 급여 변경               | 보상         |

### <a name="terms-of-employment"></a>채용 조건

채용 조건은 채용 조건 범주를 만드는 데 사용됩니다. 조건은 고용 지표 값으로 Dayforce에 매핑됩니다.

다음 채용 조건 및 설명이 필요합니다.

| 채용 조건   | 설명 |
|-----------------------|-------------|
| 정기               | 정기     |
| 직접                | 직접      |
| 인턴쉽            | 인턴쉽  |
| 영구             | 영구   |

### <a name="marital-status"></a>결혼 상태

결혼 상태 값은 Dayforce에 매핑되고 통합 시 허용되는 값으로 적절하게 변환됩니다.

다음 표는 결혼 상태 값이 Dayforce에 매핑되는 방법을 보여줍니다.

| Human Resources                 | Dayforce                  |
|------------------------|---------------------------|
| 결혼                | 결혼                   |
| 미혼                 | 미혼                    |
| 사별                | 사별                   |
| 이혼               | 이혼                  |
| 등록된 동반자 관계 | 가정 동반자      |
| 없음                   | *멕시코에서 지원되지 않음* |
| 동거             | *멕시코에서 지원되지 않음* |

### <a name="gender"></a>성별

성별 지정은 Dayforce에 매핑되고 통합 시 허용되는 값으로 적절하게 변환됩니다.

다음 표는 성별 지정이 Dayforce에 매핑되는 방법을 보여줍니다.

| Human Resources       | Dayforce                  |
|--------------|---------------------------|
| 남성         | 남성                      |
| 여성       | 여성                    |
| 미정 | *멕시코에서 지원되지 않음* |

### <a name="payment-method"></a>지급 방법

지급 방법은 직원과 회사에 직원이 지급받는 방식을 설명하는 방법을 제공합니다. 지급 방법은 Dayforce에 매핑되고 통합 시 허용되는 값으로 적절하게 변환됩니다.

다음 표는 지급 방법이 Dayforce에 매핑되는 방법을 보여줍니다.

| Human Resources             | Dayforce                  |
|--------------------|---------------------------|
| 현금               | 현금                      |
| 전자 지급 | 이체                  |
| 수표              | 수표                    |
| 은행 어음         | *멕시코에서 지원되지 않음* |
| 기타              | *멕시코에서 지원되지 않음* |

### <a name="bank-account-type"></a>은행 계좌 유형

은행 계좌 유형은 직원에 대한 전자 지급에 사용됩니다. 은행 계좌 유형은 이체 계좌 정보로 Dayforce에 매핑됩니다. 은행 계좌 유형은 통합 시 허용되는 값으로 적절하게 변환됩니다.

| Human Resources            | Dayforce                  |
|-------------------|---------------------------|
| 당좌 예금 계좌  | 당좌 예금 계좌           |
| 급여 계좌   | 급여 계좌            |
| 예금 계좌   | *멕시코에서 지원되지 않음* |
| BankGirot 계좌 | *멕시코에서 지원되지 않음* |
| PlusGirot 계좌 | *멕시코에서 지원되지 않음* |

### <a name="earning-codes"></a>소득 코드

소득 코드는 근로자가 받는 모든 유형의 소득을 고유하게 식별합니다. 코드는 회계 규칙, 세법, 보고 요구 사항 및 총합산 기능과 같은 소득과 관련된 여러 매개 변수를 처리합니다. 지원되지 않는 빈도를 사용하는 경우 기본적으로 **모든 지급** 빈도가 계산에 사용됩니다.

#### <a name="supported-frequencies"></a>지원 빈도

- 모두
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>주소

특정 국가 또는 지역, 주/도 및 구/군(자치당국) 코드를 식별하려면 Dayforce 및 국내/지역 제공업체가 인식할 수 있는 특정 형식이 필요합니다. 도시 형식은 유연하지만 모든 도시는 주/도와 연결되어야 합니다.

| Human Resources              | Dayforce              |
|---------------------|-----------------------|
| 국가/지역      | 국가 코드          |
| 우편 번호     | 우편 번호           |
| 상태               | 주/도 코드            |
| 시                | 시                  |
| 군/구              | 구/군(자치당국) |
| 주소              | 주소란 1        |
| 거리 번호       | 주소란 2        |
| 건물 주소 | 주소란 5        |

### <a name="passport-number"></a>여권 번호

직원은 여권 정보를 신고할 수 있습니다. 이 정보는 **여권** 식별 유형이며 직원의 멕시코 관련 정보의 일부로 Dayforce에 통합됩니다.

- 식별 유형 = "여권"
- 발급 날짜
- 만료 날짜

직원은 **여권** 식별 유형의 여러 식별 번호를 선언할 수 있습니다. 그러나 현재 활성 여권 항목만 Dayforce에 통합됩니다. 모든 여권 항목이 만료된 경우 가장 최근에 발급된 여권이 Dayforce에 통합됩니다.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
