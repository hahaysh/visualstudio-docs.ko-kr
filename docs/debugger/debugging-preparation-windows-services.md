---
title: '디버깅 준비: Windows 서비스 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], Windows services
- Windows Service applications, debugging
ms.assetid: ac0a99f7-ec3d-4a20-b17f-698a817fdcc2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ed27902be01868955618970d376a4615627d05dc
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-preparation-windows-services"></a>디버깅 준비: Windows 서비스
Windows 서비스는 Microsoft Windows에서 백그라운드로 실행되는 프로그램입니다. 예를 들어, 컴퓨터의 시간을 업데이트하는 Windows 시간 서비스와 텔넷 서비스가 Windows 서비스에 포함됩니다. Windows 서비스는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 내에서 실행할 수 없고 서비스 제어 관리자의 컨텍스트 내에서 실행해야 합니다. 자세한 내용은 참조 [Windows 서비스 만들기](/dotnet/framework/windows-services/how-to-create-windows-services), [Windows 서비스 응용 프로그램 디버깅](/dotnet/framework/windows-services/how-to-debug-windows-service-applications), 및 [Windows 서비스 응용 프로그램](/dotnet/framework/windows-services/index)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) (관리 코드 디버그)  
 [C#, F# 및 Visual Basic 프로젝트 형식](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [C# 디버그 구성을 위한 프로젝트 설정](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Visual Basic 디버그 구성을 위한 프로젝트 설정](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [방법: OnStart 메서드 디버그](../debugger/how-to-debug-the-onstart-method.md)