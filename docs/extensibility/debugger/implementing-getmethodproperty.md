---
title: GetMethodProperty 구현 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- GetMethodProperty method
- IDebugExpressionEvaluator2 property
ms.assetid: 6305874f-a2c4-4432-834c-07530ea84bff
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e3ed7207237a20e4dadc1284aca2d6b41a671353
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="implementing-getmethodproperty"></a>GetMethodProperty 구현
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 Visual Studio 디버그 엔진 (DE) 호출 [GetDebugProperty](../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md), 호출 하 [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) 스택 프레임에 현재 메서드에 대 한 정보를 얻을 수 있습니다.  
  
 이 구현 `IDebugExpressionEvaluator::GetMethodProperty` 다음 작업을 수행 합니다.  
  
1.  호출 [GetContainerField](../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md)에 전달 하는 [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) 개체입니다. 기호 공급자 (SP)는 반환 된 [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) 지정 된 주소를 포함 하는 메서드를 나타내는입니다.  
  
2.  가져옵니다는 [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) 에서 `IDebugContainerField`합니다.  
  
3.  클래스를 인스턴스화하며 (호출 `CFieldProperty` 이 예에서) 구현 하는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스를 포함는 `IDebugMethodField` SP에서 반환 된 개체  
  
4.  반환 된 `IDebugProperty2` 에서 인터페이스는 `CFieldProperty` 개체입니다.  
  
## <a name="managed-code"></a>관리 코드  
 이 예의 구현을 보여 줍니다. `IDebugExpressionEvaluator::GetMethodProperty` 관리 코드에서.  
  
```csharp  
namespace EEMC  
{  
    [GuidAttribute("462D4A3D-B257-4AEE-97CD-5918C7531757")]  
    public class EEMCClass : IDebugExpressionEvaluator  
    {  
        public HRESULT GetMethodProperty(  
                IDebugSymbolProvider symbolProvider,  
                IDebugAddress        address,  
                IDebugBinder         binder,  
                int                  includeHiddenLocals,  
            out IDebugProperty2      property)   
        {  
            IDebugContainerField containerField = null;  
            IDebugMethodField methodField       = null;  
            property = null;  
  
            // Get the containing method field.  
            symbolProvider.GetContainerField(address, out containerField);  
            methodField = (IDebugMethodField) containerField;  
  
            // Return the property of method field.  
            property = new CFieldProperty(symbolProvider, address, binder, methodField);  
            return COM.S_OK;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>비관리 코드  
 이 예의 구현을 보여 줍니다. `IDebugExpressionEvaluator::GetMethodProperty` 비관리 코드에서.  
  
```  
[CPP]  
STDMETHODIMP CExpressionEvaluator::GetMethodProperty(  
        in IDebugSymbolProvider *pprovider,  
        in IDebugAddress        *paddress,  
        in IDebugBinder         *pbinder,  
        in BOOL                  includeHiddenLocals,  
        out IDebugProperty2    **ppproperty  
    )  
{  
    if (pprovider == NULL)  
        return E_INVALIDARG;  
  
    if (ppproperty == NULL)  
        return E_INVALIDARG;  
    else  
        *ppproperty = 0;  
  
    HRESULT hr;  
    IDebugContainerField* pcontainer = NULL;  
  
    hr = pprovider->GetContainerField(paddress, &pcontainer);  
    if (FAILED(hr))  
        return hr;  
  
    IDebugMethodField*    pmethod    = NULL;  
    hr = pcontainer->QueryInterface( IID_IDebugMethodField,  
            reinterpret_cast<void**>(&pmethod));  
    pcontainer->Release();  
    if (FAILED(hr))  
        return hr;  
  
    CFieldProperty* pfieldProperty = new CFieldProperty( pprovider,  
                                                         paddress,  
                                                         pbinder,  
                                                         pmethod );  
    pmethod->Release();  
    if (!pfieldProperty)  
        return E_OUTOFMEMORY;  
  
    hr = pfieldProperty->Init();  
    if (FAILED(hr))  
    {  
        pfieldProperty->Release();  
        return hr;  
    }  
  
    hr = pfieldProperty->QueryInterface( IID_IDebugProperty2,  
            reinterpret_cast<void**>(ppproperty));  
    pfieldProperty->Release();  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [로컬 항목의 샘플 구현](../../extensibility/debugger/sample-implementation-of-locals.md)