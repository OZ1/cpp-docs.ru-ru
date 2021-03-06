---
title: Queue::Queue (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::queue::queue
dev_langs:
- C++
helpviewer_keywords:
- queue member [STL/CLR]
ms.assetid: 6106c07f-d5eb-4f0b-82df-ee4e2e751047
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d6c4b24ad40bf19b7a20aafcfa2d02fb6490fed1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="queuequeue-stlclr"></a>queue::queue (STL/CLR)
Создает объект контейнера адаптера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
queue();  
queue(queue<Value, Container>% right);  
queue(queue<Value, Container>^ right);  
explicit queue(container_type% wrapped);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Копируемый объект.  
  
 в оболочку  
 Упакованное контейнер для использования.  
  
## <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `queue();`  
  
 Создает оболочку пустой контейнер. Используется, чтобы указать пустую начальную управляемую последовательность.  
  
 Конструктор:  
  
 `queue(queue<Value, Container>% right);`  
  
 Создает оболочку контейнер, который является копией `right.get_container()`. Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объект очереди `right`.  
  
 Конструктор:  
  
 `queue(queue<Value, Container>^ right);`  
  
 Создает оболочку контейнер, который является копией `right->get_container()`. Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объект очереди `*right`.  
  
 Конструктор:  
  
 `explicit queue(container_type wrapped);`  
  
 использует существующий контейнер `wrapped` как изолированного контейнера. Используется для создания очереди из существующего контейнера.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/list>   
  
typedef cliext::queue<wchar_t> Myqueue;   
typedef cliext::list<wchar_t> Mylist;   
typedef cliext::queue<wchar_t, Mylist> Myqueue_list;   
int main()   
    {   
// construct an empty container   
    Myqueue c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Mylist v2(5, L'x');   
    Myqueue_list c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myqueue_list c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Myqueue_list c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 x x x x x  
 x x x x x  
 x x x x x  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Queue::Assign (STL/CLR)](../dotnet/queue-assign-stl-clr.md)   
 [Queue::generic_container (STL/CLR)](../dotnet/queue-generic-container-stl-clr.md)   
 [queue::operator= (STL/CLR)](../dotnet/queue-operator-assign-stl-clr.md)