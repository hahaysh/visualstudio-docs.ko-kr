---
title: "콘텐츠 모델 뷰 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8db7c7d-31cf-479e-9dcc-299759891795
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2991b31c387e959b055d30d37dd01cf79652adf7
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2017
---
# <a name="content-model-view"></a>콘텐츠 모델 뷰
콘텐츠 모델 뷰에서는 단순/복합 형식, 요소, 모델 그룹, 특성 및 특성 그룹을 포함하여 로컬 스키마 노드와 전역 스키마 노드는 물론 해당 구성 요소를 그래픽으로 표현할 수 있습니다. XML 주석과 처리 명령은 콘텐츠 모델 뷰에서 볼 수 없습니다. 콘텐츠 모델 뷰에 두 개의 패널:는 **작업 영역** 패널에 있는 노드의 목록을 포함 하는 [XML 스키마 디자이너 작업 영역](../xml-tools/xml-schema-designer-workspace.md), 및 스키마의 콘텐츠 모델을 볼 수 있는 디자인 화면 선택 된 노드는 **작업 영역** 패널입니다. 콘텐츠 모델 뷰에는 XML 스키마 디자이너 도구 모음과 이동 경로 탐색 막대도 들어 있습니다.  
  
 다음 이미지에서는 작업 영역 패널에 6개의 스키마 노드가 포함되어 있습니다. `purchaseOrder` 노드는 작업 영역 패널에서 선택되고 디자인 화면에 표시됩니다.  
  
 ![XML 스키마 디자이너 콘텐츠 모델 뷰](../xml-tools/media/xsddesigner_contentmodelview.gif "XSDDesigner_ContentModelView")  
  
## <a name="workspace-panel"></a>작업 영역 패널  
 작업 영역에 노드를 추가한 후에 노드 목록에 표시 됩니다는 **작업 영역** 콘텐츠 모델 뷰의 패널입니다. 노드를 선택 하는 경우는 **작업 영역** 패널, 콘텐츠 모델 뷰 디자인 화면에 나타납니다. 작업 영역에서 노드를 삭제 하려면 XSD 디자이너 도구 모음을 사용 하 여는 **작업 영역** 패널 상황에 맞는 메뉴 또는 DELETE 키입니다.  
  
 노드를 추가 하는 방법에 대 한 내용은의 "추가 노드가 작업 영역에" 섹션을 참조 하십시오. [XML 스키마 디자이너 작업 영역](../xml-tools/xml-schema-designer-workspace.md)합니다.  
  
## <a name="design-surface"></a>디자인 화면  
 작업 영역 패널에서 노드를 선택하면 노드의 세부 정보를 볼 수 콘텐츠 모델 뷰 디자인 화면에 해당 노드가 추가됩니다.  
  
 노드의 콘텐츠 모델은 트리 노드로 나타나는 요소 및 특성이 있는 확장 가능한 그래픽 트리로 표현됩니다. 기본적으로 하나의 수준만 확장됩니다. 작성자, 형식 이름, 그룹 및 기타 컨테이너와 같은 기타 정보는 이러한 정보를 포함하는 요소 및 특성과 함께 확장 가능한 세로 막대에 배치됩니다. 세로 막대를 두 번 클릭하면 가로 막대로 바뀌고 트리가 축소됩니다. 가로 막대를 두 번 클릭하면 세로 막대로 바뀌고 트리가 확장됩니다. 세로 막대를 선택하면 컨테이너의 모든 노드가 선택됩니다. 요소를 확장하거나 축소할 수 있는 경우 노드의 오른쪽에 확장기가 나타납니다.  
  
 빈 디자인 화면인 경우 XML 편집기, XML 스키마 탐색기 및 워터마크가 표시됩니다. *워터 마크* 는 모든 XSD 디자이너 뷰에 대 한 링크 목록이 나와 있습니다. 스키마 집합에 오류가 있는 경우 목록 끝에 "오류 목록을 사용하여 스키마 집합의 오류 표시 및 수정"이라는 텍스트가 표시됩니다.  
  
## <a name="breadcrumb-bar"></a>이동 경로 탐색 막대  
 콘텐츠 모델 뷰의 하단에 있는 이동 경로 탐색 막대에서는 스키마 집합에서 선택한 노드가 위치한 곳을 보여 줍니다.  
  
## <a name="context-menus"></a>상황에 맞는 메뉴  
 디자인 화면 또는 작업 영역 패널에 있는 항목을 마우스 오른쪽 단추로 클릭하면 상황에 맞는 메뉴가 나타납니다. 다음 표에서는 콘텐츠 모델 뷰 디자인 화면에 사용할 수 있는 옵션에 대해 설명합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**XML 스키마 탐색기에 표시**|스키마 탐색기에 포커스를 두고 스키마 집합 노드를 강조 표시합니다.|  
|**그래프 뷰로 표시**|그래프 뷰로 전환합니다.|  
|**샘플 XML 생성**|전역 요소에만 사용할 수 있습니다. 전역 요소를 위한 샘플 XML 파일을 생성합니다.|  
|**설명서 표시**|주석/설명서 노드 콘텐츠를 표시하거나 숨깁니다.|  
|**다이어그램을 이미지로 내보내기...**|디자인 화면을 XPS 파일에 저장합니다.|  
|**코드 보기**|XML 편집기에서 선택된 노드가 포함된 파일을 엽니다. XML 스키마 탐색기에서 선택된 항목이 XML 편집기에서도 선택됩니다.|  
|**속성 창**|열립니다는 **속성** 창 (아직 열지 않은) 하는 경우. 이 창에서 노드에 대한 정보를 표시합니다.|  
  
 다음 표에서는 작업 영역 패널에 사용할 수 있는 옵션에 대해 설명합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**XML 스키마 탐색기에 표시**|스키마 탐색기에 포커스를 두고 스키마 집합 노드를 강조 표시합니다.|  
