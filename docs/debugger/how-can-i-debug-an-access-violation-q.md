---
title: 调试 c + + 访问冲突 | Microsoft Docs
ms.custom: seodec18
ms.date: 02/05/2019
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 9311d754-0ce9-4145-b147-88b6ca77ba63
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 2be6c13e2a3c83d31540399dd3387addb08e8686
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62895125"
---
# <a name="how-can-i-debug-a-c-access-violation"></a>如何调试C++访问冲突？

## <a name="problem-description"></a>问题描述

我的程序产生了访问冲突。 如何调试它？

## <a name="solution"></a>解决方案

如果在取消引用多个指针的代码行上出现访问冲突，则可能很难辨别引起访问冲突的指针。 从 Visual Studio 2015 Update 1 起，异常对话框现对导致访问冲突的指针进行显式命名。

例如，以下代码中，将出现访问冲突：

```C++
#include <iostream>
using namespace std;

class ClassC {
public:
  void printHello() {
    cout << "hello world";
  }
};

class ClassB {
public:
  ClassC* C;
  ClassB() {
    C = new ClassC();
  }
};

class ClassA {
public:
  ClassB* B;
  ClassA() {
    // Uncomment to fix
    // B = new ClassB();
  }
};

int main() {
  ClassA* A = new ClassA();
  A->B->C->printHello();

}
```

如果在 Visual Studio 2015 Update 1 中运行此代码，你将看到以下异常对话框：

![AccessViolationCPlus](../debugger/media/accessviolationcplus.png "AccessViolationCPlus")

如果无法确定该指针为何导致访问冲突，请对代码进行跟踪，以确保导致该问题的指针被正确处理。  如果它作为参数传递，请确保正确传递且未意外创建[浅表副本](http://stackoverflow.com/questions/184710/what-is-the-difference-between-a-deep-copy-and-a-shallow-copy)。 然后为有问题的指针创建一个数据断点，以确保它没有在程序的其他地方被修改，从而验证这些值没有在程序的某个地方被无意地更改。 有关数据断点的详细信息，请参阅 [使用断点](../debugger/using-breakpoints.md)中的数据断点部分。

## <a name="see-also"></a>请参阅
- [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)