---
title: 웹 사이트 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- web site projects
ms.assetid: ce9f4266-bb64-4c09-be88-4bd6413f60d0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d3da310c6695598eef36998cc562f6d477eff29
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="web-site-support"></a>웹 사이트 지원
웹 사이트 프로젝트 시스템은 웹 프로젝트를 만드는 프로젝트 시스템. 웹 프로젝트는 웹 응용 프로그램에 만듭니다. 웹 사이트 프로젝트 코드를 연결 된 각 웹 페이지에 대 한 하나의 실행 파일을 생성 합니다. 실행 파일을 추가 /App_Code 폴더의 소스 코드 파일에서 생성 됩니다.  
  
 웹 사이트 프로젝트 시스템은 기존 프로젝트 시스템에 템플릿 및 등록 특성을 추가 하 여 생성 됩니다. 이러한 특성 중 하나는 언어에 대 한 IntelliSense 공급자를 선택합니다. IntelliSense 공급자 구현을 참조를 처리 하 고 캐시 된 스마트 웹 페이지를 요청 하는 경우 언어 컴파일러를 호출 합니다.  
  
 웹 페이지를 컴파일하는 데 사용 되는 언어 컴파일러에 등록 해야 [!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)]합니다. 사용할 수는 [ \<컴파일러 > 요소](/dotnet/framework/configure-apps/file-schema/compiler/compiler-element) 다음 예제와 같이 컴파일러를 등록 하려면 Web.config 파일에:  
  
```  
<system.codedom>  <compilers>    <compiler language="py;IronPython" extension=".py"       type="IronPython.CodeDom.PythonProvider, IronPython,       Version=1.0.2391.18146, Culture=neutral,       PublicKeyToken=b03f5f7f11d50a3a" />  </compilers></system.codedom>  
```  
  
## <a name="in-this-section"></a>섹션 내용  
 [웹 사이트 지원 템플릿](../../extensibility/internals/web-site-support-templates.md)  
 새 웹 사이트 프로젝트와 연결 된 항목을 만드는 데 사용할 수 있는 템플릿이 나열 됩니다.  
  
 [웹 사이트 지원 특성](../../extensibility/internals/web-site-support-attributes.md)  
 웹 사이트 프로젝트를 연결 하는 등록 특성을 표시 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 및 [!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)]합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [웹 프로젝트](../../extensibility/internals/web-projects.md)  
 두 종류의 웹 프로젝트, 웹 사이트 프로젝트와 웹 응용 프로그램 프로젝트의 개요를 제공 합니다.