---
title: VSIX v 3에서 Ngen 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/09/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 1472e884-c74e-4c23-9d4a-6d8bdcac043b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 146df23bff14bd93558c645521f99f6099a49bde
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ngen-support-in-vsix-v3"></a>VSIX v 3에서 Ngen 지원

Visual Studio 2017 및 새 VSIX v3 (버전 3) 확장 매니페스트 형식으로 확장 개발자 있습니다 "ngen" 설치 중에 어셈블리입니다.

다음은 어떤 "ngen" 설명 하는 MSDN에서 발췌 한 내용이입니다.

>네이티브 이미지 생성기(Ngen.exe)는 관리되는 응용 프로그램의 성능을 향상시키는 도구입니다. Ngen.exe는 컴파일된 프로세서별 컴퓨터 코드가 포함된 파일인 네이티브 이미지를 만들어서 로컬 컴퓨터의 네이티브 이미지 캐시에 설치합니다. 런타임은 JIT(Just-In-Time) 컴파일러를 사용하지 않고 캐시의 네이티브 이미지를 사용하여 원본 어셈블리를 컴파일할 수 있습니다.
>
>[Ngen.exe (네이티브 이미지 생성기)](https://msdn.microsoft.com/en-us/library/6t9t5wcf(v=vs.110).aspx)

"Ngen" 어셈블리에서 순서로 VSIX "인스턴스별 컴퓨터별"를 설치 합니다. Extension.vsixmanifest 디자이너에 있는 "모든 사용자" 확인란을 선택 하 여이 사용할 수 있습니다.

![모든 사용자를 확인 합니다.](media/check-all-users.png)

## <a name="how-to-enable-ngen"></a>Ngen을 사용 하는 방법

Ngen 어셈블리를 사용 하려면 사용할 수 있습니다는 **속성** Visual Studio의 창.

설정할 수 있는 속성 4 가지가 있습니다.

1. **Ngen** (부울)-Visual Studio 설치 관리자를 True 이면 "ngen" 어셈블리를 됩니다.
2. **Ngen 응용 프로그램** (string)-Ngen 어셈블리 종속성을 확인 하기 위해 응용 프로그램의 app.config 파일을 사용 하 여를 제공 합니다. 응용 프로그램 (Visual Studio 설치 디렉터리)에 상대적인 사용 하려면 해당 app.config에이 값을 설정 해야 합니다.
3. **Ngen 아키텍처** (enum)-기본적으로 어셈블리를 컴파일할 아키텍처. 옵션은:는 합니다. NotSpecified b 합니다. X86 c 합니다. X64 d입니다. 모두
4. **Ngen 우선 순위** (1과 3 사이의 정수)-The Ngen 우선 순위 수준에 설명 되어 [Ngen.exe 우선 순위 수준을](https://msdn.microsoft.com/en-us/library/6t9t5wcf(v=vs.110).aspx#Anchor_3)합니다.

살펴보겠습니다는 **속성** 작업에서 창:

![속성에 ngen](media/ngen-in-properties.png)

이렇게 하면 메타 데이터는 VSIX 프로젝트의.csproj 파일 내에서 해당 프로젝트 참조에 추가 됩니다.

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
    <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
    <Name>ClassLibrary1</Name>
    <Ngen>True</Ngen>
    <NgenApplication>vsn.exe</NgenApplication>
    <NgenArchitecture>X86</NgenArchitecture>
    <NgenPriority>2</NgenPriority>
</ProjectReference>
 ```

 >**참고:** 원하는 경우.csproj 파일을 직접 편집할 수 있습니다.

## <a name="extra-information"></a>추가 정보

둘 이상의 프로젝트 참조;에 대 한 디자이너 속성 변경 내용을 적용합니다 항목에 대 한 Ngen 메타 데이터도 프로젝트 내에서 설정할 수 있습니다 (사용 하 여 위에서 설명한 동일한 방법을) 만큼 항목은.NET 어셈블리.