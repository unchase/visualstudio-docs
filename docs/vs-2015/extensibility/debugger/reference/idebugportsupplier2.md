---
title: "IDebugPortSupplier2 | Microsoft Docs"
ms.custom: ""
ms.date: 11/15/2016
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier2"
helpviewer_keywords: 
  - "IDebugPortSupplier2 interface"
ms.assetid: 37067324-2ea6-4a01-8829-a6e9c7a70068
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugPortSupplier2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

This interface supplies ports to the session debug manager (SDM).  
  
## Syntax  
  
```  
IDebugPortSupplier2 : IUnknown  
```  
  
## Notes for Implementers  
 A custom port supplier implements this interface to represent a port supplier.  
  
## Notes for Callers  
 A call to `CoCreateInstance` with a port supplier's `GUID` returns this interface (this is the typical way to obtain this interface). For example:  
  
```cpp#  
IDebugPortSupplier2 *GetPortSupplier(GUID *pPortSupplierGuid)  
{  
    IDebugPortSupplier2 *pPS = NULL;  
    if (pPortSupplierGuid != NULL) {  
        CComPtr<IDebugPortSupplier2> spPortSupplier;  
        spPortSupplier.CoCreateInstance(*pPortSupplierGuid);  
        if (spPortSupplier != NULL) {  
            pPS = spPortSupplier.Detach();  
        }  
    }  
    return (pPS);  
}  
```  
  
 A call to [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md) returns this interface, representing the current port supplier being used by [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md) returns this interface, representing the port supplier that created the port.  
  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md) represents a list of `IDebugPortSupplier` interfaces (the `IEnumDebugPortSuppliers` interface is obtained from [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md), representing all of the port suppliers registered with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]).  
  
 A debug engine typically does not interact with a port supplier.  
  
## Methods in Vtable Order  
 The following table shows the methods of `IDebugPortSupplier2`.  
  
|Method|Description|  
|------------|-----------------|  
|[GetPortSupplierName](../../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md)|Gets the port supplier name.|  
|[GetPortSupplierId](../../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)|Gets the port supplier identifier.|  
|[GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md)|Gets a port from a port supplier.|  
|[EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)|Enumerates the ports that already exist.|  
|[CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)|Verifies that a port supplier supports adding new ports.|  
|[AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)|Adds a port.|  
|[RemovePort](../../../extensibility/debugger/reference/idebugportsupplier2-removeport.md)|Removes a port.|  
  
## Remarks  
 A port supplier can identify itself by name and ID, add and remove ports, and enumerate all ports that the port supplier provides.  
  
## Requirements  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## See Also  
 [Core Interfaces](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)   
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)
