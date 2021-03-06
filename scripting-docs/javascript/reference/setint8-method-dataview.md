---
title: "setInt8 메서드 (DataView) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 0a0e1450-e0c4-4778-8706-4d332442d882
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d6f9bd9c4b3bea25686036d199d1a987927172d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setint8-method-dataview"></a>setInt8 메서드(DataView)
보기의 시작 부분부터 지정 된 바이트 오프셋에 Int8 값을 저장 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
dataView.setInt8(byteOffset, value);   
```  
  
## <a name="parameters"></a>매개 변수  
 `byteOffset`  
 값을 설정 해야 하는 버퍼의 위치입니다.  
  
 `value`  
 설정할 값입니다.  
  
## <a name="remarks"></a>설명  
 보기의 끝을 넘어 작성할 수 하는 경우 이러한 메서드는 예외를 발생 시킵니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 DataView의 첫 번째 Int8를 설정 하는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setInt8(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]