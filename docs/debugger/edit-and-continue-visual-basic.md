---
title: 편집 하며 계속 하기 (Visual Basic) | Microsoft Docs
ms.custom: ''
ms.date: 10/11/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue, 64-bit
- Edit and Continue [Visual Basic]
- debugging [Visual Basic], Edit and Continue
- Visual Basic, Edit and Continue
- 64-bit Edit and Continue
ms.assetid: 7e90f34f-e699-45ab-a4c9-a4b527c498c8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aa3b8c287129c164d8c6984ac52375d6012fbd68
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="edit-and-continue-visual-basic"></a>편집하며 계속하기(Visual Basic)
[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 디버깅의 편집하며 계속하기 기능을 사용하면 코드가 중단 모드에서 실행되는 동안 코드를 변경할 수 있습니다. 코드 편집을 적용한 후에 새 편집 내용이 적용된 상태로 코드 실행을 다시 시작하고 그 결과를 확인할 수 있습니다.  
  
 편집하며 계속하기 기능은 중단 모드를 시작할 때마다 사용할 수 있습니다. 중단 모드, 명령 포인터, 소스 창에서 노랑 화살표, 포인트 수 있는 메서드 또는 속성 본문에서 실행 가능 문이 포함 된 줄에 다음을 실행 합니다.

 편집하며 계속하기에서는 디버깅 세션 중에 수행할 수 있는 대부분의 변경 내용을 지원하지만 몇 가지 예외가 있습니다. 자세한 내용은 참조 [지원 코드 변경 내용 (C# 및 Visual Basic)](../debugger/supported-code-changes-csharp.md)합니다.   
  
 허용되지 않는 편집 작업을 수행하면 변경 내용 아래에 자주색 물결선이 표시되고 작업 목록에 이 작업이 나타납니다. 편집하며 계속하기를 진행하려면 허용되지 않는 편집 작업을 취소해야 합니다. 편집하며 계속하기 외부에서는 허용되지 않는 특정 작업이 허용될 수도 있습니다. 이러한 허용되지 않는 편집의 결과를 유지하려면 디버깅을 중지하고 응용 프로그램을 다시 시작해야 합니다.  
  
 편집 하며 계속 하기는 Windows 10 용 UWP 앱 및.NET Framework 4.6을 대상으로 하는 x86 및 x64 응용 프로그램에서 지원 됩니다 (.NET Framework는 데스크톱 버전은)는 데스크톱 또는 이후 버전입니다.

 > [!NOTE]
 > 지원 되지 않는 앱 및 플랫폼에는 ASP.NET 5, Silverlight 5 및 Windows 8.1 포함 됩니다.
  
 편집 하며 계속 하기를 사용 하 여 디버깅을 시작할 때 지원 되지 않습니다 **프로세스에 연결**합니다. 편집 하며 계속 하기가 지원 되지 않는 최적화 된 코드 또는 혼합 관리 / 네이티브 코드입니다. 자세한 내용은 참조 [지원 되는 코드 변경 (C# 및 Visual Basic](../debugger/supported-code-changes-csharp.md)합니다.
  
 이 단원의 항목에서는 이 기능을 사용하는 방법과 허용되지 않는 종류의 변경에 대한 자세한 내용을 제공합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 편집하며 계속하기를 사용하여 중단 모드에서 편집 적용](../debugger/how-to-apply-edits-in-break-mode-with-edit-and-continue.md)  
 중단 모드에서 코드 편집 내용을 적용하는 방법에 대해 설명합니다.  
  
 [지원 되는 코드 변경 내용 (C# 및 Visual Basic](../debugger/supported-code-changes-csharp.md)   
 [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)] 편집하며 계속하기에서 수행할 수 없는 편집 유형에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [편집하며 계속하기](../debugger/edit-and-continue.md)  
 편집하며 계속하기에 대한 항목 목록을 제공합니다.