---
title: 그래프 뷰 범례를 사용하여 Visual Studio에서 부하 테스트 분석 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Load Test Analyzer, graphs view legend
- load tests, graphs view legend
ms.assetid: 0f6ba8e4-1343-419c-8a9f-240cf50efed7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 967cc1c854689ba034077d25f61cea74d1f082a2
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="using-the-graphs-view-legend-to-analyze-load-tests"></a>그래프 뷰 범례를 사용하여 부하 테스트 분석

부하 테스트 분석기의 그래프 뷰에는 현재 선택한 그래프와 연결된 각 성능 카운터에 대한 정보가 표시되는 범례 패널이 포함되어 있습니다.

![그래프 뷰 범례](../test/media/load_viewlegend.png "Load_ViewLegend")

범례에는 다음과 같은 정보가 포함됩니다.

-   **그래프에 표시:** 이 확인란을 사용하여 **User load** 또는 **Errors/Sec**와 같은 특정 카운터에 대한 선을 그래프에 표시할지 여부를 지정합니다. 그래프에 선을 표시하려면 확인란을 선택합니다. 그래프에서 그리기 선을 제거하려면 이 확인란의 선택을 취소합니다. 그리기 선을 제거해도 해당 카운터에 대한 통계는 범례에 계속 표시됩니다.

-   **범위:** 이 열에는 성능 카운터의 Y축 범위가 표시됩니다. 기본적으로 이 값은 샘플 데이터의 범위가 변경되면 자동으로 조정됩니다. 자동으로 조정되는 범위는 항상 최대값보다 큰 10의 다음 거듭제곱입니다. 여기에는 음의 거듭제곱도 포함됩니다. 그래프에는 각각 범위가 다른 다양한 카운터를 포함할 수 있습니다. 따라서 Y축의 레이블은 특정 범위로 지정되는 것이 아니라 각 카운터의 전체 범위에 대한 백분율을 나타내는 0에서 100 사이의 값으로 지정됩니다. 예를 들어 범위가 1,000인 카운터의 경우 Y축의 데이터 요소 60은 카운터 값 600에 해당합니다.

    > [!NOTE]
    > 범위를 특정 값으로 잠가 자동 범위 값 조정을 해제할 수 있습니다. 범위를 잠그면 해당 범위를 초과하는 값은 그래프의 맨 위에 지정된 최대값으로 표시됩니다. 범위를 특정 값으로 잠그려면 **출력 옵션** 대화 상자를 사용합니다. 자세한 내용은 [방법: 그래프 카운터의 플롯 옵션 지정](../test/how-to-specify-plot-options-for-graphing-counters.md)을 참조하세요.

-   **카운터:** **카운터**, **인스턴스**, **범주** 및 **컴퓨터**라는 네 개의 열은 성능 카운터를 고유하게 식별합니다.

-   **색:** **색** 열은 성능 카운터에 대해 표시된 선의 색과 선 스타일을 표시합니다. **플롯 옵션** 대화 상자를 사용하여 그래프상의 성능 카운터 색이나 선 스타일을 변경합니다. 범례의 바로 가기 메뉴에서 **플롯 옵션** 대화 상자를 사용할 수 있습니다. 자세한 내용은 [방법: 그래프 카운터의 플롯 옵션 지정](../test/how-to-specify-plot-options-for-graphing-counters.md)을 참조하세요.

-   **통계:** **최소**, **최대**, **평균** 및 **마지막** 열에는 성능 카운터에 대한 각각의 통계가 표시됩니다. 이러한 값은 그래프의 표시 영역에 표시되는 데이터에 해당합니다. 예를 들어 특정 실행 영역을 확대한 경우 범례 통계에는 확대된 영역의 값만 반영됩니다. "마지막" 열은 가장 최근에 완료된 샘플링 간격의 성능 카운터 값입니다.

    > [!NOTE]
    > "마지막" 열은 부하 테스트를 실행하는 동안에만 부하 테스트 분석기의 범례에 표시됩니다.

     자세한 내용은 [방법: 그래프의 영역 확대](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)를 참조하세요.

범례에서 항목을 선택하면 다음 작업을 수행할 수 있습니다.

-   선택한 항목을 범례와 그래프 모두에서 제거할 수 있습니다. 항목을 마우스 오른쪽 단추로 클릭하고 **삭제**를 선택하거나 **Delete** 키를 누릅니다.

-   그래프에 표시된 선이 강조 표시됩니다.

-   데이터 표에 선택한 항목의 데이터가 표시됩니다.

-   카운터에 대한 **플롯 옵션** 대화 상자에 액세스할 수 있습니다.

> [!TIP]
> 부하 테스트 분석기의 도구 모음에서 **그래프 옵션 드롭다운** 단추를 사용하고 **범례 표시**를 선택하여 그래프 뷰와 관련된 **범례** 패널을 표시하거나 숨길 수 있습니다.

## <a name="see-also"></a>참고 항목

- [방법: 그래프 카운터에 대한 출력 옵션 지정](../test/how-to-specify-plot-options-for-graphing-counters.md)
- [방법: 그래프의 영역 확대](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)
- [그래프 뷰에서 부하 테스트 결과 분석](../test/analyze-load-test-results-in-the-graphs-view.md)