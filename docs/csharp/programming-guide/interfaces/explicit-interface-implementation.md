---
title: 显式接口实现 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ac90726fd50f104d1b9251d4f9b097b721ea5e7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75701753"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>显式接口实现（C# 编程指南）
如果一个[类](../../language-reference/keywords/class.md)实现的两个接口包含签名相同的成员，则在该类上实现此成员会导致这两个接口将此成员用作其实现。 如下示例中，所有对 `Paint` 的调用皆调用同一方法。以下的示例对类型进行定义：
  
[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

以下的示例调用这些方法：

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

但是，如果两个[接口](../../language-reference/keywords/interface.md)成员不执行同一功能，则会导致其中一个接口或两个接口的实现不正确。 创建仅通过接口调用且特定于该接口的类成员，则有可能显式实现接口成员。 这可通过使用接口名称和句点命名类成员来完成。 例如：  
  
[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]
  
类成员 `IControl.Paint` 仅通过 `IControl` 接口可用，`ISurface.Paint` 仅通过 `ISurface` 可用。 这两个方法实现相互独立，两者均不可直接在类上使用。 例如：  
  
[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]
  
显式实现还用于处理两个接口分别声明名称相同的不同成员（例如属性和方法）的情况。 若要实现两个接口，类必须对属性 P 或方法 P 使用显式实现，或对二者同时使用，从而避免编译器错误。 例如：
  
[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]
  
如果一个类从一个接口那里继承了方法实现，那么该方法就只能通过对接口类型的引用进行访问。继承的成员不会被作为类的公共成员。以下的示例为接口方法定义了默认实现：

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

以下的示例调用默认实现：

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

任何实现了`IControl`接口的类都可以覆盖默认的`Paint`方法，可以作为一个公共方法，或者显式接口实现。
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../index.md)
- [类和结构](../classes-and-structs/index.md)
- [接口](./index.md)
- [继承](../classes-and-structs/inheritance.md)
