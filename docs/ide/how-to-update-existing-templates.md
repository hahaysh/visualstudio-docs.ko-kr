---
title: Visual Studio에서 기존 프로젝트 및 항목 템플릿 업데이트
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: f5cf764f76d72b17128c46f2b7ec16ffcf4153cf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-update-existing-templates"></a>방법: 기존 템플릿 업데이트

템플릿을 만들고 파일을 *.zip* 파일로 압축한 후 템플릿을 수정하려고 할 수 있습니다. 템플릿의 파일을 수동으로 변경하거나 해당 템플릿을 기반으로 하는 프로젝트에서 새 템플릿을 내보내는 방법으로 이 작업을 수행할 수 있습니다.

## <a name="using-the-export-template-wizard-to-update-an-existing-project-template"></a>템플릿 내보내기 마법사를 사용하여 기존 프로젝트 템플릿 업데이트

Visual Studio에서는 기존 템플릿을 업데이트하는 데 사용할 수 있는 **템플릿 내보내기** 마법사를 제공합니다.

1. **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.

1. 업데이트할 템플릿을 선택하고 프로젝트의 이름과 위치를 입력한 다음 **확인**을 선택합니다.

1. Visual Studio에서 프로젝트를 수정합니다.

1. **프로젝트** 메뉴에서 **템플릿 내보내기**를 선택합니다.

    **템플릿 내보내기 마법사**가 열립니다.

1. 마법사에서 표시되는 메시지를 따라 템플릿을 *.zip* 파일로 내보냅니다.

1. (선택 사항) **새 프로젝트** 대화 상자에 템플릿을 추가하려면 *%USERPROFILE%\Documents\Visual Studio \<버전\>\Templates\ProjectTemplates* 디렉터리에 *.zip* 파일을 추가합니다. **템플릿 내보내기 마법사**에서 **템플릿을 자동으로 Visual Studio로 가져오기** 옵션을 선택하지 않은 경우 이 단계를 수행해야 합니다.

1. 이전 템플릿 *.zip* 파일을 삭제합니다.

## <a name="manually-update-an-existing-template"></a>기존 템플릿 수동 업데이트

압축된 *.zip* 파일에 있는 파일을 수정하여 **템플릿 내보내기 마법사**를 사용하지 않고 기존 템플릿을 업데이트할 수 있습니다.

### <a name="to-manually-update-an-existing-template"></a>기존 템플릿을 수동으로 업데이트하려면

1. 템플릿을 포함하는 *.zip* 파일을 찾습니다. 사용자 프로젝트 템플릿은 일반적으로 *%USERPROFILE%\Documents\Visual Studio \<버전\>\Templates\ProjectTemplates*에 있습니다.

1. *.zip* 파일의 압축을 풉니다.

1. 현재 템플릿 파일을 수정 또는 삭제하거나 템플릿에 새 파일을 추가합니다.

1. *.vstemplate* XML 파일을 열어서 수정한 다음, 저장하여 업데이트된 동작 또는 새 파일을 처리합니다.

    *.vstemplate* 스키마에 대한 자세한 내용은 [Visual Studio 템플릿 스키마 참조(확장성)](../extensibility/visual-studio-template-schema-reference.md)를 참조하세요. 원본 파일에서 매개 변수화할 수 있는 항목에 대한 자세한 내용은 [템플릿 매개 변수](../ide/template-parameters.md)를 참조하세요.

1. 템플릿에 있는 파일을 선택하고 마우스 오른쪽 단추를 클릭하면 나타나는 메뉴, 즉 바로 가기 메뉴에서 **보내기** > **압축(ZIP) 폴더**를 선택합니다.

    선택한 파일이 *.zip* 파일로 압축됩니다.

1. 새 *.zip* 파일을 이전 *.zip* 파일과 같은 디렉터리에 넣습니다.

1. 추출된 템플릿 파일과 이전 템플릿 *.zip* 파일을 삭제합니다.

## <a name="see-also"></a>참고 항목

- [템플릿 사용자 지정](../ide/customizing-project-and-item-templates.md)
- [프로젝트 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)
- [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)
- [템플릿 매개 변수](../ide/template-parameters.md)
- [방법: 시작 키트 만들기](../ide/how-to-create-starter-kits.md)