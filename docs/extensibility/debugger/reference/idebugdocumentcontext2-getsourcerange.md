---
title: IDebugDocumentContext2::GetSourceRange | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocumentContext2::GetSourceRange
helpviewer_keywords:
- IDebugDocumentContext2::GetSourceRange
ms.assetid: 5903c75e-5390-4d13-9314-1ee276255313
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f003ba3f97f053c4617408bfc9334da057bb98ef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdocumentcontext2getsourcerange"></a>IDebugDocumentContext2::GetSourceRange
이 문서 컨텍스트의 소스 코드 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSourceRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```csharp  
int GetSourceRange(   
   TEXT_POSITION[] pBegPosition,  
   TEXT_POSITION[] pEndPosition  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pBegPosition`  
 [out에서] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조 시작 위치를 사용 하 여 입력 됩니다. 이 정보가 필요 하지 않은 경우이 인수를 null 값으로 설정 합니다.  
  
 `pEndPosition`  
 [out에서] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조 끝 위치를 사용 하 여 입력 됩니다. 이 정보가 필요 하지 않은 경우이 인수를 null 값으로 설정 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 소스 범위에 기여 하는 코드는 이전 문을 직후를 현재 문 뒤에서 소스 코드의 전체 범위가입니다. 소스 범위는 일반적으로 소스 문, 주석, 디스어셈블리 창에서 코드를 포함 하 여 혼합 하는 데 사용 됩니다.  
  
 이 문서 컨텍스트 내에 포함 된 코드 문에 대 한 범위를 가져오려면 호출는 [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)