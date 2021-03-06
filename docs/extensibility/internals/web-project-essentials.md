---
title: 웹 프로젝트 Essentials | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- web projects, essentials
ms.assetid: ca2f4e43-322c-4431-8680-52da846940bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6918c539409a31dfe5249adb5858ca20c8c2337c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="web-project-essentials"></a>웹 프로젝트 Essentials
웹 프로젝트는 웹 응용 프로그램을 만듭니다. 스마트 웹 페이지에 있는 웹 응용 프로그램을 만들려면 웹 프로젝트를 사용할 수 있습니다. 스마트 웹 페이지에는 필요에 따라 웹 페이지를 렌더링 하는 서버 쪽 코드를 있습니다.  
  
 와 같은 일반적인 프로그래밍 언어를 사용 하 여 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 또는 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]를 수집 하 고 사용자의 정보를 처리 하 고, 데이터베이스에 저장 등을 스마트 웹 페이지를 만들 수 있습니다.  
  
-   코드 숨김 모델 파일 확장명이.aspx 나.asmx 웹 페이지와 종속 된 소스 코드 파일을 연결 합니다. 예를 들어 hello.aspx 종속 된 소스 코드 파일 hello.aspx.cs가 있을 수 있습니다.  
  
-   스마트 웹 페이지에 연결 된 서버 쪽 코드는 웹 사이트 /bin 폴더에 있는 실행 파일로 컴파일됩니다.  
  
-   특정 웹 페이지에 연결 되지 않은 하는 도우미 클래스와 같은 추가 소스 코드 파일, 웹 사이트 /App_Code 폴더에 있습니다.  
  
    -   웹 사이트 프로젝트 (WSP) 각 스마트 웹 페이지에 대 한 실행 파일을 생성합니다. 실행 파일을 추가 /App_Code 폴더에서 소스 코드 파일에서 생성 됩니다.  
  
    -   WAP ()는 웹 응용 프로그램 프로젝트 /App_Code 폴더의 모든 소스 파일 뿐만 아니라 모든 스마트 웹 페이지에 대 한 코드를 결합 하는 단일 실행 파일을 생성 합니다.  
  
-   웹 프로젝트에 대 한 솔루션 파일은 웹 사이트 자체에서 별도로 있습니다. 기본적으로 솔루션 파일은 \Documents and 설정을\\*사용자 계정*\My Documents\\*\<Visual Studio # # # >*\Projects\\ *YourWebSite*합니다.  
  
    > [!NOTE]
    >  웹 사이트에는 솔루션 파일을 유지 하려면 방금 이동 후 다시 여십시오.  
  
-   Visual Studio에서 솔루션 파일이 없는 웹 사이트를 열면 새 솔루션 파일에 대 한 자동으로 생성 됩니다.  
  
-   웹 프로젝트는 프로젝트 파일이 있습니다. 프로젝트 정보는 솔루션 파일, web.config 파일 및 다른 위치에 저장 됩니다.  
  
-   웹 프로젝트에 전역 속성을 자동으로 추가 웹 프로젝트 솔루션 폴더에 저장소 파일을 만듭니다.  
  
-   페이지 지시문을 사용 하 여 스마트 웹 페이지는 서버 쪽 프로그래밍 언어와 연결할 수 또는 \<스크립트 runat = "server" > 태그입니다.  
  
-   또한 웹 페이지는 모든 스크립팅 언어로 작성 된 클라이언트 스크립트 블록의 모든 수를 가질 수 있습니다.  
  
-   웹 사이트 프로젝트 시스템은 프로젝트 및 항목 템플릿 및 등록을 추가 하 여 구현 되는 [!INCLUDE[vwprvw](../../extensibility/internals/includes/vwprvw_md.md)] 프로젝트.  
  
-   WAP 시스템 프로젝트 버전과 라고도 하는 프로젝트 하위 형식으로 구현 됩니다. [!INCLUDE[vwprvw](../../extensibility/internals/includes/vwprvw_md.md)] 프로젝트 WAP 시스템을 만드는 WAP 하위 형식에 따라 지원 됩니다. 프로젝트 하위 형식에 대 한 자세한 내용은 참조 하십시오. [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)합니다.  
  
-   스마트 웹 페이지는 서버 쪽 프로그래밍 언어와 HTML을 결합합니다. 서버 쪽 언어에 포함 된 언어를 라고 합니다. 웹 프로젝트 시스템이 포함 된 언어를 지원 하기 위해 구현 해야 합니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> 인터페이스의 제품군입니다.  
  
    -   편집기에 포함 된 언어를 지원 하기 위해 HTML 언어 서비스는 포함 된 언어 서비스에 포함 된 언어 코드를 표시 지연 해야 합니다.  
  
    -   항상 오류 표식 (빨간색 물결 모양) 코드 편집기의 기본 버퍼에 만들어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [웹 프로젝트](../../extensibility/internals/web-projects.md)