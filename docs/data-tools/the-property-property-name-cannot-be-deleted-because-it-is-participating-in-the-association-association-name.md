---
title: 속성은 연결에 참여 하 고 있으므로 삭제할 수 없습니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 98f95c489758b808ae7a210f7d83332f84571d1f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>속성 &lt;속성 이름&gt; 연결에 참여 하기 때문에 삭제할 수 없습니다 &lt;연결 이름&gt;

선택한 속성으로 설정 됩니다는 **연결 속성** 오류 메시지에 표시 된 클래스 간 연결에 대 한 합니다. 속성이 데이터 클래스 간 연결에 참여 중인 경우에는 해당 속성을 삭제할 수 없습니다.

설정의 **연결 속성** 하면 원하는 속성을 삭제할 수 데이터 클래스의 다른 속성에 있습니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. O/R 디자이너에서 오류 메시지에 표시된 데이터 클래스를 연결하는 연결 선을 선택합니다.

2. 열려는 선을 두 번 클릭은 **연결 편집기** 대화 상자.

3. 속성을 제거는 **연관 속성**합니다.

4. 속성 삭제를 다시 한 번 시도합니다.

## <a name="see-also"></a>참고자료

- [O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)
- [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)