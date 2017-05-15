---
title: "방법: 책갈피 컨트롤 크기 조정"
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
  - "컨트롤[Visual Studio에서 Office 개발], 크기 조정"
  - "책갈피 컨트롤, 크기 조정"
ms.assetid: 3de1c774-921a-4113-a54a-e3b8d4a65d53
caps.latest.revision: 45
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 44
---
# 방법: 책갈피 컨트롤 크기 조정
  Microsoft Office Word 문서에 추가할 때 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤의 크기를 설정합니다. 나중에 크기를 조정할 수도 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 책갈피의 크기를 조정하는 방법은 세 가지가 있습니다.  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에서 텍스트를 추가하거나 제거합니다.  
  
     책갈피에서 텍스트를 추가할 때마다 새 텍스트를 포함하기 위해 책갈피의 크기가 자동으로 커집니다. 텍스트를 삭제하면 책갈피의 크기가 자동으로 줄어듭니다.  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤의 <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> 및 <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> 속성을 바꿉니다.  
  
     이 방법은 몇 개의 문자만으로 크기를 변경하는 경우 유용합니다.  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 다시 만듭니다.  
  
     이 방법은 책갈피의 크기 또는 위치를 대폭 변경할 경우 유용합니다.  
  
 문서 수준 프로젝트에서 디자인 타임 또는 런타임에 프로젝트의 문서에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가할 수 있습니다. VSTO 추가 기능 프로젝트에서는 런타임에 열려 있는 임의 문서에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가할 수 있습니다. 자세한 내용은 [방법: Word 문서에 책갈피 컨트롤 추가](../vsto/how-to-add-bookmark-controls-to-word-documents.md)을 참조하세요.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## Start 및 End 속성 변경  
  
#### 디자인 타임에 문서 수준 프로젝트에서 책갈피 크기를 조정하려면  
  
1.  **속성** 창에서 책갈피를 선택합니다.  
  
2.  <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> 속성 값을 늘리거나 줄입니다.  
  
3.  <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> 속성 값을 늘리거나 줄입니다.  
  
#### 런타임에 문서 수준 프로젝트에서 책갈피 크기를 조정하려면  
  
1.  런타임 또는 디자인 타임에 만든 <xref:Microsoft.Office.Tools.Word.Bookmark>의 <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> 및 <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> 속성을 수정합니다.  
  
     다음 코드 예제에서는 `SampleBookmark`라는 책갈피의 시작 부분에 다섯 개의 문자를 추가합니다. 이 코드는 책갈피 앞에 최소 다섯 개의 문자로 된 텍스트가 있다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsWord#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsWord/CS/ThisDocument.cs#2)]
     [!code-vb[Trin_VstcoreHostControlsWord#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsWord/VB/ThisDocument.vb#2)]  
  
     다음 코드 예제는 동일한 책갈피의 끝에 다섯 개의 문자를 추가합니다. 이 코드는 책갈피 다음에 최소 다섯 개의 문자로 된 텍스트가 있다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsWord#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsWord/CS/ThisDocument.cs#3)]
     [!code-vb[Trin_VstcoreHostControlsWord#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsWord/VB/ThisDocument.vb#3)]  
  
#### 런타임에 VSTO 추가 기능 프로젝트에서 책갈피 크기를 조정하려면  
  
1.  런타임에 만든 <xref:Microsoft.Office.Tools.Word.Bookmark>의 <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> 및 <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> 속성을 수정합니다.  
  
     다음 코드 예제는 활성 문서의 첫 번째 단락에 텍스트를 포함하는 <xref:Microsoft.Office.Tools.Word.Bookmark>를 만든 다음 <xref:Microsoft.Office.Tools.Word.Bookmark>의 처음과 끝에서 다섯 개의 문자를 제거합니다.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#16](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#16)]
     [!code-vb[Trin_WordAddInDynamicControls#16](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#16)]  
  
## 책갈피 다시 만들기  
 기존 책갈피와 동일한 이름을 가지고 있지만 크기가 다른 새 책갈피를 추가하여 문서 수준 프로젝트에서 책갈피 크기를 조정할 수 있습니다.  
  
#### 디자인 타임에 문서 수준 프로젝트에서 책갈피를 다시 만들려면  
  
1.  새 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에 포함될 텍스트를 선택합니다.  
  
2.  **삽입** 메뉴에서 **책갈피**를 클릭합니다.  
  
3.  **책갈피** 대화 상자에서 크기를 조정하려는 책갈피 이름을 선택하고 **추가**를 클릭합니다.  
  
## 참고 항목  
 [방법: Word 문서에 책갈피 컨트롤 추가](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [방법: NamedRange 컨트롤 크기 조정](../vsto/how-to-resize-namedrange-controls.md)   
 [방법: ListObject 컨트롤 크기 조정](../vsto/how-to-resize-listobject-controls.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  