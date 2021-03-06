---
title: WMS 지원 창고에서 위치 구성
description: 이 가이드는 새로운 WMS 지원 창고(고급 창고 관리 프로세스를 사용하는 창고)의 위치 설정을 구성하는 방법을 보여줍니다.
author: perlynne
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, WHSLocationFormat, WHSLocationType, WHSLocationProfile, WHSParameters, WHSZoneGroup, WHSZone, WHSLocationBuild, WHSLocation, WHSPackSizeCategory, WHSLocationLimit, WHSInventFixedLocation, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5273a388b30a41b75bd76c92fa4b9ff05c8f8d6
ms.sourcegitcommit: db80edbe0c32e3a5f22aae6154781f3ff8a2ab2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2021
ms.locfileid: "8449383"
---
# <a name="configure-locations-in-a-wms-enabled-warehouse"></a>WMS 지원 창고에서 위치 구성

[!include [banner](../../includes/banner.md)]

이 가이드는 새로운 WMS 지원 창고(고급 창고 관리 프로세스를 사용하는 창고)의 위치 설정을 구성하는 방법을 보여줍니다. 프로세스는 일반적으로 창고 관리자가 수행합니다. 데모 데이터 회사 USMF 또는 자체 데이터에서 이 가이드를 실행할 수 있습니다. 전제 조건은 하나 이상의 사이트가 구성되어 있다는 것입니다.


## <a name="create-a-new-warehouse"></a>새 창고 만들기
1. **탐색 창 > 모듈 > 재고 관리 > 설정 > 재고 내역 > 창고** 로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **창고** 필드에 값을 입력합니다.
4. **이름** 필드에 값을 입력합니다.
5. **사이트** 필드에서 기존 사이트 값을 선택하거나 입력합니다.
6. **창고** 섹션을 확장합니다.
7. **창고 관리 프로세스 옵션 사용** 을 예로 설정합니다. 이 설정을 사용하면 창고 작업 및 모바일 디바이스를 사용하여 고급 창고 프로세스를 실행할 수 있습니다.
8. 페이지를 닫습니다.

## <a name="define-a-location-format"></a>위치 형식 정의
1. **탐색 창 > 모듈 > 창고 관리 > 설정 > 창고 > 위치 형식** 으로 이동합니다. 위치 형식은 창고 내에서 사용되는 다양한 위치 빈 위치에 대해 고유하고 일관된 이름을 만드는 데 사용되는 명명 시스템입니다. 구분 기호를 위치 형식의 일부로 사용하면 통로 번호와 같은 위치 구성 요소를 쉽게 식별할 수 있습니다. 이 예에서는 4개의 구성 요소가 있는 이름을 만듭니다. 예를 들어 통로, 랙, 선반 및 빈이 될 수 있습니다.
2. **새로 만들기** 를 클릭합니다.
3. **위치 형식** 필드에 값을 입력합니다.
4. **이름** 필드에 값을 입력합니다.
5. **세그먼트 설명** 필드에 값을 입력합니다. 이것은 위치 이름의 첫 번째 구성 요소가 나타내는 것을 설명합니다. 예를 들어 '통로'가 될 수 있습니다.
6. **길이** 필드에 숫자를 입력합니다. 이는 위치 이름의 이 부분에 포함되어야 하는 문자 수를 결정합니다. 구분 기호를 포함하여 이름에 있는 모든 구성 요소의 합계는 10자를 초과할 수 없습니다.    
7. **구분자** 필드에 값을 입력합니다. 이것은 이름의 첫 번째 구성 요소와 두 번째 구성 요소 사이에 사용되는 문자 또는 기호를 결정합니다.  
8. **세부 정보** 섹션에서 **새로 만들기** 를 클릭합니다.
9. **세그먼트 설명** 필드에 값을 입력합니다.
10. **길이** 필드에 숫자를 입력합니다.
11. **구분자** 필드에 값을 입력합니다.
12. **세부 정보** 섹션에서 **새로 만들기** 를 클릭합니다.
13. **세그먼트 설명** 필드에 값을 입력합니다.
14. **길이** 필드에 숫자를 입력합니다.
15. **구분자** 필드에 값을 입력합니다.
16. **세부 정보** 섹션에서 **새로 만들기** 를 클릭합니다.
17. **세그먼트 설명** 필드에 값을 입력합니다.
18. **길이** 필드에 숫자를 입력합니다.
19. **저장** 을 클릭합니다.
20. 페이지를 닫습니다.

