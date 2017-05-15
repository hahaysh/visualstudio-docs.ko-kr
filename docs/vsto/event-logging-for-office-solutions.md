---
title: "Office 솔루션에 대한 이벤트 로깅"
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
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 이벤트 뷰어"
  - "ClickOnce 배포[Visual Studio에서 Office 개발], 이벤트 뷰어"
  - "응용 프로그램 배포[Visual Studio에서 Office 개발], 이벤트 뷰어"
  - "Visual Studio에서 Office 개발, 이벤트 뷰어"
ms.assetid: 31a246fe-ce1c-4f0e-9a21-9cf974c247fe
caps.latest.revision: 33
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 32
---
# Office 솔루션에 대한 이벤트 로깅
  Windows에서 이벤트 뷰어를 사용하여 Office 솔루션을 설치하거나 제거할 때 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서 캡처되는 예외 메시지를 확인할 수 있습니다. 이벤트 로거에서 이러한 메시지를 사용하여 설치 및 배포 문제를 해결할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## 이벤트 로그 읽기  
 **이벤트 뷰어**를 열고 확인하려는 이벤트를 필터링합니다.  
  
#### Windows Server 2003 및 Windows XP에서 이벤트 로그를 읽으려면  
  
1.  제어판에서 **관리 도구**를 엽니다.  
  
2.  **이벤트 뷰어**를 시작합니다.  
  
3.  이벤트 로그의 목록에서 **응용 프로그램**을 선택합니다.  
  
4.  **보기** 메뉴에서 **필터**를 클릭합니다.  
  
5.  **이벤트 원본** 목록에서 **VSTO 4.0**을 선택합니다.  
  
6.  설치 이벤트의 경우 **이벤트 ID** 상자에 **4096**을 입력합니다.  
  
7.  **확인**을 클릭하여 필터링된 보기를 확인합니다.  
  
#### Windows 7, Windows Vista 및 Windows Server 2008에서 이벤트 로그를 읽으려면  
  
1.  제어판에서 **관리 도구**를 엽니다.  
  
2.  **이벤트 뷰어**를 시작합니다.  
  
3.  **Windows 로그**를 확장합니다.  
  
4.  이벤트 로그의 목록에서 **응용 프로그램**을 선택합니다.  
  
5.  **동작** 메뉴에서 **현재 로그 필터링**을 클릭합니다.  
  
6.  **이벤트 원본** 목록에서 **VSTO 4.0**을 선택합니다.  
  
7.  설치 이벤트의 경우 **이벤트 ID** 상자에 **4096**을 입력합니다.  
  
8.  **확인**을 클릭하여 필터링된 보기를 확인합니다.  
  
 이벤트 뷰어는 다음과 같은 정보를 포함합니다.  
  
-   솔루션에 대한 배포 매니페스트의 위치  
  
-   오류 또는 예외의 원인을 설명하는 메시지  
  
 이러한 예외 메시지를 통해 신뢰할 수 없는 인증서, 신뢰할 수 없는 문서 위치 또는 잘못된 배포 매니페스트 등 설치 문제의 원인을 확인할 수 있습니다.  
  
 Office 솔루션을 제거한 후에도 예외 메시지는 이벤트 로그에 남아있습니다.  
  
 Office 솔루션을 실행 중일 때 예외 메시지를 표시하거나 기록하려면 [Office 프로젝트 디버깅](../vsto/debugging-office-projects.md) 및 [Office 프로젝트 디버깅](../vsto/debugging-office-projects.md)을 참조하세요.  
  
### 지역화  
 예외 메시지의 언어는 Visual Studio Tools for Office Runtime 도구에 의해 결정됩니다. 예를 들어 최종 사용자의 컴퓨터에 일본어 언어 팩이 설치되어 있다면 예외 메시지는 일본어로 이벤트 로그에 기록됩니다.  
  
## 이벤트 로거를 사용하지 않도록 설정  
 기본적으로 이벤트 로거는 Office 솔루션을 설치하거나 제거할 때 사용됩니다. VSTO\_EVENTLOGDISABLED 환경 변수를 “1”로 설정하여 이벤트 로거를 사용하지 않도록 설정할 수 있습니다.  
  
#### 이벤트 로그를 사용하지 않도록 설정하려면  
  
1.  제어판에서 **시스템**을 엽니다.  
  
2.  **고급** 탭에서 **환경 변수**를 클릭합니다.  
  
3.  **시스템 변수** 창에서 **새로 만들기**를 클릭합니다.  
  
4.  **새 시스템 변수** 대화 상자에서 **변수 이름** 상자에 **VSTO\_EVENTLOGDISABLED**를 입력합니다.  
  
5.  **변수 값** 상자에 **1**을 입력합니다.  
  
6.  **확인**을 클릭합니다.  
  
## 참고 항목  
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [Office 솔루션 배포 문제 해결](../vsto/troubleshooting-office-solution-deployment.md)  
  
  