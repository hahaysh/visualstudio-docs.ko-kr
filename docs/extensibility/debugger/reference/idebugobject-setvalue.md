---
title: IDebugObject::SetValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject::SetValue
helpviewer_keywords:
- IDebugObject::SetValue method
ms.assetid: d652e09c-cdc1-4519-8116-d7c743f5679b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ae6f8f589c0dca8c97e1a9664d9eaa93bf9e8741
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugobjectsetvalue"></a>IDebugObject::SetValue
연속 된 일련의 바이트에서 개체의 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetValue(   
   BYTE* pValue,  
   UINT  nSize  
);  
```  
  
```csharp  
int SetValue(  
   byte[] pValue,   
   uint   nSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pValue`  
 [in] 새 값을 나타내는 바이트 배열입니다.  
  
 `nSize`  
 [in] 크기 (바이트)에서 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 배열의 값이에 복사 됩니다 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체를 기존 값을 대체 합니다. 새 값의 크기는 기존 값 보다 크거나 작을 수 있습니다. 이 `IDebugObject` null 참조일 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)