## <a name="define-location-types"></a>위치 유형 정의
1. **탐색 창 > 모듈 > 창고 관리 > 설정 > 창고 > 위치 유형** 으로 이동합니다. 위치 유형을 필터링 옵션으로 사용하여 다양한 창고 관리 프로세스를 제어할 수 있습니다. 최소한 아웃바운드 창고 관리 프로세스를 정의하려면 스테이징 및 최종 배송 위치 유형을 생성해야 합니다. 
2. **새로 만들기** 를 클릭합니다.
3. **위치** 유형 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.
5. 페이지를 닫습니다.

## <a name="define-location-profile"></a>위치 프로필 정의
1. **탐색 창 > 모듈 > 창고 관리 > 설정 > 창고 > 위치 프로필** 로 이동합니다. 위치 프로파일의 정의는 매우 중요합니다. 여기에서 그룹화된 위치 용량과 저장되는 인벤토리 및 저장 방법과 관련된 정책을 제어할 수 있습니다. 위치 프로필을 필터링 옵션으로 사용하여 다양한 창고 관리 프로세스를 제어할 수 있습니다. 최소한 창고 관리 프로세스를 사용하려면 사용자 위치 프로파일을 작성해야 합니다.
2. **새로 만들기** 를 클릭합니다.
3. **위치 프로필 ID** 필드에 값을 입력합니다.
4. **이름** 필드에 값을 입력합니다.
5. **위치 형식** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. **위치 유형** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
9. 목록에서 원하는 레코드를 찾아 선택합니다.
10. 목록에서 선택한 행의 링크를 클릭합니다.
11. **혼합 인벤토리 상태 허용** 확인란을 선택 또는 선택 취소합니다. 이 위치 프로필에 의해 그룹화될 위치에서 혼합 재고 상태 값을 허용하려면 이 옵션을 활성화합니다. 
12. **배치 일에 대한 규칙 무시** 확인란을 선택 또는 선택 취소합니다. 이 규칙을 준수하지 않는 인벤토리 배치의 혼합을 허용하기 위해 인벤토리 배치 만료 날짜가 다를 수 있는 일수에 대한 규칙을 무시하려면 이 옵션을 활성화합니다.  
13. **순환 재고 허용** 확인란을 선택 또는 선택 취소합니다. 이 위치 프로필에 의해 그룹화될 모든 위치에서 순환 재고 처리를 허용하려면 이 옵션을 활성화합니다. 
14. **차원** 섹션을 펼치거나 접습니다. 차원 탭을 사용하면 매개 변수와 방법을 정의하여 각 위치 내에서 하중 용량을 정확하게 계산할 수 있습니다.  
15. 페이지를 닫습니다.

## <a name="enable-warehouse-management-parameters"></a>창고 관리 매개 변수 사용
1. **탐색 창 > 모듈 > 창고 관리 > 설정 > 창고 관리 매개 변수** 로 이동합니다. 창고 작업을 처리할 수 있으려면 사용자 위치 프로파일에 대한 매개변수를 준비 위치 유형 및 최종 운송 위치 유형에 설정해야 합니다. 아웃바운드 프로세스가 정의한 최종 운송 위치 유형에서 종료되는 즉시 관련 아웃바운드 트랜잭션이 "선택됨"으로 업데이트됩니다.
2. **위치 프로필** 섹션을 확장합니다.
3. **사용자 위치** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. **위치 유형** 섹션을 확장합니다.
6. **스테이징 위치 유형** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. **최종 운송 위치 유형** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
9. 목록에서 선택한 행의 링크를 클릭합니다.
10. 페이지를 닫습니다.

## <a name="define-warehouse-zone-groups"></a>창고 구역 그룹 정의
1. **탐색 창 > 모듈 > 창고 관리 > 설정 > 창고 > 창고 구역 그룹** 으로 이동합니다. 창고 구역을 필터 옵션으로 사용하여 다양한 창고 관리 프로세스를 제어할 수 있습니다. 영역을 정의하려면 먼저 영역 그룹을 생성해야 합니다.   
2. **새로 만들기** 를 클릭합니다.
3. **구역 그룹 ID** 필드에 값을 입력합니다.
4. **구역 그룹 이름** 필드에 값을 입력합니다.
5. 페이지를 닫습니다.

## <a name="define-warehouse-zones"></a>창고 구역 정의
1. **탐색 창 > 모듈 > 창고 관리 > 설정 > 창고 > 구역** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **구역 ID** 필드에 값을 입력합니다.
4. **구역 이름** 필드에 값을 입력합니다.
5. **구역 그룹 ID** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. 페이지를 닫습니다.

