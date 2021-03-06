---
title: Несколько базовых классов | Документы Microsoft
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
helpviewer_keywords:
- base classes [C++], multiple
- derived classes [C++], multiple bases
- multiple inheritance, class declaration
- multiple base classes [C++]
ms.assetid: a30c69fe-401c-4a87-96a0-e0da70c7c740
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b765fabe8b83169353650286d05d02301dcb4807
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="multiple-base-classes"></a>Несколько базовых классов
Как описано в [множественное наследование](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca), класс может быть производным от более чем одного базового класса. В модели множественного наследования (где классы являются производными от более чем одного базового класса) базовые классы задаются с помощью *базового списка* элемента грамматики. Например, объявление класса для `CollectionOfBook`, производного от `Collection` и `Book`, можно указать следующим образом.  
  
```  
// deriv_MultipleBaseClasses.cpp  
// compile with: /LD  
class Collection {  
};  
class Book {};  
class CollectionOfBook : public Book, public Collection {  
    // New members  
};  
```  
  
 Порядок, в котором указываются базовые классы, не имеет значения, кроме некоторых случаев, когда вызываются конструкторы и деструкторы. В таких случаях порядок, в котором указываются базовые классы, влияет на следующее.  
  
-   Порядок, в котором конструктор выполняет инициализацию. Если код основан на том, что инициализация части `Book` `CollectionOfBook` должна выполняться перед частью `Collection`, порядок указания важен. Инициализация выполняется в классы указаны в порядке *базового списка*.  
  
-   Порядок, в котором вызываются деструкторы для очистки. Опять же, если определенная часть класса должна присутствовать, а другая часть должна быть удалена, порядок имеет значение. Деструкторы вызываются в порядке, обратном указанию классов в *базового списка*.  
  
    > [!NOTE]
    >  Порядок указания базовых классов может повлиять на структуру памяти класса. Не принимайте никаких программных решений на основе порядка базовых членов в памяти.  
  
 При указании *базового списка*, то же имя класса нельзя указывать более одного раза. Однако класс может стать косвенным базовым классом производного класса несколько раз.  
  
## <a name="virtual-base-classes"></a>Виртуальные базовые классы  
 Поскольку класс может несколько раз выступать как косвенный базовый класс к производному классу, в C++ имеется способ оптимизировать функционирование таких базовых классов. Виртуальные базовые классы позволяют экономить пространство и исключать неоднозначности в иерархиях классов, в которых используется множественное наследование.  
  
 Каждый невиртуальный объект содержит копию элементов данных, определенных в базовом классе. Такой повтор данных приводит к ненужному увеличению их объема. Кроме того, при каждой попытке обращения к элементам базового класса приходится указывать, какая именно их копия требуется.  
  
 Если базовый класс определен как виртуальный базовый класс, то он может несколько раз выступать как косвенный базовый класс без дублирования элементов данных. Единственная копия его элементов данных совместно используется всеми базовыми классами, которые используют его как виртуальный базовый класс.  
  
 При объявлении виртуального базового класса, **виртуальных** ключевое слово встречается в базовых списках производных классов.  
  
 Рассмотрим иерархию классов, представленную на следующем рисунке, на котором показана имитация графа Lunch-Line.  
  
 ![Граф имитации очереди](../cpp/media/vc38xp1.gif "vc38XP1")  
