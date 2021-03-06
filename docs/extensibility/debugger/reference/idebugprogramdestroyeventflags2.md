---
title: IDebugProgramDestroyEventFlags2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugProgramDestroyEventFlags2 interface
ms.assetid: d384ff71-dc71-40b9-a871-801f8b6a3418
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f6b57206159ce00fbb79e9f9af1a6353588df76c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogramdestroyeventflags2"></a>IDebugProgramDestroyEventFlags2
기본 동작을 재정의 하는 디버그 엔진을 사용 하도록 설정 된 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] UI는 디버그 세션을 종료 하는 경우.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProgramDestroyEventFlags2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스는 디버그 엔진에서 구현 됩니다. 만들고 프로세스의 수명 동안 여러 프로그램을 제거할 수 있는 호스트에 두는 것이 유용 합니다.  
  
## <a name="methods"></a>메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugProgramDestroyEventFlags2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)|검색 프로그램 플래그를 삭제 합니다.|  
  
## <a name="remarks"></a>설명  
 기본 동작은 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] UI 모든 프로그램 프로그램 보낸 후 디자인 모드로 다시 이동 하는 이벤트를 삭제 합니다. 이 인터페이스에 디버그 엔진을을 해당 동작을 변경할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll