---
title: "Пошаговое руководство: Реализация фьючерсов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 119969860f031acbc2f1764a34a456d2e8a16437
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-implementing-futures"></a>Пошаговое руководство. Реализация фьючерсов
В этом разделе показано, как реализовать фьючерсов в приложении. Разделе показано, как объединить существующие функциональные возможности в среде выполнения с параллелизмом в формат, что делает больше.  
  
> [!IMPORTANT]
>  В этом разделе рассматривается понятие фьючерсов для демонстрационных целей. Мы рекомендуем использовать [std::future](../../standard-library/future-class.md) или [concurrency::task](../../parallel/concrt/reference/task-class.md) Если требуется асинхронная задача, которая вычисляет значение для последующего использования.  
  
 Объект *задачи* является вычисление, которое можно разложить на дополнительные, более мелкие вычисления. Объект *будущих* — это асинхронная задача, которая вычисляет значение для последующего использования.  
  
 Для реализации фьючерсов в этом разделе определяются `async_future` класса. `async_future` Класс использует эти компоненты среды выполнения с параллелизмом: [concurrency::task_group](reference/task-group-class.md) класса и [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) класса. `async_future` Класс использует `task_group` класса для асинхронного вычисления значения и `single_assignment` класса для хранения результата вычисления. Конструктор `async_future` класса принимает рабочую функцию, которая вычисляет результат, и `get` метод возвращает результат.  
  
### <a name="to-implement-the-asyncfuture-class"></a>Реализация класса async_future  
  
1.  Объявите шаблонный класс с именем `async_future` , параметризованный по типу результирующего вычисления. Добавить `public` и `private` разделы к этому классу.  
  
 [!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]  
  
2.  В `private` раздел `async_future` объявите `task_group` и `single_assignment` элемента данных.  
  
 [!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]  
  

3.  В `public` раздел `async_future` класса, реализуйте конструктор. Конструктор — это шаблон, который параметризуется по рабочую функцию, которая вычисляет результат. Конструктор асинхронно выполняет рабочую функцию в `task_group` элемента данных и использует [concurrency::send](reference/concurrency-namespace-functions.md#send) функцию для записи результата в `single_assignment` элемент данных.  
  
 [!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]  
  
4.  В `public` раздел `async_future` , следует реализовать деструктор. Деструктор ожидает завершения выполнения задачи.  
  
 [!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]  
  

5.  В `public` раздел `async_future` , следует реализовать `get` метод. Этот метод использует [concurrency::receive](reference/concurrency-namespace-functions.md#receive) функция для извлечения результата рабочей функции.  

  
 [!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем примере показано полное `async_future` класса и пример его использования. `wmain` Функция создает объект std::[вектор](../../standard-library/vector-class.md) , содержащий 10000 случайных целых чисел. Затем он использует `async_future` объектов, чтобы найти наименьшее и наибольшее значения, содержащиеся в `vector` объекта.  
  
### <a name="code"></a>Код  
 [!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_6.cpp)]  
  
### <a name="comments"></a>Комментарии  
 В этом примере выводятся следующие данные:  
  
```Output  
smallest: 0  
largest:  9999  
average:  4981  
```  
  
 В этом примере `async_future::get` метод для получения результатов вычисления. `async_future::get` Метод ожидает завершения, если вычисление по-прежнему активна вычисления.  
  
## <a name="robust-programming"></a>Отказоустойчивость  


 Чтобы расширить `async_future` класса, чтобы обрабатывать исключения, вызываемые рабочей функцией, измените `async_future::get` метод, вызываемый [Concurrency::task_group:: wait](reference/task-group-class.md#wait) метод. `task_group::wait` Метод создает все исключения, которые были созданы в рабочей функции.  


  
 В следующем примере показано измененная версия `async_future` класса. `wmain` Функция использует `try` - `catch` блок для печати результат `async_future` объекта или для печати значения исключение, которое создается в рабочей функции.  
  
 [!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]  
  
 В этом примере выводятся следующие данные:  
  
```Output  
caught exception: error  
```  
  
 Дополнительные сведения о модели обработки исключений в среде выполнения с параллелизмом см. в разделе [обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `futures.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe futures.cpp/EHsc**  
  
## <a name="see-also"></a>См. также  
 [Пошаговые руководства для среды выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Класс task_group](reference/task-group-class.md)   
 [Класс single_assignment](../../parallel/concrt/reference/single-assignment-class.md)
