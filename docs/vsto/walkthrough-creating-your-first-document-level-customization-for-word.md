---
title: "연습: Word용 첫 문서 수준 사용자 지정 만들기"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "문서 수준 사용자 지정[Visual Studio에서 Office 개발], 프로젝트 처음 만들기"
  - "Visual Studio에서 Office 개발, 프로젝트 처음 만들기"
  - "Word[Visual Studio에서 Office 개발], 프로젝트 처음 만들기"
ms.assetid: ec9f5173-0923-4aee-985a-e760e80eaae3
caps.latest.revision: 45
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 44
---
# 연습: Word용 첫 문서 수준 사용자 지정 만들기
  이 소개용 연습에서는 Microsoft Office Word에 대한 문서 수준 사용자 지정을 만드는 방법을 보여 줍니다.  이러한 종류의 솔루션에서 만드는 기능은 특정 문서가 열려 있는 경우에만 사용할 수 있습니다.  문서가 열려 있을 때 새 리본 탭 표시와 같은 응용 프로그램 수준 변경은 문서 수준 사용자 지정을 사용하여 수행할 수 없습니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   Word 문서 프로젝트 만들기  
  
-   Visual Studio 디자이너에 호스트된 문서에 텍스트 추가  
  
-   Word의 개체 모델을 사용하여 사용자 지정 문서가 열릴 때 문서에 텍스트를 추가하는 코드 작성  
  
-   프로젝트를 빌드 및 실행하여 테스트  
  
-   프로젝트를 정리하여 개발 컴퓨터에서 불필요한 빌드 파일 및 보안 설정 제거  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## 프로젝트 만들기  
  
#### Visual Studio에서 새 Word 문서 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  템플릿 창에서 **Visual C\#** 또는 **Visual Basic**을 확장한 다음 **Office\/SharePoint**를 확장합니다.  
  
4.  확장된 **Office\/SharePoint** 노드 아래에서 **Office 추가 기능** 노드를 선택합니다.  
  
5.  프로젝트 템플릿 목록에서 Word VSTO 문서 프로젝트를 선택합니다.  
  
6.  **이름** 상자에 **FirstDocumentCustomization**을 입력합니다.  
  
7.  **확인**을 클릭합니다.  
  
     **Visual Studio Tools for Office 프로젝트 마법사**가 열립니다.  
  
8.  **새 문서 만들기**를 선택하고 **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 **FirstDocumentCustomization** 프로젝트를 만들고 **FirstDocumentCustomization** 문서와 ThisDocument 코드 파일을 프로젝트에 추가합니다.  디자이너에서 **FirstDocumentCustomization** 문서가 자동으로 열립니다.  
  
## 디자이너에서 문서를 닫은 후 다시 열기  
 프로젝트를 개발하는 동안 디자이너에서 의도적으로 또는 실수로 문서를 닫은 경우 다시 열 수 있습니다.  
  
#### 디자이너에서 문서를 닫은 후 다시 열려면  
  
1.  디자이너 창의 **닫기** 단추\(X\)를 클릭하여 문서를 닫습니다.  
  
2.  **솔루션 탐색기**에서 **ThisDocument** 코드 파일을 마우스 오른쪽 단추로 클릭하고 **뷰 디자이너**를 클릭합니다.  
  
     또는  
  
     **솔루션 탐색기**에서 **ThisDocument** 코드 파일을 두 번 클릭합니다.  
  
## 디자이너에서 문서에 텍스트 추가  
 디자이너에서 열려 있는 문서를 수정하여 사용자 지정의 UI\(사용자 인터페이스\)를 디자인할 수 있습니다.  예를 들어 텍스트, 테이블 또는 Word 컨트롤을 추가할 수 있습니다.  디자이너를 사용하는 방법에 대한 자세한 내용은 [Visual Studio 환경의 Office 프로젝트](../vsto/office-projects-in-the-visual-studio-environment.md)를 참조하세요.  
  
#### 디자이너를 사용하여 문서에 텍스트를 추가하려면  
  
1.  디자이너에 열려 있는 문서에서 다음 텍스트를 입력합니다.  
  
     **This text was added by using the designer.**  
  
## 프로그래밍 방식으로 문서에 텍스트 추가  
 다음 작업으로, ThisDocument 코드 파일에 코드를 추가합니다.  새 코드는 Word의 개체 모델을 사용하여 문서에 두 번째 텍스트 단락을 추가합니다.  기본적으로 ThisDocument 코드 파일에는 다음과 같은 생성된 코드가 포함되어 있습니다.  
  
-   문서의 프로그래밍 모델을 나타내고 Word의 개체 모델에 대한 액세스를 제공하는 `ThisDocument` 클래스의 부분 정의입니다.  자세한 내용은 [문서 호스트 항목](../vsto/document-host-item.md) 및 [Word 개체 모델 개요](../vsto/word-object-model-overview.md)를 참조하세요.  `ThisDocument` 클래스의 나머지 부분은 수정해서는 안 되는 숨김 코드 파일에서 정의됩니다.  
  
