---
title: FuncDebugStart | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- FuncDebugStart symbol
- debugging [DIA SDK], start point
ms.assetid: 1cbc6ca5-87d0-4c30-a39e-0a9dc62ce1a9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d8d3b8a518f95c8374f16e60fd91b0321177442e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="funcdebugstart"></a>FuncDebugStart
함수는 디버깅에 정의 된 지점에는 시작 지점에 대 한 기호도 식별 되는 `SymTagFuncDebugStart` 태그입니다.  
  
## <a name="properties"></a>속성  
 다음 표에서이 기호 형식에 대해 사용할 수 있는 속성을 보여 줍니다.  
  
|속성|데이터 형식|설명|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|오프셋된 부분의 location; 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)합니다.|  
|[IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|섹션 부분의 location; 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)합니다.|  
|[IDiaSymbol::get_customCallingConvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|`TRUE` 함수 (DIA SDK v 8.0 이상 에서만에서)에 사용자 지정 호출 규칙을 사용 합니다.|  
|[IDiaSymbol::get_farReturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|`TRUE` 함수 수행 (DIA SDK v 8.0 이상 에서만에서)까지 반환 합니다.|  
|[IDiaSymbol::get_interruptReturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|`TRUE` 경우 함수는 인터럽트 (DIA SDK v 8.0 이상 에서만에서)에서 반환을 포함 합니다.|  
|[IDiaSymbol::get_isStatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|`TRUE` 경우 (DIA SDK v 8.0 이상 에서만에서) 함수는 정적으로 표시 됩니다.|  
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|바깥쪽 함수에 대 한 기호입니다.|  
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 기호의 ID입니다.|  
|[IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|시작점 군데 정적; 자세한 내용은 참조 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)합니다.|  
|[IDiaSymbol::get_noInline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|`TRUE` 함수를 지정 된 경우는 [noinline](/cpp/cpp/noinline) 특성 (DIA SDK v 8.0 이상 에서만에서).|  
|[IDiaSymbol::get_noReturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|`TRUE` 함수를 지정 된 경우는 [noreturn](/cpp/cpp/noreturn) 특성 (DIA SDK v 8.0 이상 에서만에서).|  
|[IDiaSymbol::get_notReached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|`TRUE` 경우 (DIA SDK v 8.0 이상 에서만에서)는 함수가 호출 되지 않는 합니다.|  
|[IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|메모리에 있는 기호의 오프셋 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md), `LocIsRegRel`합니다.|  
|[IDiaSymbol::get_optimizedCodeDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|`TRUE` 코드에 최적화 된 코드 (DIA SDK v 8.0 이상 에서만에서)에 대 한 디버그 정보입니다.|  
|[IDiaSymbol::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|해당 블록 내에서 함수의 상대 위치입니다.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|기호 인덱스 ID입니다.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagFuncDebugStart` (중 하나는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값).|  
|[IDiaSymbol::get_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|함수는 실행 파일 내에서 위치입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)   
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)