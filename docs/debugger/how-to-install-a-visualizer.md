---
title: 如何：安装可视化工具 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b9b09bc837cae4eaad2c0dbcb2bb82a7daa248eb
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63389325"
---
# <a name="how-to-install-a-visualizer"></a>如何：安装可视化工具
创建了可视化工具后，您还必须安装该可视化工具，这样您才可在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中使用它。 安装可视化工具是个简单的过程。

> [!NOTE]
> 在 UWP 应用中，仅在标准文本支持 HTML、 XML 和 JSON 可视化工具。 不支持自定义（用户创建的）可视化工具。

### <a name="to-install-a-visualizer"></a>安装可视化工具

1. 查找包含已创建的可视化工具的 DLL。

2. 将 DLL 复制到下列位置之一：

    - VisualStudioInstallPath `\Common7\Packages\Debugger\Visualizers`

    - `My Documents\` VisualStudioVersion `\Visualizers`

3. 若要使用托管可视化工具进行远程调试，请将 DLL 复制到远程计算机上的同一路径。

4. 重新启动调试会话。

## <a name="see-also"></a>请参阅
- [创建自定义可视化工具](../debugger/create-custom-visualizers-of-data.md)
- [如何：编写可视化工具](/visualstudio/debugger/create-custom-visualizers-of-data)