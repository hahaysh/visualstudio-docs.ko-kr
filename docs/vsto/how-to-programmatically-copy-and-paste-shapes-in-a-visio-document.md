---
title: '방법: 프로그래밍 방식으로 셰이프 복사 및 붙여넣기 Visio 문서에서 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- shapes [Office development in Visual Studio], copying and pasting Visio shapes
- Visio [Office development in Visual Studio], copying and pasting Visio shapes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 488cda5519a211754498b50a88995de64a8ed366
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-copy-and-paste-shapes-in-a-visio-document"></a>방법: 프로그래밍 방식으로 Visio 문서에서 셰이프 복사 및 붙여넣기
  문서 한 페이지의 셰이프를 프로그래밍 방식으로 복사하고 동일한 문서의 새 페이지에 붙여넣을 수 있습니다. 기본 위치(활성 창의 가운데)에 붙여넣을 수도 있고 아니면 원래 페이지의 동일한 좌표 위치에 붙여넣을 수도 있습니다.  
  
## <a name="copying-and-pasting-shapes"></a>셰이프 복사 및 붙여넣기  
 개체 모델에 대한 세부 정보는 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](https://msdn.microsoft.com/library/office/ff765757.aspx), [Microsoft.Office.Interop.Visio.Shape.DrawOval](https://msdn.microsoft.com/library/office/ff767121.aspx), [Microsoft.Office.Interop.Visio.Shape.Copy](https://msdn.microsoft.com/library/office/ff765638.aspx), [Microsoft.Office.Interop.Visio.Shape.Paste](https://msdn.microsoft.com/library/office/ff768361.aspx) 메서드 및 [Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNormal](https://msdn.microsoft.com/library/office/ff765187.aspx) 플래그를 참조하세요.  
  
#### <a name="to-copy-shapes-to-the-center-of-another-page"></a>셰이프를 다른 페이지의 가운데에 복사하려면  
  
-   다음 예제에서는 첫 번째 페이지에서 셰이프를 복사하여 두 번째 페이지의 가운데에 붙여넣는 방법을 보여 줍니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#14)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#14)]  
  
## <a name="copying-and-pasting-shapes-with-the-same-positions"></a>동일한 위치를 사용하여 셰이프 복사 및 붙여넣기  
 개체 모델에 대한 세부 정보는 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](https://msdn.microsoft.com/library/office/ff765757.aspx), [Microsoft.Office.Interop.Visio.Shape.DrawOval](https://msdn.microsoft.com/library/office/ff767121.aspx), [Microsoft.Office.Interop.Visio.Shape.Copy](https://msdn.microsoft.com/library/office/ff765638.aspx), [Microsoft.Office.Interop.Visio.Shape.Paste](https://msdn.microsoft.com/library/office/ff768361.aspx) 메서드 및 [Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNoTranslate](https://msdn.microsoft.com/library/office/ff765187.aspx) 플래그를 참조하세요.  
  
 붙여넣은 정보의 형식을 제어 하 고 (선택 사항) 원본 파일 (예를 들어 Microsoft Office Word 문서)에 대 한 링크를 설정 해야 할 경우 PasteSpecial 메서드를 사용 합니다.  
  
#### <a name="to-copy-shapes-and-shape-locations-to-another-page"></a>셰이프 및 셰이프 위치를 다른 페이지에 복사하려면  
  
-   다음 예제에서는 첫 번째 페이지에서 셰이프를 복사하고 원래 좌표 위치를 사용하여 두 번째 페이지에 붙여넣는 방법을 보여 줍니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#15)]  
  
## <a name="see-also"></a>참고 항목  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [Visio 셰이프 작업](../vsto/working-with-visio-shapes.md)   
 [방법: 프로그래밍 방식으로 Visio 문서에 셰이프 추가](../vsto/how-to-programmatically-add-shapes-to-a-visio-document.md)  
  
  