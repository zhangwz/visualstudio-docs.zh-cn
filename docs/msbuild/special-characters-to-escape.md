---
title: 要转义的特殊字符 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- special characters to escape
- msbuild, special characters to escape
ms.assetid: 5b5172c3-41e4-4f38-a16f-2aeac831a5fc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3b9c73def1870e09a43485ddd423ee9d3000bbee
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "65846228"
---
# <a name="special-characters-to-escape"></a>要转义的特殊字符
仅当特殊字符在使用它们的上下文中具有特殊意义时，才必须对特殊字符进行转义。 例如，星号 (*) 仅在项定义的“Include”和“Exclude”属性对 <xref:Microsoft.Build.Tasks.CreateItem> 的调用中是特殊字符。 在所有其他情况下，星号都将被视为原义星号。 虽然不需要转义项目文件中无处不在的星号，但做也没有坏处。

 使用表示法 %\<xx> 替换特殊字符，其中 \<xx> 表示 ASCII 字符的十六进制值。 例如，如需将星号 (*) 用作原义字符，可使用值 `%2A`。

 要转义的特殊字符的完整列表紧跟：

|字符|说明|
|---------------|-----------------|
|%|百分号，用于引用元数据。|
|$|美元符号，用于引用属性。|
|@|At 符号，用于引用项列表。|
|(|左圆括号，用在列表中。|
|)|右圆括号，用在列表中。|
|;|分号，列表分隔符。|
|?|问号，描述项的“Include/Exclude”节中的文件规范时使用的通配符。|
|*|星号，描述项的“Include/Exclude”节中的文件规范时使用的通配符。|

## <a name="see-also"></a>请参阅
- [如何：转义 MSBuild 中的特殊字符](../msbuild/how-to-escape-special-characters-in-msbuild.md)
- [MSBuild 参考](../msbuild/msbuild-reference.md)
