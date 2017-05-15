---
title: "InfoPath에 대해 리본 메뉴 사용자 지정"
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
  - "InfoPath[Visual Studio에서 Office 개발], 리본"
  - "리본[Visual Studio에서 Office 개발], InfoPath"
ms.assetid: 498c6457-679a-46f2-939f-c0597a17b7ec
caps.latest.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 18
---
# InfoPath에 대해 리본 메뉴 사용자 지정
  Microsoft Office InfoPath에서 리본을 사용자 지정할 경우 응용 프로그램에서 사용자 지정 리본이 나타나는 위치를 고려해야 합니다.[!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]에서는 다음 세 가지 유형의 InfoPath 응용 프로그램 창에서 리본을 표시할 수 있습니다.  
  
-   디자인 모드에서 열린 양식 템플릿을 표시하는 창입니다.  
  
-   양식 템플릿에 기반을 둔 양식을 표시하는 창입니다.  
  
-   인쇄 미리 보기 창입니다.  
  
 **적용 대상:** 이 항목의 정보는 InfoPath 2010의 VSTO 추가 기능 프로젝트에 적용됩니다. 자세한 내용은 [Office 응용 프로그램 및 프로젝트 형식에 따라 사용 가능한 기능](../vsto/features-available-by-office-application-and-project-type.md)을 참조하세요.  
  
 사용자와 디자이너는 디자이너 모드에서 양식 템플릿을 열고 템플릿의 모양과 레이아웃을 수정합니다. 사용자는 양식 템플릿에 기반을 둔 양식을 열고 콘텐츠를 추가합니다.  
  
 인쇄 미리 보기 창을 통해 디자이너와 사용자는 양식이나 양식 템플릿을 인쇄하기 전에 해당 페이지를 미리 볼 수 있습니다.  
  
> [!NOTE]  
>  인쇄 미리 보기 창에는 **추가 기능** 탭이 나타나지 않습니다. 인쇄 미리 보기 창에 사용자 지정 탭을 표시하려면 탭의 **OfficeId** 속성을 **TabAddIns**로 설정하지 않았는지 확인합니다.  
  
 리본을 표시할 각 창의 리본 형식을 지정해야 합니다.  
  
## 리본 디자이너에서 리본 형식 지정  
 **리본\(비주얼 디자이너\)** 항목을 사용할 경우 **속성** 창에서 리본의 **RibbonType** 속성을 클릭하고 다음 표에 설명된 리본 ID를 선택합니다.  
  
|리본 ID|프로젝트를 실행할 때 리본이 표시되는 창입니다.|  
|-----------|--------------------------------|  
|**Microsoft.InfoPath.Designer**|디자인 모드에서 열린 양식 템플릿을 표시하는 창입니다.|  
|**Microsoft.InfoPath.Editor**|양식 템플릿에 기반을 둔 양식을 표시하는 창입니다.|  
|**Microsoft.InfoPath.PrintPreview**|인쇄 미리 보기 창입니다.|  
  
 프로젝트에 리본을 두 개 이상 추가할 수 있습니다. 리본 두 개 이상이 리본 ID를 공유하면 프로젝트의 `ThisAddin` 클래스에서 런타임에 표시할 CreateRibbonExtensibilityObject 메서드를 재정의합니다. 자세한 내용은 [리본 개요](../vsto/ribbon-overview.md)을 참조하세요.  
  
## 리본 XML을 사용하여 리본 형식 지정  
 **리본\(XML\)** 항목을 사용할 경우 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> 메서드에서 *ribbonID* 매개 변수 값을 확인하고 해당하는 리본을 반환합니다.  
  
 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> 메서드는 Visual Studio를 통해 리본 코드 파일에서 자동으로 생성됩니다.*ribbonID* 매개 변수는 열려 있는 InfoPath 창의 형식을 식별하는 문자열입니다.  
  
 다음 코드 예제에서는 디자인 모드에서 양식 템플릿을 표시하는 창에만 사용자 지정 리본을 표시하는 방법을 보여 줍니다. 표시할 리본은 Ribbon 클래스에서 생성되는 `GetResourceText()` 메서드에서 지정합니다. Ribbon 클래스에 대한 자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)을 참조하세요.  
  
 [!code-csharp[Trin_RibbonInfoPathBasic#1](../snippets/csharp/VS_Snippets_OfficeSP/trin_ribboninfopathbasic/cs/ribbon.cs#1)]
 [!code-vb[Trin_RibbonInfoPathBasic#1](../snippets/visualbasic/VS_Snippets_OfficeSP/trin_ribboninfopathbasic/vb/ribbon.vb#1)]  
  
## 참고 항목  
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)   
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)  
  
  