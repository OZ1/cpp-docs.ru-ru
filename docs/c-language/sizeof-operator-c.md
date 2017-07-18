---
title: "Оператор sizeof (C) | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sizeof
dev_langs:
- C++
helpviewer_keywords:
- sizeof operator
ms.assetid: 70826d03-3451-41e4-bebb-a820ae66d53f
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 051f54958d3ba0523d6047f77d7a8217d60bd51c
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="sizeof-operator-c"></a>Оператор sizeof (C)
Оператор `sizeof` предоставляет объем хранения (в байтах), необходимого для хранения объекта типа "операнд". Этот оператор позволяет избежать задания зависимых от компьютера размера данных в программах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
sizeof unary-expression  
sizeof ( type-name )  
```  
  
## <a name="remarks"></a>Примечания  
Операнд является либо любым идентификатором *unary-expression*, либо выражением type-cas (то есть описателем типа, заключенным в скобки). *unary-expression* не может представлять объект битового поля, неполный тип или указатель функции. Результатом является целочисленная константа без знака. Стандартный заголовок STDDEF.H определяет этот тип как **size_t**.  
  
При применении оператора `sizeof` к идентификатору массива результатом является размер целого массива, а не размер указателя, представленного идентификатором массива.  
  
При применении оператора `sizeof` к имени структуры или типа объединения, идентификатору структуры или типа объединения, результатом является число байтов в структуре или объединении, включая внутреннее и конечное заполнение. Этот размер может включать внутреннее и конечное заполнение, используемое для выравнивания элементов структуры или объединения относительно границ памяти. Таким образом, результат может не соответствовать размеру, вычисленному путем добавления требований к хранению отдельных элементов.  
  
Если безразмерный массив является последним элементом структуры, оператор `sizeof` возвращает размер структуры без массива.  
  
```  
buffer = calloc(100, sizeof (int) );  
```  
  
В этом примере для передачи размера объекта `sizeof`, который меняется в зависимости от компьютеров, как аргумент функции времени выполнения с именем `int`, используется оператор `calloc`. Значение, возвращаемое функцией, хранится в `buffer`.  
  
```  
static char *strings[] = {  
      "this is string one",  
      "this is string two",  
      "this is string three",  
   };  
const int string_no = ( sizeof strings ) / ( sizeof strings[0] );   
```  
  
В этом примере `strings` — это массив указателей на `char`. Число указателей — это число элементов в массиве, но оно не определено. Легко определить количество указателей с помощью оператора `sizeof`, вычислив число элементов в массиве. Значение целого числа **const** `string_no` инициализируется до этого числа. Поскольку это значение **const**, `string_no` невозможно изменить.  
  
## <a name="see-also"></a>См. также  
[Операторы в C](c-operators.md)  
[Операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)  
  