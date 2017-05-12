---
title: "Интерфейсы (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11034314-d54a-426d-923b-5ab7a6b9f8ce
caps.latest.revision: 20
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 20
---
# Интерфейсы (C++/CX)
Хотя класс ссылки может наследовать не более чем от одного конкретного базового класса, он может реализовывать любое количество классов интерфейсов. Сам класс интерфейса \(или структура интерфейса\) может наследовать \(или требовать\) несколько классов интерфейсов, может перегружать свои функции\-члены и иметь параметры\-типы.  
  
## Характеристики  
 Интерфейс имеет следующие характеристики:  
  
-   Класс интерфейса \(или структура\) должен быть объявлен в пространстве имен, а также может иметь режим доступа public \(открытый\) или private \(закрытый\). Только открытые интерфейсы формируют метаданные.  
  
-   члены интерфейса могут включать в себя свойства, методы и события;  
  
-   Все члены интерфейса неявно являются открытыми и виртуальными.  
  
-   поля и статические члены запрещены;  
  
-   Типы, используемые в качестве свойств, параметров методов и возвращаемых значений могут быть только типами [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]; к ним относятся основные типы и типы классов перечислений.  
  
## Объявление и использование  
 В следующем примере показан способ объявления интерфейса. Обратите внимание, что интерфейс можно объявить или как класс, или как тип структуры.  
  
 [!code-cpp[cx_interfaces#01](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#01)]  
  
 Для реализации интерфейса класс ссылки или структура ссылки объявляет и реализует виртуальные методы и свойства. Интерфейс и реализующий его класс ссылки должны использовать одинаковые имена параметров методов, как показано в следующем примере:  
  
 [!code-cpp[cx_interfaces#02](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#02)]  
  
## Иерархии наследования интерфейсов  
 Интерфейс может наследовать от одного или нескольких интерфейсов. Но в отличие от структуры и класса ссылки, интерфейс не объявляет наследуемые члены интерфейса. Если интерфейс B наследует от интерфейса A, а класс ссылки C наследует от интерфейса B, класс C должен реализовывать и A, и B. Это показано в следующем примере.  
  
 [!code-cpp[cx_interfaces#03](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#03)]  
  
## Реализация свойств и событий интерфейса  
 Как показано в предыдущем примере, для реализации свойств интерфейса можно использовать тривиальные виртуальные свойства. Также можно определить пользовательские методы получения и задания в реализующем классе.  Оба эти метода должны быть открытыми в свойстве интерфейса.  
  
 [!code-cpp[cx_interfaces#04](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#04)]  
  
 Если интерфейс объявляет свойство, доступное только для получения или только для задания, реализующий класс должен явно предоставить метод получения или задания.  
  
 [!code-cpp[cx_interfaces#05](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#05)]  
  
 Кроме того, можно реализовать пользовательские методы добавления и удаления для событий в реализующем классе.  
  
## Явная реализация интерфейса  
 Если класс ссылки реализует несколько интерфейсов, и эти интерфейсы содержат методы, имена и сигнатуры которых идентичны компилятору, можно использовать следующий синтаксис для явного указания метода интерфейса, который реализуется методом класса.  
  
 [!code-cpp[cx_interfaces#06](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#06)]  
  
## Универсальные интерфейсы  
 В [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] ключевое слово `generic` используется для представления параметризованного типа [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Параметризованный тип передается в метаданные и может использоваться кодом, который написан на любом языке, поддерживающем параметры\-типы.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] определяет некоторые универсальные интерфейсы, например [Windows::Foundation::Collections::IVector\<T](Windows::Foundation::Collections::IVector), однако не поддерживает создание открытых, определяемых пользователем универсальных интерфейсов в [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]. Однако можно создавать закрытые универсальные интерфейсы.  
  
 Ниже показано, как с помощью типов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] можно создать универсальный интерфейс.  
  
-   Универсальный определяемый пользователем `interface class` в компоненте не может передаваться в соответствующий файл метаданных Windows; поэтому он не может быть открытым и не может реализовываться клиентским кодом в других файлах WinMD. Он может быть реализован неоткрытыми классами ссылок в том же компоненте. Открытый класс ссылки может иметь универсальный тип интерфейса в качестве закрытого члена.  
  
     В следующем фрагменте кода показано, как объявить универсальный `interface class`, а затем реализовать его в закрытом классе ссылки и использовать класс ссылки в качестве закрытого члена открытого класса ссылки.  
  
     [!code-cpp[cx_interfaces#07](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#07)]  
  
-   Универсальный интерфейс должен следовать стандартным правилам интерфейсов, регламентирующим возможности доступа, члены, отношения *requires* \(требует\), базовые классы и т. д.  
  
-   Универсальный интерфейс может принимать один или несколько параметров универсальных типов, перед которыми указывается `typename` или `class`. Параметры, не являющиеся типами, не поддерживаются.  
  
-   Параметр\-тип может быть любым типом [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Это означает, что параметр\-тип может быть ссылочным типом, типом значения, классом интерфейса, делегатом, основным типом или открытым перечислимым классом.  
  
-   *Закрытый универсальный интерфейс* — это интерфейс, наследующий от универсального интерфейса и указывающий аргументы конкретного типа для всех параметров\-типов. Его можно использовать везде, где допускается использовать неуниверсальный закрытый интерфейс.  
  
-   *Открытый универсальный интерфейс* — это интерфейс, имеющий один или несколько параметров\-типов, для которых пока не предоставлено никаких конкретных типов. Его можно использовать везде, где допускается использовать типы, в том числе в качестве аргумента\-типа другого универсального интерфейса.  
  
-   Параметризовать можно только весь интерфейс, но не отдельные методы.  
  
-   Параметры\-типы нельзя ограничивать.  
  
-   Закрытый универсальный интерфейс имеет неявно создаваемый UUID. Пользователь не может задать UUID.  
  
-   Если в интерфейсе имеется какая\-либо ссылка на текущий интерфейс \(в параметре метода, возвращаемом значении или свойстве\), предполагается, что она указывает на текущий экземпляр. Например *IMyIntf* означает *IMyIntf\<T\>*.  
  
-   Если тип параметра метода является параметром\-типом, при объявлении этого параметра или переменной используется имя параметра\-типа без указателя, собственной ссылки и деклараторов дескрипторов. Иначе говоря, невозможно написать "T^".  
  
-   Шаблонные классы ссылок должны быть закрытыми. Они могут реализовывать универсальные интерфейсы и передавать параметр шаблона *T* в универсальный аргумент *T*. Каждый создаваемый экземпляр шаблонного класса ссылки сам является классом ссылки.  
  
## См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)