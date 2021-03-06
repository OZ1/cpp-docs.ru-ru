---
title: "Справочник (C++ AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
dev_langs:
- C++
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 005b25fa44f229e9d9e2b59b0a20c41a661ed6c3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="reference-c-amp"></a>Справочник (C++ AMP)
В этом разделе содержатся справочные сведения для среды выполнения C++ Accelerated Massive Parallelism (C++ AMP).  
  
> [!NOTE]
>  В стандарте языка C++ использование идентификаторов, начинающихся с символа подчеркивания (`_`), зарезервировано для таких реализаций, как библиотеки. Не используйте в коде имена, начинающиеся с символа подчеркивания. Поведение элементов кода, имена которых соответствуют этому соглашению, не гарантируется и может быть изменено в будущем. По этим причинам такие элементы кода исключены из этой документации.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)  
 Предоставляет классы и функции, которые позволяют ускорение кода C++ на оборудовании параллельных данных.  
  
 [Пространство имен Concurrency::direct3d](concurrency-direct3d-namespace.md)  
 Предоставляет функции, поддерживающие взаимодействие D3D. Обеспечивает эффективное использование ресурсов D3D для вычислений в коде AMP и использование ресурсов, созданные в AMP в коде D3D, не создавая промежуточные резервированием. C++ AMP можно использовать для добавочного ускорения разделах ресурсоемких приложений DirectX и использовать этот API D3D в формируемые AMP вычисления данных.  
  
 [Пространство имен Concurrency::fast_math](concurrency-fast-math-namespace.md)  
 Функции в `fast_math` пространства имен не удовлетворяют требованиям C99. Имеются только одинарной точности версии каждой функции. Эти функции используют встроенные функции DirectX, которые работают быстрее, чем соответствующие функции в `precise_math` пространства имен и не требуют расширенной поддержки двойной точности на сочетания клавиш, но они являются менее точными. Существуют две версии каждой функции для источника уровня совместимости с кодом C99; обе версии принимают и возвращают значения одинарной точности.  
  
 [Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)  
 Предоставляет типы и функции, предназначенные для программирования графики.  
  
 [Пространство имен Concurrency::precise_math](concurrency-precise-math-namespace.md)  
 Функции в `precise_math` пространства имен являются совместимыми C99. Числа одинарной точности и двойной точности версии каждой функции включены. Эти функции — Сюда входят функции одиночной точности, требуется расширенная поддержка двойной точности на сочетания клавиш.  
  
## <a name="related-sections"></a>Связанные разделы  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 C++ AMP ускоряет выполнение кода C++, используя преимущества оборудования параллельными данными, часто присутствует в качестве графического процессора (GPU) на выделенной видеокарте.





