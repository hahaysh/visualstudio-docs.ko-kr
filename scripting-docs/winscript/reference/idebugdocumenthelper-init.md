---
title: IDebugDocumentHelper::Init | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugDocumentHelper.Init
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::Init
ms.assetid: 1dd5a01f-0779-4109-8c6c-f16f5a3835bf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 45cd57e4ba9e86bf84f927f487c637d61aa5339b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthelperinit"></a>IDebugDocumentHelper::Init
`Init` 메서드 이름과 초기 특성으로 디버그 문서 도우미를 초기화 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Init(  
   IDebugApplication*  pda,  
   LPCOLESTR           pszShortName,  
   LPCOLESTR           pszLongName,  
   TEXT_DOC_ATTR       docAttr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pda`  
 [in] 이 문서와 관련 된 디버그 응용 프로그램입니다.  
  
 `pszShortName`  
 [in] 문서의 짧은 이름이 포함 된 null로 끝나는 문자열입니다.  
  
 `pszLongName`  
 [in] 문서의 긴 이름을 포함 하는 null로 끝나는 문자열.  
  
 `docAttr`  
 [in] 텍스트 문서 특성을 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 이름과 초기 특성으로 디버그 문서 도우미를 초기화합니다.  
  
 이 문서 될 때까지 트리에 나타나지 않으면 `IDebugDocumentHelper::Attach` 호출 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHelper::Attach](../../winscript/reference/idebugdocumenthelper-attach.md)   
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [TEXT_DOC_ATTR 상수](../../winscript/reference/text-doc-attr-constants.md)