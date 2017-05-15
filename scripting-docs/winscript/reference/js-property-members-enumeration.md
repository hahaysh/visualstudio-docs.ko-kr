---
title: "JS_PROPERTY_MEMBERS 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: JS_PROPERTY_MEMBERS
apilocation: jscript9diag.dll
ms.assetid: 3b870e5c-5518-4073-8384-f0c9c1777d9e
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# JS_PROPERTY_MEMBERS 열거형
개체의 멤버에 대한 요청에 반환할 정보 형식을 지정하는 플래그입니다.  
  
## 구문  
  
```  
enum JS_PROPERTY_MEMBERS  
{  
   JS_PROPERTY_MEMBERS_ALL = 0,  
   JS_PROPERTY_MEMBERS_ARGUMENTS = 1  
} JS_PROPERTY_MEMBERS;  
```  
  
## Members  
  
### 값  
  
|이름|설명|  
|--------|--------|  
|`JS_PROPERTY_MEMBERS_ALL`|모든 멤버를 열거하기 위한 요청을 나타냅니다.|  
|`JS_PROPERTY_MEMBERS_ARGUMENTS`|인수에만 열거 하는 요청을 나타냅니다.|  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)