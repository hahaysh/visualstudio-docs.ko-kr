---
title: '연습: XSLT 프로파일러'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 87387c9a-2e89-4801-ad51-83740cd6ea25
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c36b1e079027bd0513a7396e703db610dd737639
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-xslt-profiler"></a>연습: XSLT 프로파일러

XSLT 프로파일러는 XSLT 코드의 성능 관련 문제를 측정 및 평가하고, 대상으로 지정하는 데 도움이 되는 자세한 XSLT 성능 보고서를 만듭니다. XSLT 프로파일러에는 XSL 및 XSLT 스타일시트 최적화에 유용한 힌트도 포함되어 있습니다. 최대 성능이 필요한 XSLT 응용 프로그램의 경우 이 도구가 반드시 필요합니다.

## <a name="prerequisites"></a>전제 조건

다음 연습에서는의 절차는 Visual Studio 및.NET Framework 버전 4.0 이상 필요 합니다.

### <a name="create-the-performance-report"></a>성능 보고서 만들기

1.  Visual Studio에서 XSLT 문서를 엽니다.

2.  클릭는 **XSLT 프로 파일링** XML 메뉴에서 사용할 수 있는 옵션입니다.

3.  입력 XML 문서를 제공합니다. XML 문서가 아직 열려 있지 않으면 파일을 확인하는 메시지가 표시됩니다.

4.  분석이 시작되고 진행률 표시줄에서 편집기 내의 진행률을 표시합니다.

5.  XSLT 출력이 출력 창에 표시됩니다.

6.  성능 세션이 끝나면 성능 보고서를 확인합니다. 성능 보고서에 저장된 데이터를 통해 XSLT 성능을 확인하고 분석할 수 있습니다.

### <a name="get-all-the-available-views"></a>사용 가능한 모든 뷰 가져오기

1.  클릭는 **현재 보기** 드롭다운 목록에서 사용 가능한 모든 뷰를 가져옵니다.

2.  선택의 **요약 보기** 옵션에 **현재 보기** 드롭 다운 목록입니다. 기본적으로 성능 보고서에 표시 됩니다는 **요약 보기**합니다. XSLT 문서를 사용하여 성능 문제를 확인할 때는 이 뷰를 먼저 검토합니다. **요약 보기** 다음 데이터 요소를 나열 합니다.

    -   가장 많이 호출된 함수

    -   개별 작업이 가장 많은 함수

    -   가장 많은 실행 시간이 소요되는 함수

3.  기본적으로 각 데이터 요소에 대한 세 개의 열인 함수 이름, 절대값의 호출 수 및 총 함수 호출에 대한 이름 지정 함수의 백분율 값이 있습니다. 각 데이터 요소에서는 **요약 보기**, 함수 데이터 요소를 마우스 오른쪽 단추로 클릭 하 여 더 자세한 뷰로 탐색할 수 있습니다.

4.  선택 된 **함수 뷰** 옵션에 **현재 보기** 드롭 다운 목록. **함수 뷰** 프로 파일링 중 호출 된 함수를 나열 합니다. 열 이름을 클릭하면 데이터를 정렬할 수 있습니다. 기본적으로 다음 열이 표시됩니다.

    -   **함수 이름**

    -   **경과된 포괄 시간**

    -   **경과된 전용 시간**

    -   **응용 프로그램 포괄 시간**

    -   **응용 프로그램 전용 시간**

    -   **호출 수**

5.  모든 시간 열이 절대값과 백분율로 모두 표시됩니다. 용어 **단독** 한 함수가이 함수를 실행 하는 동안 호출 된 다른 함수에서 소요 된 시간을 제외한 실행에 소요 된 총 시간을 나타냅니다.

6.  용어 **Inclusive** 호출 하 고 다른 함수를 호출 했는지 여부가 이러한 함수를 호출 함수의 모든 함수의 실행 시간을 포함 하 여 실행에 소요 된 총 시간을 나타냅니다.

### <a name="select-callercallee-view"></a>호출자/호출 수신자 뷰 선택

