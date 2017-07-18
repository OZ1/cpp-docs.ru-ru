---
title: "Общие правила и ограничения | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Общие правила и ограничения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Microsoft  
  
-   Если функция или объект объявлен без атрибута **dllimport** или `dllexport`, то они считаются частью интерфейса DLL.  Поэтому объявление функции или объекта должно находиться в том же самом модуле или в другом модуле той же программы.  Для того чтобы включить функцию или объект в интерфейс DLL, необходимо в другом модуле объявить определение функции или объекта, указав для них атрибут `dllexport`.  В противном случае возникает ошибка компоновщика.  
  
     При объявлении функции или объекта с атрибутом `dllexport` его определение должно отображаться в каком\-либо модуле той же программы.  В противном случае возникает ошибка компоновщика.  
  
-   Если в одном и том же модуле содержатся объявления одной и той же функции или объекта с атрибутами **dllimport** и `dllexport`, то атрибут `dllexport` имеет приоритет перед **dllimport**.  Однако компилятор создает предупреждение.  Например:  
  
    ```  
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   В C\+\+ можно инициализировать глобально объявленный или статический указатель локальных данных либо выполнить инициализацию с помощью адреса объекта данных, объявленного с атрибутом **dllimport**, в результате чего создается ошибка в языке С.  Кроме того, можно инициализировать статический указатель локальной функции с использованием адреса функции, объявленной с атрибутом **dllimport**.  В C такое присваивание задает указатель на адрес преобразователя импорта библиотеки DLL \(заглушки кода, передающей контроль функции\), а не адрес функции.  В C\+\+ оно задает указатель на адрес функции.  Например:  
  
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
  
     Однако поскольку программа с атрибутом `dllexport` в объявлении объекта должна содержать определение этого объекта где\-либо в программе, указатель на глобальную или локальную статическую функцию можно инициализировать с адресом функции с атрибутом `dllexport`.  Аналогичным образом указатель на глобальные или локальные статические данные можно инициализировать с адресом объекта данных с атрибутом `dllexport`.  Например, следующий код не создает ошибки в C или C\+\+:  
  
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
  
-   Из\-за изменений в поведении, реализованном в Visual C\+\+ .NET с целью сделать приложение `dllexport` более консистентным в отношении регулярных классов и специализаций шаблонов классов, при применении `dllexport` к регулярному классу, имеющему базовый класс, который не помечен как `dllexport`, компилятор создает ошибку C4275.  
  
     Компилятор создает то же самое предупреждение, если базовый класс является специализацией шаблона классов.  Чтобы обойти это поведение, пометьте базовый класс `dllexport`.  Проблема при специализации шаблона класса заключается в том, где разместить **\_\_declspec\(dllexport\)**; помечать шаблон классов не разрешается.  Вместо этого необходимо явно создать экземпляр шаблона классов и пометить это явное создание экземпляра с помощью `dllexport`.  Например:  
  
    ```  
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     Этот обходной путь завершается сбоем, если аргумент шаблона — это производный класс.  Например:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     Поскольку это общая схема для шаблонов, компилятор изменил семантику `dllexport` при применении к классу, имеющему несколько базовых классов, и в случае, когда один или более базовых классов является специализацией шаблона классов.  В этом случае компилятор неявно применяет `dllexport` к специализациям шаблонов классов.  В Visual C\+\+ .NET пользователь может выполнить следующие действия и не получить предупреждение:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## См. также  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)