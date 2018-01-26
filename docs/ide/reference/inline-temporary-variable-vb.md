---
title: "Visual Basic에서 임시 변수를 해당 값으로 바꾸기 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7553a67892322a1acb2db33d7a16b399b6f0b23a
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="inline-a-temporary-variable-in-visual-basic"></a>Visual Basic에서 임시 변수 인라인

**대상:** 임시 변수를 제거하고 해당 값으로 바꿀 수 있습니다.

**시기:** 임시 변수를 사용하면 코드를 이해하기가 더 어렵습니다.

**이유:** 임시 변수를 제거하면 코드를 더 쉽게 읽을 수 있습니다.

**방법:**

1. 인라인할 임시 변수를 강조 표시하거나 임시 변수 내부에 텍스트 커서를 놓습니다.

   ![강조 표시된 코드](media/inline-highlight-vb.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거합니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭하고 **빠른 작업 및 리팩터링** 메뉴를 선택합니다.

1. [미리 보기] 창 팝업에서 **인라인 임시 변수**를 선택합니다.

   변수가 제거되고 해당 사용이 변수 값으로 즉시 대체됩니다.

   ![인라인 결과](media/inline-result-vb.png)

## <a name="see-also"></a>참고 항목

[리팩터링](../refactoring-in-visual-studio.md)