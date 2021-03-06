---
title: ReadLinesFromFile 任务 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ReadLinesFromFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ReadLinesFromFile task
- ReadLinesFromFile task [MSBuild]
ms.assetid: a18af929-b53a-4d9e-b7bf-e3d3737ee85f
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6783b3e20c004e4270876dd8ee6b8b574a810d66
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2019
ms.locfileid: "59648973"
---
# <a name="readlinesfromfile-task"></a>ReadLinesFromFile 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

从文本文件读取项列表。  
  
## <a name="parameters"></a>参数  
 下表描述了 `ReadLinesFromFile` 任务的参数。  
  
|参数|说明|  
|---------------|-----------------|  
|`File`|必选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定要读取的文件。 文件的每一行都必须有一项。|  
|`Lines`|可选的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 输出参数。<br /><br /> 包含从文件读取的行。|  
  
## <a name="remarks"></a>备注  
 除上面列出的参数外，此任务还从 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数，后者自身继承自 <xref:Microsoft.Build.Utilities.Task> 类。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="example"></a>示例  
 以下示例使用 `ReadLinesFromFile` 任务，从文本文件中的列表创建项。 从该文件读取的项均存储在 `ItemsFromFile` 项集合中。  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyTextFile Include="Items.txt"/>  
    </ItemGroup>  
  
    <Target Name="ReadFromFile">  
        <ReadLinesFromFile  
            File="@(MyTextFile)" >  
            <Output  
                TaskParameter="Lines"  
                ItemName="ItemsFromFile"/>  
        </ReadLinesFromFile>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>请参阅  
 [任务参考](../msbuild/msbuild-task-reference.md)   
 [MSBuild 概念](../msbuild/msbuild-concepts.md)   
 [任务](../msbuild/msbuild-tasks.md)
