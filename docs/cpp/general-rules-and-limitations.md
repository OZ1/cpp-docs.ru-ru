---
title: Общие правила и ограничения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51f92844e993671a3423c04523ccf4e03f7f7e48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="general-rules-and-limitations"></a>Общие правила и ограничения
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
  
-   Если объявить функцию или объект без **dllimport** или `dllexport` атрибут, функция или объект не является частью интерфейса DLL. Поэтому объявление функции или объекта должно находиться в том же самом модуле или в другом модуле той же программы. Для того чтобы включить функцию или объект в интерфейс DLL, необходимо в другом модуле объявить определение функции или объекта, указав для них атрибут `dllexport`. В противном случае возникает ошибка компоновщика.  
  
     При объявлении функции или объекта с атрибутом `dllexport` его определение должно отображаться в каком-либо модуле той же программы. В противном случае возникает ошибка компоновщика.  
  
-   Если содержит один модуль в программе одновременно **dllimport** и `dllexport` объявления для этой же функции или объекта, `dllexport` атрибут имеет приоритет над **dllimport** атрибут. Однако компилятор создает предупреждение. Пример:  
  
    ```  
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   В C++ можно инициализировать глобально объявленный или статический локальных данных указатель или с адресом объекта данных, объявленного с **dllimport** атрибут, который приводит к возникновению ошибки на языке C. Кроме того, можно инициализировать статический указатель локальной функции с адресом функции, объявленной с **dllimport** атрибута. В C такое присваивание задает указатель на адрес преобразователя импорта библиотеки DLL (заглушки кода, передающей контроль функции), а не адрес функции. В C++ оно задает указатель на адрес функции. Пример:  
  
    ```  
    __declspec( dllimport ) void func1( void );  
    __declspec( dllimport ) int i;  
  
    int *pi = &i;                             // Error in C  
    static void ( *pf )( void ) = &func1;     // Address of thunk in C,  
                                              // function in C++  
  
    void func2()  
    {  
       static int *pi = &i;                  // Error in C  
       static void ( *pf )( void ) = &func1; // Address of thunk in C,  
                                             // function in C++  
    }  
    ```  
  
     Однако поскольку программа с атрибутом `dllexport` в объявлении объекта должна содержать определение этого объекта где-либо в программе, указатель на глобальную или локальную статическую функцию можно инициализировать с адресом функции с атрибутом `dllexport`. Аналогичным образом указатель на глобальные или локальные статические данные можно инициализировать с адресом объекта данных с атрибутом `dllexport`. Например, следующий код не создает ошибки в C или C++:  
  
    ```  
    __declspec( dllexport ) void func1( void );  
    __declspec( dllexport ) int i;  
  
    int *pi = &i;                              // Okay  
    static void ( *pf )( void ) = &func1;      // Okay  
  
    void func2()  
    {  
        static int *pi = &i;                   // Okay  
        static void ( *pf )( void ) = &func1;  // Okay  
    }  
    ```  
  
-   Если применить `dllexport` к регулярному классу, имеющим базового класса, который не помечен как `dllexport`, компилятор создает ошибку C4275.  
  
     Компилятор создает то же самое предупреждение, если базовый класс является специализацией шаблона классов. Чтобы обойти это поведение, пометьте базовый класс `dllexport`. Проблемой в специализации шаблона класса является размещение **__declspec(dllexport)**; нельзя пометить шаблона класса. Вместо этого необходимо явно создать экземпляр шаблона классов и пометить это явное создание экземпляра с помощью `dllexport`. Пример:  
  
    ```  
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     Этот обходной путь завершается сбоем, если аргумент шаблона — это производный класс. Пример:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     Поскольку это общая схема для шаблонов, компилятор изменил семантику `dllexport` при применении к классу, имеющему несколько базовых классов, и в случае, когда один или более базовых классов является специализацией шаблона классов. В этом случае компилятор неявно применяет `dllexport` к специализациям шаблонов классов. Можно выполнить следующие и не получить предупреждение:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)