---
title: "IEnumRemoteDebugApplications::Next | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumRemoteDebugApplications.Next
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IEnumRemoteDebugApplications::Next"
ms.assetid: 33f6c620-6dd3-4057-b982-b88a7a1f02b4
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IEnumRemoteDebugApplications::Next
`Next` 세그먼트 열거 시퀀스에서 지정한 개수의 메서드를 검색 합니다.  
  
## 구문  
  
```  
HRESULT Next(  
   ULONG                      celt,  
   IRemoteDebugApplication**  ppda,  
   ULONG*                     pceltFetched  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 검색 하는 세그먼트의 수입니다.  
  
 `ppda`  
 \[out\] 배열을 반환 합니다. `IRemoteDebugApplication` 인터페이스를 검색 하는 세그먼트를 나타냅니다.  
  
 `pceltFetched`  
 \[out\] 실제 수 열거자에서 반입 되는 세그먼트입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 세그먼트 열거 시퀀스에서 지정한 개수의 검색합니다.  
  
## 참고 항목  
 [IEnumRemoteDebugApplications 인터페이스](../../winscript/reference/ienumremotedebugapplications-interface.md)