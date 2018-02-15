---
title: "Azure Virtual Machine에서 Visual Studio 사용 | Microsoft Docs"
description: "Azure Virtual Machine에서 Visual Studio를 사용하는 방법에 대한 자세한 정보"
ms.date: 01/30/2018
ms.technology: vs-acquisition
ms.topic: article
helpviewer_keywords:
- azure services
- virtual machine; VM
- installation
- visual studio
author: PhilLee-MSFT
ms.author: phillee
manager: sacalla
ms.workload:
- multiple
ms.openlocfilehash: d8e99965867d5dbc2710d6c56c5b3dc90fc16dc8
ms.sourcegitcommit: 4b4027244b8de25e30b533148804b87321d3e8a6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2018
---
# <a id="top"> </a> Azure의 Visual Studio 이미지
사전 구성된 Azure VM(가상 머신)에서 실행되는 Visual Studio를 사용하는 것이 제대로 작동하는 개발 환경을 처음부터 구현하는 가장 쉽고 빠른 방법입니다.  다양한 Visual Studio 구성을 포함하는 시스템 이미지가 [Azure Marketplace](https://portal.azure.com/)에서 제공됩니다. VM을 부팅하기만 하면 됩니다.

Azure를 처음 사용하는 경우 [체험 Azure 계정을 만드세요](https://azure.microsoft.com/free).

## <a name="what-configurations-and-versions-are-available"></a>사용 가능한 구성 및 버전은 무엇인가요?
Azure Marketplace에서 최신 주 버전(Visual Studio 2017 및 Visual Studio 2015)용 이미지를 찾을 수 있습니다.  주 버전마다 원래 릴리스된( ‘RTW’) 버전과 업데이트된 “최신” 버전이 표시됩니다.  각 버전에 대한 Visual Studio Enterprise 및 Visual Studio Community 버전이 있습니다.  이러한 이미지는 최신 Visual Studio 및 Windows 업데이트를 포함하도록 매달 한 번 이상 업데이트됩니다.  이미지 이름은 동일하지만 각 이미지의 설명에 설치된 제품 버전과 이미지의 ‘기준’ 날짜가 포함되어 있습니다.

|               릴리스 버전              |        버전       |     제품 버전     |
|:------------------------------------------:|:---------------------:|:-----------------------:|
| Visual Studio 2017 - 최신(버전 15.5) | Enterprise, Community |      버전 15.5.3     |
|         Visual Studio 2017 - RTW           | Enterprise, Community |      버전 15.0.7     |
|   Visual Studio 2015 - 최신(업데이트 3)   | Enterprise, Community |  버전 14.0.25431.01  |
|         Visual Studio 2015 - RTW           |         없음          | (서비스 만료됨) |

> [!NOTE]
> Microsoft 서비스 정책에 따라 원래 릴리스된(‘RTW’) Visual Studio 2015 버전에 대한 서비스가 만료되었습니다.  따라서 Visual Studio 2015 업데이트 3이 Visual Studio 2015 제품 라인에 대해 제공되는 유일한 버전입니다.

자세한 내용은 [Visual Studio 서비스 정책](https://www.visualstudio.com/en-us/productinfo/vs-servicing-vs)을 참조하세요.

## <a name="what-features-are-installed"></a>설치된 기능은 무엇인가요?
각 이미지에는 해당 Visual Studio 버전에 권장되는 기능 집합이 포함되어 있습니다.  일반적으로 설치에는 다음이 포함됩니다.

* 권장되는 선택적 구성 요소를 포함하는 사용 가능한 모든 워크로드
* .NET 4.6.2 및 .NET 4.7 SDK, 타기팅 팩 및 개발자 도구
* Visual F#
* Visual Studio용 GitHub 확장
* LINQ to SQL 도구

이미지를 빌드할 때 Visual Studio를 설치하는 데 사용하는 명령줄은 다음과 같습니다.

```
    vs_enterprise.exe --allWorkloads --includeRecommended --passive ^
       add Microsoft.Net.Component.4.7.SDK ^
       add Microsoft.Net.Component.4.7.TargetingPack ^ 
       add Microsoft.Net.Component.4.6.2.SDK ^
       add Microsoft.Net.Component.4.6.2.TargetingPack ^
       add Microsoft.Net.ComponentGroup.4.7.DeveloperTools ^
       add Microsoft.VisualStudio.Component.FSharp ^
       add Component.GitHub.VisualStudio ^
       add Microsoft.VisualStudio.Component.LinqToSql
```

이미지에 필요한 Visual Studio 기능이 없는 경우 피드백 도구(페이지의 오른쪽 위)를 통해 피드백을 제공하세요.

## <a name="what-size-vm-should-i-choose"></a>어떤 크기의 VM을 선택해야 하나요?
새 가상 머신을 쉽게 프로비전할 수 있으며, Azure에서 전체 범위의 가상 머신 크기를 제공합니다.  하드웨어 구입과 마찬가지로 성능 대비 비용을 고려하는 것이 좋습니다.  Visual Studio는 강력한 다중 스레드 응용 프로그램이므로 최소한 프로세서 2개와 7GB 메모리가 포함된 VM 크기를 선택하는 것이 좋습니다. Azure에서 이 요구 사항은 최소한 다음과 같은 VM 크기를 의미합니다.

   * Standard_D2_v3
   * Standard_D2s_v3
   * Standard_D4_v3
   * Standard_D4s_v3
   * Standard_D2_v2
   * Standard_D2S_v2
   * Standard_D3_v2

최신 머신 크기에 대한 자세한 내용은 [Azure의 Windows 가상 머신 크기](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/sizes)를 참조하세요.

Azure를 사용하면 처음에 선택한 크기에 관계없이 VM 크기를 조정하여 초기 선택을 다시 조정할 수 있습니다.  새 VM을 더 적합한 크기로 프로비전하거나 기존 VM의 크기를 다른 기본 하드웨어로 조정할 수 있습니다.  자세한 내용은 [Windows VM 크기 조정](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/resize-vm)을 참조하세요.

## <a name="after-i-get-the-vm-running-then-what"></a>VM을 실행한 후에는 어떻게 해야 하나요?
Visual Studio는 Azure의 “사용자 라이선스 필요” 모델을 따릅니다.  따라서 독점 하드웨어의 설치와 마찬가지로, 첫 번째 단계 중 하나는 Visual Studio 설치에 대한 라이선스를 부여하는 것입니다.  Visual Studio 구독과 연결된 Microsoft 계정으로 로그인하여 Visual Studio의 잠금을 해제하거나 초기 구입 시 받은 제품 키를 사용하여 Visual Studio의 잠금을 해제할 수 있습니다.  자세한 내용은 [Visual Studio에 로그인](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) 및 [Visual Studio의 잠금을 해제하는 방법](https://docs.microsoft.com/en-us/visualstudio/ide/how-to-unlock-visual-studio)을 참조하세요.

## <a name="after-i-build-out-the-dev-vm-how-do-i-save-capture-it-for-future-or-team-use"></a>개발 VM을 빌드한 후 나중에 사용하거나 팀 사용을 위해 저장(캡처)하려면 어떻게 하나요?

개발 환경의 스펙트럼은 매우 크며, 더 복잡한 환경을 빌드할 경우 연관된 실제 비용이 있습니다.  그러나 환경 구성에 관계없이 Azure는 본인이나 다른 팀 구성원이 나중에 사용할 수 있도록 완벽하게 구성된 VM을 ‘기준 이미지’로 저장/캡처하여 투자를 쉽게 보존할 수 있게 합니다.  그런 다음 새 VM을 부팅할 때 Marketplace 이미지 대신 기준 이미지에서 프로비전하면 됩니다.

간단히 요약하면, 실행 중인 VM을 sysprep 및 종료한 다음 Azure Portal의 UI를 통해 VM을 이미지로 *캡처(그림 1)*합니다.  Azure는 이미지가 포함된 `.vhd` 파일을 선택한 저장소 계정에 저장합니다.  새 이미지는 구독의 리소스 목록에 이미지 리소스로 표시됩니다.

<img src="media/capture-vm.png" alt="Capture an image through the Azure portal’s UI" style="border:3px solid Silver; display: block; margin: auto;"><center>*(그림 1) Azure Portal의 UI를 통해 이미지 캡처*</center>

자세한 내용은 [이미지에 VM 캡처](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/capture-image-resource)를 참조하세요.

  **미리 알림:** VM을 sysprep하는 것을 잊지 마세요.  이 단계를 수행하지 않으면 Azure가 이미지에서 VM을 프로비전할 수 없습니다.

> [!NOTE]
> 이미지 저장 비용이 일부 발생하지만, 이 증분 비용은 VM이 필요한 팀 구성원마다 VM을 처음부터 다시 빌드하기 위한 인력 비용에 비해 훨씬 저렴합니다.  예를 들어 팀의 모든 구성원이 다시 사용할 수 있는 127GB 이미지를 만들고 저장하는 데 필요한 비용은 매달 몇 달러입니다.  이 비용은 각 직원이 개별적으로 사용할, 제대로 구성된 개발 시스템을 빌드 및 검증하는 데 소요되는 시간에 비해 중요하지 않습니다.

또한 개발 작업 또는 기술은 다양한 개발 구성 및 여러 머신 구성과 같은 추가 확장성이 필요할 수 있습니다.  Azure DevTest Labs를 사용하여 ‘골든 이미지’의 구성을 자동화하는 _레시피_를 만들고 팀이 실행 중인 VM에 대한 정책을 관리할 수 있습니다.  [개발자용 Azure DevTest Labs 사용](https://docs.microsoft.com/en-us/azure/devtest-lab/devtest-lab-developer-lab)에서 DevTest Labs에 대한 자세한 정보를 확인할 수 있습니다.

## <a name="next-steps"></a>다음 단계
이제 사전 구성된 Visual Studio 이미지에 대해 살펴보았으며, 다음 단계에서는 새 VM을 만들겠습니다.

* [Azure Portal을 통해 VM 만들기](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal)
* [Windows 가상 머신 개요](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/overview)