-   `ThisDocument_Startup` 및 `ThisDocument_Shutdown` 이벤트 처리기.  이러한 이벤트 처리기는 문서를 열고 닫을 때 호출됩니다.  이러한 이벤트 처리기를 사용하여 문서가 열릴 때 사용자 지정을 초기화하고 문서가 닫힐 때 사용자 지정에서 사용하는 리소스를 정리할 수 있습니다.  자세한 내용은 [Office 프로젝트의 이벤트](../vsto/events-in-office-projects.md)를 참조하세요.  
  
#### 코드를 사용하여 문서에 두 번째 텍스트 단락을 추가하려면  
  
1.  **솔루션 탐색기**에서 **ThisDocument**를 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  
  
     Visual Studio에서 코드 파일이 열립니다.  
  
2.  `ThisDocument_Startup` 이벤트 처리기를 다음 코드로 바꿉니다.  문서가 열리면 이 코드에서 두 번째 텍스트 단락을 문서에 추가합니다.  
  
     [!code-csharp[Trin_WordDocumentTutorial#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordDocumentTutorial/CS/ThisDocument.cs#1)]
     [!code-vb[Trin_WordDocumentTutorial#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordDocumentTutorial/VB/ThisDocument.vb#1)]  
  
    > [!NOTE]  
    >  이 코드는 인덱스 값 1을 사용하여 <xref:Microsoft.Office.Tools.Word.Document.Paragraphs%2A> 속성의 첫 번째 단락에 액세스합니다.  Visual Basic 및 Visual C\#은 0부터 시작하는 배열을 사용하지만 Word 개체 모델에서 대다수 컬렉션의 배열 하한은 1입니다.  자세한 내용은 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)을 참조하세요.  
  
## 프로젝트 테스트  
  
#### 문서를 테스트하려면  
  
1.  **F5** 키를 눌러 프로젝트를 빌드하고 실행합니다.  
  
     프로젝트를 빌드하면 코드가 문서와 연결된 어셈블리로 컴파일됩니다.  Visual Studio는 프로젝트에 대한 빌드 출력 폴더에 문서와 어셈블리의 복사본을 넣고 사용자 지정을 실행할 수 있도록 개발 컴퓨터의 보안 설정을 구성합니다.  자세한 내용은 [Office 솔루션 빌드](../vsto/building-office-solutions.md)를 참조하세요.  
  
2.  문서에서 다음 텍스트가 표시되는지 확인합니다.  
  
     **This text was added by using the designer.**  
  
     **This text was added by using code.**  
  
3.  문서를 닫습니다.  
  
## 프로젝트 정리  
 프로젝트 개발을 완료하면 빌드 출력 폴더의 파일 및 빌드 프로세스에서 생성된 보안 설정을 제거해야 합니다.  
  
#### 개발 컴퓨터에서 완료된 프로젝트를 정리하려면  
  
1.  Visual Studio의 **빌드** 메뉴에서 **솔루션 정리**를 클릭합니다.  
  
## 다음 단계  
 기본적인 Word용 문서 수준 사용자 지정을 만들었으므로 다음 항목에서 사용자 지정을 개발하는 방법에 대해 자세히 알아볼 수 있습니다.  
  
-   문서 수준 사용자 지정에서 수행할 수 있는 일반적인 프로그래밍 작업: [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md).  
  
-   Word용 문서 수준 사용자 지정과 관련된 프로그래밍 작업: [Word 솔루션](../vsto/word-solutions.md).  
  
-   Word의 개체 모델 사용: [Word 개체 모델 개요](../vsto/word-object-model-overview.md).  
  
-   Word의 UI 사용자 지정\(예: 리본에 사용자 지정 탭 추가 또는 사용자 고유의 작업 창 만들기\): [Office UI 사용자 지정](../vsto/office-ui-customization.md).  
  
-   Visual Studio의 Office 솔루션에서 제공하는 확장된 Word 개체를 사용하여 Word 개체 모델을 통해 수행할 수 없는 작업\(예: 문서에서 관리되는 컨트롤 호스트 및 Windows Forms 데이터 바인딩 모델을 사용하여 데이터에 Word 컨트롤 바인딩\) 수행: [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md).  
  
-   Word용 문서 수준 사용자 지정 빌드 및 디버그: [Office 솔루션 빌드](../vsto/building-office-solutions.md).  
  
-   Word용 문서 수준 사용자 지정 배포: [Office 솔루션 배포](../vsto/deploying-an-office-solution.md).  
  
## 참고 항목  
 [Office 솔루션 개발 개요&#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Word 솔루션](../vsto/word-solutions.md)   
 [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)   
 [Word 개체 모델 개요](../vsto/word-object-model-overview.md)   
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [Office 솔루션 빌드](../vsto/building-office-solutions.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)  
  
  