1.  선택 **호출자/호출 수신자** 뷰에서 **현재 보기** 드롭 다운 목록입니다.

2.  **호출자/호출 수신자** 보기에는 다음 세 개의 개별 부분에:

    -   **함수를 호출한 함수**: 특정 함수를 호출한 모든 함수가 뷰의 위쪽 부분에 나열 됩니다.

    -   **현재 함수**: 호출 된 특정 함수가 뷰의 가운데 부분에 나열 됩니다.

    -   **에 의해 호출 된 함수** : 특정 함수가 호출한 모든 함수가 뷰의 아래쪽 부분에 나열 됩니다.

3.  이름이 `SyncToNavigator`인 함수가 뷰의 가운데에 나타나는 경우 `SyncToNavigator` 함수를 호출한 모든 함수가 뷰의 위쪽에 나타나고 `SyncToNavigator`에 의해 호출된 모든 함수가 뷰의 아래쪽에 나타납니다.

4.  뷰의 다른 두 부분에 나열된 함수를 두 번 클릭하여 뷰의 가운데에 있는 함수를 변경할 수 있습니다. 그러면 변경 내용을 자동으로 반영하도록 뷰가 업데이트됩니다.

5.  열 이름을 클릭하면 데이터를 정렬할 수도 있습니다.

### <a name="select-calltree-view"></a>호출 트리 뷰 선택

1.  선택 **호출 트리 뷰** 에 **현재 보기** 드롭 다운 목록입니다. 이 뷰는 프로그램 실행의 트리 뷰입니다.

2.  **호출 트리 뷰** 프로세스 이름으로 트리의 루트를 보여 줍니다. 함수는 트리 노드입니다. 이 뷰를 통해 특정 호출 추적으로 드릴인투하고 성능에 미치는 영향이 가장 큰 추적을 분석할 수 있습니다. 보기는 비슷합니다는 **호출 스택 뷰** 디버깅 하는 동안 사용할 수 있습니다. 열 외에도 **함수 뷰**에 **호출 트리 뷰**를 표시 하는 추가 열이는 **모듈 이름**합니다.

3.  선택 **표시** 에 **현재 보기** 드롭 다운 목록입니다.

4.  XSLT 프로파일러에는 연결된 주석이 포함된 데이터 컬렉션 스트림에 나타나는 표시가 있습니다. 표시는 코드에서 카운터가 있는 위치입니다. XSLT 프로파일러에서 XSLT 성능 카운터를 수집하도록 지정하면 이러한 표시 중 하나가 실행될 때마다 카운터가 수집됩니다. 데이터가 포함 된 테이블에 표시 됩니다는 **표시 ID**, **표시 이름과** (**시작 프로그램**, **종료 프로그램**), 및  **타임 스탬프**합니다. 있는 기호는 집계 되지 않습니다 및에서 시간 순서에 표시는 **View** 성능 보고서입니다.

### <a name="select-modules-in-the-current-view"></a>현재 뷰에서 모듈 선택

1.  선택 **모듈** 에 **현재 보기** 드롭 다운 목록입니다.

2.  모듈 뷰는 모듈 수준으로 집계된 모든 함수의 단순 목록입니다. 모듈 성능 데이터의 뷰를 표시하거나 닫으려면 모듈 이름을 확장하거나 축소합니다. 열 이름을 클릭하면 데이터를 정렬할 수 있습니다. 기본적으로 없는 절대값과 백분율 수가 대 한 **경과 된 포괄 시간**, **경과 된 전용 시간**, **응용 프로그램 포괄 시간**, **응용 프로그램 전용 시간**, 및 **호출 수가**합니다.

3.  선택 **프로세스** 에 **현재 보기** 드롭 다운 목록입니다.

4.  프로세스 보기를 포함 하는 테이블 표시는 **프로세스 ID**, **프로세스 이름**, **시작 시간**, 및 **종료 시간**합니다. 열 이름을 클릭하면 데이터를 정렬할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [연습: XSLT 계층 구조 사용](../xml-tools/walkthrough-using-xslt-hierarchy.md)