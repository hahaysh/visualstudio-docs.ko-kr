---
title: IDebugEngine2::RemoveAllSetExceptions | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::RemoveAllSetExceptions
helpviewer_keywords:
- IDebugEngine2::RemoveAllSetExceptions
ms.assetid: 165fbe89-802d-4d99-85ca-c10fd6cccc09
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e3446b910aa1e728319d0f4c7acdbf65b01d1cb4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugengine2removeallsetexceptions"></a>IDebugEngine2::RemoveAllSetExceptions
예외는 IDE가 특정 런타임 아키텍처 나 언어에 대 한 설정 목록을 제거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RemoveAllSetExceptions(   
   REFGUID guidType  
);  
```  
  
```csharp  
int RemoveAllSetExceptions(   
   ref Guid guidType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidType`  
 [in] 언어에 대 한 GUID 또는 런타임 아키텍처에만 적용 되는 디버그 엔진에 대 한 GUID입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 방법으로 제거 하는 예외에 대 한 이전 호출에서 설정 된 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) 메서드.  
  
 특정 예외를 제거 하려면 호출는 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)