|**그래프 뷰로 표시**|그래프 뷰로 전환합니다.|  
|**작업 영역 지우기**|작업 영역 및 디자인 화면을 지웁니다.|  
|**작업 영역에서 제거**|작업 영역 및 디자인 화면에서 선택한 노드를 제거합니다.|  
|**작업 영역에서 선택을 제외한 모든 필드 제거**|작업 영역 및 디자인 화면에서 선택하지 않은 노드를 제거합니다.|  
|**샘플 XML 생성**|전역 요소에만 사용할 수 있습니다. 전역 요소를 위한 샘플 XML 파일을 생성합니다.|  
|**모두 선택**|작업 영역 패널에서 모든 노드를 선택합니다.|  
|**코드 보기**|XML 편집기에서 선택된 노드가 포함된 파일을 엽니다. XML 스키마 탐색기에서 선택된 항목이 XML 편집기에서도 선택됩니다.|  
|**속성 창**|열립니다는 **속성** 창 (아직 열지 않은) 하는 경우. 이 창에서 노드에 대한 정보를 표시합니다.|  
  
## <a name="properties-window"></a>속성 창  
 상황에 맞는 메뉴를 사용 하 여 처음으로 엽니다는 **속성** 창. 기본적으로는 **속성** 창이 Visual Studio의 오른쪽 아래에 나타납니다. 콘텐츠 모델 뷰에 렌더링 된 노드를 클릭 하면 해당 노드의 속성이에 표시 됩니다는 **속성** 창.  
  
## <a name="xsd-designer-toolbar"></a>XSD 디자이너 도구 모음  
 콘텐츠 모델 뷰가 활성화되면 다음 XSD 디자이너 도구 모음 단추가 사용됩니다.  
  
 ![XML 스키마 디자이너 도구 모음](../xml-tools/media/xsdcontentmodelviewtoolbar.gif "XSDContentModelViewToolbar")  
  
|옵션|설명|  
|------------|-----------------|  
|**시작 뷰 표시**|전환 하는 [보기 시작](../xml-tools/start-view.md)합니다. 바로 가기 키를 사용 하 여이 뷰에 액세스할 수 있습니다: **CTRL + 1**합니다.|  
|**콘텐츠 모델 뷰 표시**|전환 하는 [콘텐츠 모델 뷰](../xml-tools/content-model-view.md)합니다. 바로 가기 키를 사용 하 여이 뷰에 액세스할 수 있습니다: **CTRL + 2**합니다.|  
|**그래프 뷰 표시**|전환 하는 [그래프 보기](../xml-tools/graph-view.md)합니다. 바로 가기 키를 사용 하 여이 뷰에 액세스할 수 있습니다: **CTRL + 3**합니다.|  
|**작업 영역 지우기**|작업 영역 및 디자인 화면을 지웁니다.|  
|**작업 영역에서 제거**|작업 영역 및 디자인 화면에서 선택한 노드를 제거합니다.|  
|**작업 영역에서 선택을 제외한 모든 필드 제거**|작업 영역 및 디자인 화면에서 선택하지 않은 노드를 제거합니다.|  
|**설명서 표시**|주석/설명서 노드 콘텐츠를 표시하거나 숨깁니다.|  
  
## <a name="panscroll"></a>이동/스크롤  
 마우스를 클릭하고 끄는 동안 스크롤 막대를 사용하거나 Ctrl 키를 눌러 디자인 화면을 이동할 수 있습니다. 클릭하여 끌기를 통해 디자인 화면을 이동할 때 커서는 네 방향을 가리키는 네 개의 교차 화살표로 변경됩니다.  
  
## <a name="undoredo"></a>실행 취소/다시 실행  
 콘텐츠 모델 뷰에서 다음 작업에 대한 실행 취소/다시 실행 기능이 사용됩니다.  
  
-   끌어서 놓기를 통해 단일 노드 추가  
  
-   스키마 탐색기에서 검색 결과 창의 여러 노드 추가  
  
-   시작 뷰에서 노드 추가  
  
-   단일 또는 여러 노드 삭제  
  
## <a name="zoom"></a>확대/축소  
 콘텐츠 모델 뷰의 오른쪽 아래 모퉁이에서 확대/축소를 사용할 수 있습니다.  
  
 확대/축소는 다음 방법으로 제어할 수 있습니다.  
  
-   마우스가 콘텐츠 모델 뷰 화면 위를 가리킬 때 Ctrl 키를 누른 채 마우스 휠 회전  
  
-   슬라이더 컨트롤 사용. 슬라이더에서는 현재 확대/축소 수준을 보여 줍니다.  
  
확대/축소 슬라이더는 해당 슬라이더를 직접 선택하거나, 해당 슬라이더에 마우스를 올려 놓거나, Ctrl 키를 마우스 휠과 함께 사용하여 확대/축소하는 경우 불투명합니다. 이외의 경우 확대/축소 슬라이더는 항상 투명합니다.  
  
## <a name="xml-editor-integration"></a>XML 편집기 통합  
 상황에 맞는 메뉴를 사용하여 XSD 디자이너와 XML 편집기 사이를 전환할 수 있습니다.  
  
 XML 편집기에서 스키마 집합을 변경하면 해당 변경 내용이 콘텐츠 모델 뷰에서 동기화됩니다. 자세한 내용은 참조 [XML 편집기와 통합](../xml-tools/integration-with-xml-editor.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 스키마 디자이너 작업 영역](../xml-tools/xml-schema-designer-workspace.md)