---
title: '방법: Creator 메서드 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], Creator
- BDC [SharePoint development in Visual Studio], adding entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entity instances
- BDC [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Creator
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0424c6561b063b17f384215021a1300122dcbb1c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-a-creator-method"></a>방법: Creator 메서드 추가
  Creator 메서드는 엔터티 데이터 원본에 새 데이터를 추가합니다. BDC 비즈니스 데이터 연결 () 서비스는 사용자가 선택 하면이 메서드를 호출는 **새 항목** 모델을 기반으로 하는 목록의 리본에 단추입니다. 자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
### <a name="to-add-a-creator-method"></a>Creator 메서드를 추가 하려면  
  
1.  BDC 디자이너에서 엔터티를 선택 합니다.  
  
2.  메뉴 모음에서 **보기**, **다른 창**, **BDC 메서드 세부 정보**합니다.  
  
     **BDC 메서드 세부 정보** 창이 열립니다. 해당 창에 대 한 자세한 내용은 참조 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)합니다.  
  
3.  에 **메서드 추가** 목록에서 선택 **Creator 메서드 만들기**합니다.  
  
     Visual Studio는 모델에 다음과 같은 요소를 추가 하 고 이러한 요소에 표시 된 **BDC 메서드 세부 정보** 창.  
  
    -   라는 메서드 **만들기**합니다.  
  
    -   메서드에 대 한 입력된 매개 변수입니다.  
  
    -   메서드에 대 한 반환 매개 변수입니다.  
  
    -   매개 변수에 대 한 설명자를 입력 합니다.  
  
    -   메서드에 대 한 메서드 인스턴스입니다.  
  
     자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
4.  **솔루션 탐색기**, 엔터티에 대해 생성 된 서비스 코드 파일의 바로 가기 메뉴를 열고 선택한 후 **코드 보기**합니다.  
  
     엔터티 서비스 코드 파일에는 코드 편집기에서 열립니다. 엔터티 서비스 코드 파일에 대 한 자세한 내용은 참조 [비즈니스 데이터 연결 모델을 만드는](../sharepoint/creating-a-business-data-connectivity-model.md)합니다.  
  
5.  데이터 원본에 데이터를 추가 하는 작성자 메서드에 코드를 추가 합니다. 다음 예제에서는 SQL Server에 대 한 AdventureWorks 예제 데이터베이스에 연락처를 추가합니다.  
  
    > [!NOTE]  
    >  값을 바꿉니다는 `ServerName` 필드와 사용자 서버의 이름입니다.  
  
     [!code-csharp[SP_BDC#4](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#4)]
     [!code-vb[SP_BDC#4](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: 특정 Finder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 메서드에 매개 변수를 추가 합니다.](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)  
  
  