---
title: 빌드 작업
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 5399BCB1-E317-4C7B-87B1-C531E985DE6E
ms.openlocfilehash: 3e876bbc20f2f2e86ba7ec4806f67f4a2573a089
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="build-actions"></a>빌드 작업

Mac용 Visual Studio 프로젝트의 모든 파일에는 빌드 중 파일에 발생하는 작업을 제어하는 빌드 작업이 있습니다. 아래 그림과 같이 파일을 마우스 오른쪽 단추로 클릭하고 **빌드 작업**으로 이동하면 이러한 빌드 작업을 설정할 수 있습니다.

![](media/projects-and-solutions-image1.png)

C# 프로젝트에 대한 몇 가지 일반적인 빌드 작업은 다음과 같습니다.

* **None** - 파일이 어떤 방식으로든 빌드에 속하지 않습니다. 단순히 IDE에서 쉽게 액세스하기 위해 프로젝트에 포함되었습니다.
* **Compile** - 파일이 C# 컴파일러에 소스 파일로 전달됩니다.
* **EmbeddedResource** - 파일이 어셈블리에 포함될 리소스로 C# 컴파일러에 전달됩니다. 그런 다음 `System.Reflection` 네임스페이스를 사용하여 어셈블리에서 파일을 읽을 수 있습니다.
* **Content** - ASP.NET 프로젝트의 경우 이러한 파일이 배포 시 사이트의 일부로 포함됩니다. Xamarin.iOS 및 Xamarin.Mac 프로젝트의 경우 앱 번들에 포함됩니다.

솔루션 탐색기에서 둘 이상의 파일을 선택하여 한 번에 여러 파일에 빌드 작업을 설정할 수 있습니다.

또한 특정 프로젝트에 대한 빌드 작업이 있습니다. 예를 들어 Xamarin.iOS 프로젝트에는 앱 번들의 일부로 파일을 추가하는 **BundleResource** 빌드 작업이 있습니다. Xamarin.Android 특정 빌드 작업에 대한 정보는 [빌드 프로세스](/xamarin/android/deploy-test/building-apps/build-process#Build_Actions) 가이드에서 확인할 수 있습니다.