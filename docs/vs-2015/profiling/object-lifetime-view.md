---
title: “对象生存期”视图 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.objectlifetime
helpviewer_keywords:
- lifetime, objects
- Objects Lifetime view
- profiling tools reports, Lifetime view
- performance reports, objects lifetime view
- profiling tools, Lifetime view
ms.assetid: d0501fdd-4b3a-4e74-b6ac-51d950a2e15b
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ef216c1220cbfda37da579d3ea2dfdd32837ab75
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2019
ms.locfileid: "54833682"
---
# <a name="object-lifetime-view"></a>“对象生存期”视图
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在“性能会话”属性页上选中“还收集 .NET 对象的生存期数据”时，可以使用“对象生存期”视图。  
  
 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 的垃圾回收器负责管理应用程序的内存分配和释放。 为优化垃圾回收器的性能，将托管堆分为三代：第 0 代、第 1 代和第 2 代。 运行时的垃圾回收器将新对象存储在第 0 代中。 未回收的对象将会升级并存储在第 1 代和第 2 代中。  
  
 垃圾回收器通过释放整个代的对象来回收内存。 对于被分析应用程序所创建的对象，“对象生存期”视图显示对象的数量和大小，以及回收对象时属于哪一代。  
  
## <a name="general"></a>常规  
  
|列|说明​​|  
|------------|-----------------|  
|**类名**|所分配类型的类名。|  
|**进程 ID**|分析运行的进程 ID。|  
|**进程名**|进程的名称。|  
|**模块名**|函数所在模块的名称。|  
|**模块路径**|函数所在模块的路径。|  
  
## <a name="instance-data"></a>实例数据  
 实例数据指示在分析运行期间，所创建的该类型的对象数，以及垃圾回收器解除分配的对象所属的代。  
  
|列|说明​​|  
|------------|-----------------|  
|**实例**|此类型对象的分配数。|  
|**总实例数百分比**|在分析运行期间进行的分配总数的百分比。|  
|**已收集的第 0 代实例数**|在垃圾回收算法的第 0 代中，已解除分配的类型实例数。|  
|**已收集的第 1 代实例数**|在垃圾回收算法的第 1 代中，已解除分配的类型实例数。|  
|**已收集的第 2 代实例数**|在垃圾回收算法的第 2 代中，已解除分配的类型实例数。|  
|**最终仍活动的实例数**|至分析运行结束时，仍未解除分配的类型实例数。|  
  
## <a name="size-byte-data"></a>大小（字节）数据  
 大小（字节）数据指示在分析运行期间，所创建的该类型对象的大小，以及解除对象分配时所属的每个代中回收的内存量。  
  
|列|说明​​|  
|------------|-----------------|  
|**已分配的总字节数**|此类型所有实例的总字节数。|  
|**总字节数百分比**|在分析运行期间，为此类型的实例分配的总字节数的百分比。|  
|**已收集的第 0 代字节数**|在垃圾回收算法的第 0 代中，已解除分配的类型实例的大小。|  
|**已收集的第 1 代字节数**|在垃圾回收算法的第 1 代中，已解除分配的类型实例的大小。|  
|**已收集的第 2 代字节数**|在垃圾回收算法的第 2 代中，已解除分配的类型实例的大小。|  
  
## <a name="large-object-heap-data"></a>大型对象堆数据  
 .NET 内存分配器在标准托管堆以外的位置管理大型对象。 大型对象堆数据指示在此位置管理的类型对象的数目和大小。  
  
|列|说明​​|  
|------------|-----------------|  
|**已收集的大型对象堆实例数**|位于大型对象堆中，且在分析运行期间收集的此类型实例的数目。|  
|**已收集的大型对象堆字节数**|位于大型对象堆中，且在分析运行期间收集的此类型实例的大小（以字节为单位）。|  
  
## <a name="see-also"></a>请参阅  
 [.NET 内存数据视图](../profiling/dotnet-memory-data-views.md)
