---
title: IDebugModuleLoadEvent2::GetModule | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugModuleLoadEvent2::GetModule
helpviewer_keywords:
- IDebugModuleLoadEvent2::GetModule
ms.assetid: c86482bb-9ce5-4e63-bbe0-969b50169424
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b6188ba6842a922fa0758a21c0f496f50889f8b3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmoduleloadevent2getmodule"></a>IDebugModuleLoadEvent2::GetModule
되는 모듈을 가져옵니다 로드 또는 언로드 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetModule(   
   IDebugModule2** pModule,  
   BSTR*           pbstrDebugMessage,  
   BOOL*           pbLoad  
);  
```  
  
```csharp  
int GetModule(   
   out IDebugModule2 pModule,  
   ref string        pbstrDebugMessage,  
   ref int           pbLoad  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pModule`  
 [out] 반환 된 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 로드 하거나 언로드하는 모듈을 나타내는 개체입니다.  
  
 `pbstrDebugMessage`  
 [out에서] 이 이벤트를 설명 하는 선택적 메시지를 반환 합니다. 이 매개 변수는 null 값을 메시지 없이 요청 됩니다.  
  
 `pbLoad`  
 [out에서] 0이 아닌 (`TRUE`) 모듈 로드 하 고 0 이면 (`FALSE`) 모듈의 언로드 작업이 수행 하는 경우. 이 매개 변수는 null 값, 상태가 요청 됩니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)