## <a name="create-locations-using-the-location-setup-wizard"></a>위치 설정 마법사를 사용하여 위치 생성
1. **탐색 창 > 모듈 > 창고 관리 > 설정 > 창고 > 위치 설정 마법사** 로 이동합니다.
2. **창고** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
3. 목록에서 원하는 레코드를 찾아 선택합니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. **구역 ID** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. **위치 프로필 ID** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
9. 목록에서 원하는 레코드를 찾아 선택합니다.
10. 목록에서 선택한 행의 링크를 클릭합니다.
11. 목록에서 선택한 행을 표시합니다.
12. **시작 번호** 필드에 번호를 입력합니다. 시작 번호 및 끝 번호 필드는 생성될 위치의 수를 정의합니다. 예를 들어 위치 형식의 네 줄 모두에 대해 시작 번호를 1로 설정하고 끝 번호를 3으로 설정하면 81개의 위치가 생성됩니다(3x3x3x3).   
13. **끝 번호** 필드에 번호를 입력합니다.
14. 목록에서 원하는 레코드를 찾아 선택합니다.
15. **시작 번호** 필드에 번호를 입력합니다.
16. **끝 번호** 필드에 번호를 입력합니다.
17. 목록에서 원하는 레코드를 찾아 선택합니다.
18. **시작 번호** 필드에 번호를 입력합니다.
19. **끝 번호** 필드에 번호를 입력합니다.
20. 목록에서 원하는 레코드를 찾아 선택합니다.
21. **시작 번호** 필드에 번호를 입력합니다.
22. **끝 번호** 필드에 번호를 입력합니다.
23. 만들기를 클릭합니다.

## <a name="create-locations-manually"></a>수동으로 위치 생성
1. **창고 관리 > 설정 > 창고 > 위치** 로 이동합니다. 창고 내 위치를 수동으로 쉽게 생성할 수 있습니다. 위치 이름과 위치 프로필 ID는 필수 값입니다. 
2. **새로 만들기** 를 클릭합니다.
3. **창고** 필드에 값을 입력합니다.
4. **위치** 필드에 값을 입력합니다. 여기에서 새 위치를 만드는 중이므로 기존 이름을 선택하는 대신 고유한 새 이름을 입력해야 합니다.
5. **위치 프로필 ID** 필드에 값을 입력합니다.
6. 페이지를 닫습니다.

## <a name="define-pack-size-categories"></a>팩 크기 범주 정의
1. **창고 관리 > 설정 > 창고 > 팩 크기 범주** 로 이동합니다. 포장 크기 범주는 유사한 물리적 포장 크기를 가진 항목을 그룹화하는 데 사용할 수 있습니다. 이 예에서 포장 크기 범주는 창고의 특정 구역 내 피킹 위치의 용량을 제어하는 데 사용됩니다. 재고 제한 처리의 일부로 사용하려면 팩 크기 카테고리 ID를 출시된 제품 엔터티에 할당해야 합니다.  
2. **새로 만들기** 를 클릭합니다.
3. **포장 크기 범주 ID** 필드에 값을 입력합니다.
4. **포장 크기 범주 이름** 필드에 값을 입력합니다.
5. 페이지를 닫습니다.

## <a name="define-location-stocking-limits"></a>위치 재고 제한 정의
1. **창고 관리 > 설정 > 창고 > 위치 재고 제한** 으로 이동합니다. 위치 재고 제한은 재고를 운반할 물리적 용량이 없는 위치에 재고를 배치하도록 요청하는 작업이 생성되지 않도록 하는 데 도움이 됩니다.  
2. **새로 만들기** 를 클릭합니다.
3. **창고** 필드에 값을 입력합니다.
4. **위치 프로필 ID** 필드에 값을 입력합니다.
5. **포장 크기 범주 ID** 필드에 값을 입력합니다.
6. **수량** 필드에 숫자를 입력합니다.
7. **저장** 을 클릭합니다.
8. 페이지를 닫습니다.

## <a name="define-fixed-picking-locations"></a>고정 피킹 위치 정의
1. **창고 관리 > 설정 > 창고 > 고정 위치** 로 이동합니다. 제품 또는 제품 변형별로 사용할 위치를 정의할 수 있습니다. 동일한 창고 내에서 동일한 제품에 대해 여러 개의 고정 위치를 생성할 수 있습니다.     
2. **새로 만들기** 를 클릭합니다.
3. **품목 번호** 필드에 값을 입력합니다.
4. **창고** 필드에 값을 입력합니다.
5. **위치** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
