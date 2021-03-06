---
title: 常量 （调试接口访问 SDK） |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- constants, DIA SDK
- DIA SDK, constants
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 931e1ab46793a5ff7e0434949330eaf4dbc820e8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58936276"
---
# <a name="constants-debug-interface-access-sdk"></a>常量（调试接口访问 SDK）
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

这些字符串常量可用于标识程序调试数据库 (PDB) 文件通过 DIA SDK 的各个部分。  
  
## <a name="constants"></a>常量  
 以下被声明为 C/c + + 宏。  
  
|宏|值|  
|-----------|-----------|  
|`DiaTable_Symbols`|L"符号"|  
|`DiaTable_Sections`|L"Section"|  
|`DiaTable_SrcFiles`|L"SourceFiles"|  
|`DiaTable_LineNums`|L"LineNumbers"|  
|`DiaTable_SegMap`|L"SegmentMap"|  
|`DiaTable_Dbg`|L"Dbg"|  
|`DiaTable_InjSrc`|L"InjectedSource"|  
|`DiaTable_FrameData`|L"FrameData"|  
  
## <a name="example"></a>示例  
 下面是示例使用这些符号之一：  
  
```cpp#  
HRESULT GetSymbolTable(IDiaEnumTables *pEnumTables, IDiaTable **pTable)  
{  
    HRESULT hr;  
    VARIANT var;  
    var.vt      = VT_BSTR;  
    var.bstrVal = SysAllocString( DiaTable_Symbols );  
    hr = pEnumTables->Item( var, pTable );  
    return(hr);  
}  
```  
  
## <a name="requirements"></a>要求  
 标头： dia2.h  
  
## <a name="see-also"></a>请参阅  
 [参考](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)   
 [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [接口（调试接口访问 SDK）](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)
