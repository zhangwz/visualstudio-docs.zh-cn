---
title: 代码分析问题疑难解答
ms.date: 11/04/2016
ms.topic: troubleshooting
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 936428b82e721a1df6003a4bb0eecefe5b696b4c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62825346"
---
# <a name="troubleshooting-code-analysis-issues"></a>代码分析问题疑难解答
本主题包含以下 Visual Studio 代码分析问题的疑难解答信息。

- [Visual Studio 2010 规则集中的更改未反映在以前的 Visual Studio 版本中](#ChildRuleSetChangesInPreviousVersions)

## <a name="ChildRuleSetChangesInPreviousVersions"></a>Visual Studio 2010 规则集中的更改未反映在以前的 Visual Studio 版本中
 在包含子规则集的 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] 中创建规则集时，对子规则集的更改不会应用到使用 Visual Studio 早期版本的计算机上的代码分析运行中。 若要解决此问题，必须强制执行对父规则集（即包含子规则集的规则集）的重写。

1. 打开 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] 中的父规则集。

2. 对规则集进行更改，例如添加或删除规则，然后保存。

3. 重新打开此规则集，撤消更改，然后再次保存。

## <a name="see-also"></a>请参阅

- [分析应用程序质量](../code-quality/code-analysis-for-managed-code-overview.md)
- [分析托管代码质量](../code-quality/code-analysis-for-managed-code-overview.md)
- [使用规则集对代码分析规则进行分组](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)