Смоделированный граф Lunch-Line  
  
 Как видно на рисунке, класс `Queue` является базовым для двух других классов: `CashierQueue` и `LunchQueue`. Однако когда эти два класса объединяются и образуют класс `LunchCashierQueue`, возникает следующая проблема: новый класс содержит два подчиненных объекта типа `Queue` — один из `CashierQueue`, а другой из `LunchQueue`. На следующем рисунке показана концептуальная структура памяти (фактическая структура памяти может быть оптимизирована).  
  
 ![Имитации &#45; объекта строки](../cpp/media/vc38xp2.gif "vc38XP2")  
Смоделированный объект Lunch-Line  
  
 Обратите внимание, что в объекте `Queue` имеется два подчиненных объекта `LunchCashierQueue`. В следующем коде содержится объявление `Queue` как виртуального базового класса:  
  
```  
// deriv_VirtualBaseClasses.cpp  
// compile with: /LD  
class Queue {};  
class CashierQueue : virtual public Queue {};  
class LunchQueue : virtual public Queue {};  
class LunchCashierQueue : public LunchQueue, public CashierQueue {};  
```  
  
 Благодаря ключевому слову `virtual` будет включена только одна копия подчиненного объекта `Queue` (см. следующий рисунок).  
  
 ![Имитации &#45; объекта строки, виртуальные базовые классы](../cpp/media/vc38xp3.gif "vc38XP3")  
Имитация объекта Lunch-Line с виртуальными базовыми классами  
  
 Класс может иметь как виртуальный, так и невиртуальный компонент заданного типа. Это происходит при условиях, которые иллюстрирует следующий рисунок.  
  
 ![Виртуальные и невиртуальные компоненты класса](../cpp/media/vc38xp4.gif "vc38XP4")  
Виртуальные и невиртуальные компоненты одного класса  
  
 На этом рисунке показано, что классы `CashierQueue` и `LunchQueue` используют `Queue` как виртуальный базовый класс. Однако `TakeoutQueue` определяет `Queue` в качестве базового класса, а не виртуального базового класса. Поэтому в `LunchTakeoutCashierQueue` имеется два подчиненных объекта типа `Queue`: один из пути наследования, включающего `LunchCashierQueue`, а второй из пути, включающего `TakeoutQueue`. Это показано на следующем рисунке.  
  
 ![Виртуальное и невиртуальное наследование в макете объектов](../cpp/media/vc38xp5.gif "vc38XP5")  
Структура объектов с наследованием от виртуальных и невиртуальных базовых классов  
  
> [!NOTE]
>  Наследование от виртуальных базовых классов позволяет существенно сократить объем данных по сравнению с наследованием от невиртуальных классов. Однако оно может породить дополнительные затраты на обработку.  
  
 Если производный класс переопределяет виртуальную функцию, которую он наследует от виртуального базового класса, и если конструктор или деструктор производного базового класса вызывает эту функцию при помощи указателя на виртуальный базовый класс, то компилятор может вставить дополнительные скрытые поля vtordisp в классы с виртуальными базовыми классами. Параметр компилятора /vd0 отключает добавление скрытого члена смещения конструктора или деструктора vtordisp. Параметр компилятора /vd1 (по умолчанию) разрешает добавлять их по мере необходимости. Добавление полей vtordisps следует отключать только в том случае, если точно известно, что все конструкторы и деструкторы классов вызывают виртуальные функции виртуально.  
  
 Параметр компилятора /vd действует на весь модуль компиляции. Используйте **vtordisp** pragma для предотвращения и затем повторно включите vtordisp-поля на основе класса, класс:  
  
```  
#pragma vtordisp( off )  
class GetReal : virtual public { ... };  
#pragma vtordisp( on )  
```  
  
## <a name="name-ambiguities"></a>Неоднозначность имен  
 Множественное наследование предоставляет возможность наследования имен по нескольким путям. Имена членов класса в этих путях не обязательно должны быть уникальными. Эти конфликты имен называются неоднозначностями.  
  
 Любое выражение, которое ссылается на член класса, должно иметь однозначную ссылку. В следующем примере показано, как появляются неоднозначности.  
  
```  
// deriv_NameAmbiguities.cpp  
// compile with: /LD  
// Declare two base classes, A and B.  
class A {  
public:  
    unsigned a;  
    unsigned b();  
};  
  
class B {  
public:  
    unsigned a();  // Note that class A also has a member "a"  
    int b();       //  and a member "b".  
    char c;  
};  
  
// Define class C as derived from A and B.  
class C : public A, public B {};  
```  
  
 При наличии указанных выше объявлений класса код, такой как указано ниже, является неоднозначным, поскольку не ясно, ссылается ли `b` на `b` в `A` или в `B`.  
  
```  
C *pc = new C;  
  
pc->b();  
```  
  
 Рассмотрим предыдущий пример. Поскольку имя `a` является членом обоих классов `A` и `B`, компилятор не может определить, какая переменная `a` обозначает функцию, которую необходимо вызвать. Доступ к члену неоднозначен, если он может ссылаться на несколько функций, объектов, типов или перечислителей.  
  
 Компилятор определяет неоднозначности, выполняя тесты в указанном порядке.  
  
1.  Если доступ к имени неоднозначен (как описано выше), создается сообщение об ошибке.  
  
2.  Если перегруженные функции однозначны, они разрешаются.
  
3.  Если доступ к имени нарушает разрешение доступа к членам, создается сообщение об ошибке. (Дополнительные сведения см. в разделе [управления доступом к членам](../cpp/member-access-control-cpp.md).)  
  
 Если выражение приводит к неоднозначности в результате наследования, его можно разрешить вручную, указав вместо данного имени имя класса. Чтобы выполнить компиляцию в предыдущем примере без неоднозначностей, можно использовать следующий код.  
  
```  
C *pc = new C;  
  
pc->B::a();  
```  
  
> [!NOTE]
>  Если объявлен `C`, могут возникнуть ошибки, если сослаться на `B` в области `C`. Однако ошибка не выдается, если не внести неквалифицированную ссылку на `B` в области `C`.  
  
### <a name="dominance"></a>Доминирование  
 Через граф наследования можно достичь несколько имен (функции, объекта или перечислителя). С невиртуальными базовыми классами такие случаи неоднозначны. Они также неоднозначны с виртуальными базовыми классами, если одно из имен не доминирует над другими.  
  
 То или иное имя доминирует над другим, если оно определено в обоих классах и один класс является производным от другого. Доминирующее имя — это имя в производном классе; оно используется тогда, когда в противном случае возникла бы неоднозначность, как показано в следующем примере.  
  
```  
// deriv_Dominance.cpp  
// compile with: /LD  
class A {  
public:  
    int a;  
};  
  
class B : public virtual A {  
public:  
    int a();  
};  
  
class C : public virtual A {};  
  
class D : public B, public C {  
public:  
    D() { a(); } // Not ambiguous. B::a() dominates A::a.  
};  
```  
  
### <a name="ambiguous-conversions"></a>Неоднозначные преобразования  
 Явные и неявные преобразования указателей и ссылок в типы класса могут приводить к неоднозначности. На следующем рисунке "Неоднозначное преобразование указателей в базовые классы" показано следующее:  
  
-   Объявление объекта типа `D`.  
  
-   В результате применения оператора взятия адреса (**&**) на этот объект. Обратите внимание, что оператор взятия адреса всегда возвращает базовый адрес объекта.  
  
-   Результат явного преобразования указателя, полученного с помощью оператора взятия адреса, в тип базового класса `A`. Обратите внимание, что приведение адреса объекта к типу `A*` не всегда предоставляет компилятору достаточно информации о том, какой из типов подобъектов типа `A` следует выбрать; в данном случае существуют два подобъекта.  
  
 ![Неоднозначное преобразование указателей в базовые классы](../cpp/media/vc38xt1.gif "vc38XT1")  
Неоднозначное преобразование указателей в базовые классы  
  
 Преобразование в тип `A*` (указатель на `A`) является неоднозначным, поскольку нет способа определить, какой подобъект типа `A` является правильным. Обратите внимание, что неоднозначности можно избежать, явно указав используемый подобъект, как показано ниже:  
  
```  
(A *)(B *)&d       // Use B subobject.  
(A *)(C *)&d       // Use C subobject.  
```  
  
### <a name="ambiguities-and-virtual-base-classes"></a>Неоднозначности и виртуальные базовые классы  
 Если используются виртуальные базовые классы, доступ к функциям, объектам, типам и перечислениям можно получить по путям множественного наследования. Поскольку существует только один экземпляр базового класса, неоднозначность при доступе к этим именам отсутствует.  
  
 На следующем рисунке показано составление объектов с использованием виртуального и невиртуального наследования.  
  
 ![Виртуальное ответвление и невиртуальное наследование](../cpp/media/vc38xr1.gif "vc38XR1")  
Виртуальное и  невиртуальное наследование  
  
 На этом рисунке доступ к любому члену класса `A` через невиртуальная базовые классы вызывает неоднозначность; у компилятора нет сведений, поясняющих, нужно ли использовать вложенный объект, связанный с `B`, или вложенный объект, связанный с `C`. Однако если `A` задано как виртуальный базовый класс, вопросов о том, к какому из вложенных объектов осуществляется доступ, не возникает.  
  
## <a name="see-also"></a>См. также  
 [Наследование](../cpp/inheritance-cpp.md)