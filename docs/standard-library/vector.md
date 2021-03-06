---
title: "&lt;vector&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <vector>
dev_langs:
- C++
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94038dcbda6c35723fabbaee153902ec48e45c71
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltvectorgt"></a>&lt;vector&gt;
Определяет вектор классов шаблонов контейнеров и некоторые вспомогательные шаблоны.  
  
 `vector` — это контейнер, который упорядочивает элементы данного типа в виде линейной последовательности. Он обеспечивает быстрый произвольный доступ к любому элементу и позволяет динамически добавлять элементы в последовательность и удалять их. `vector` является наиболее подходящим типом контейнера для последовательности, когда на первом месте стоит производительность произвольного доступа.  
  
 Подробнее о классе `vector` см. в разделе [Класс vector](../standard-library/vector-class.md). Сведения о специализации `vector<bool>` см. в разделе [Класс vector\<bool>](../standard-library/vector-bool-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace std {  
template <class Type, class Allocator>  
class vector;  
template <class Allocator>  
class vector<bool>;  
 
template <class Allocator>  
struct hash<vector<bool, Allocator>>;  
 // TEMPLATE FUNCTIONS  
template <class Type, class Allocator>  
bool operator== (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator!= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<(
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator> (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator>= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
void swap (
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);

}  // namespace std  
```  
  
#### <a name="parameters"></a>Параметры  
 Тип  
 Параметр-шаблон для типа данных, хранящихся в векторе.  
  
 Allocator  
 Параметр-шаблон для хранимого объекта распределителя, отвечающего за выделение и освобождение памяти.  
  
 `left`  
 Первый (левый) вектор в операции сравнения.  
  
 `right`  
 Второй (правый) вектор в операции сравнения.  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор! =](../standard-library/vector-operators.md#op_neq)|Проверяет следующее условие: объект вектора слева от оператора не равен объекту вектора справа от оператора.|  
|[оператор<](../standard-library/vector-operators.md#op_lt)|Проверяет следующее условие: объект вектора слева от оператора меньше, чем объект вектора справа от оператора.|  
|[operator\<=](../standard-library/vector-operators.md#op_gt_eq)|Проверяет следующее условие: объект вектора слева от оператора меньше или равен объекту вектора справа от оператора.|  
|[оператор==](../standard-library/vector-operators.md#op_eq_eq)|Проверяет следующее условие: объект вектора слева от оператора равен объекту вектора справа от оператора.|  
|[оператор>](../standard-library/vector-operators.md#op_gt)|Проверяет следующее условие: объект вектора слева от оператора больше, чем объект вектора справа от оператора.|  
|[оператор>=](../standard-library/vector-operators.md#op_gt_eq)|Проверяет следующее условие: объект вектора слева от оператора больше или равен объекту вектора справа от оператора.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс vector](../standard-library/vector-class.md)|Класс шаблона контейнеров последовательностей для хранения элементов заданного типа в линейном порядке и быстрого произвольного доступа к любому элементу.|  
  
### <a name="specializations"></a>Специализации  
  
|||  
|-|-|  
|[Класс vector\<bool>](../standard-library/vector-bool-class.md)|Полная специализация вектора шаблонного класса для элементов типа `bool` с распределителем для базового типа, используемого специализацией.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<vector>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)

