---
title: "Класс Platform::Collections:: inputiterator | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
dev_langs:
- C++
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: caf29e32fc4af5c6d1e3f65abbe250bb150679c0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="platformcollectionsinputiterator-class"></a>Класс Platform::Collections::InputIterator
Предоставляет InputIterator библиотеки стандартных шаблонов для коллекций, унаследованных от среды выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename X>  
class InputIterator;  
```  
  
#### <a name="parameters"></a>Параметры  
 `X`  
 Имя типа класса шаблона InputIterator.  
  
### <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`difference_type`|Различие указателя (ptrdiff_t).|  
|`iterator_category`|Категория итератора ввода (:: std::input_iterator_tag).|  
|`pointer`|Указатель на `const X`|  
|`reference`|Ссылка на `const X`|  
|`value_type`|Имя типа `X` .|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[InputIterator::InputIterator](#ctor)|Инициализирует новый экземпляр класса InputIterator.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Оператор InputIterator::operator!=](#operator-inequality)|Указывает, отличен ли текущий объект InputIterator от указанного объекта InputIterator.|  
|[Оператор InputIterator::operator*](#operator-decrement)|Извлекает ссылку на элемент, указанный текущим итератором InputIterator.|  
|[Оператор InputIterator::operator++](#operator-increment)|Выполняет приращение текущего итератора InputIterator.|  
|[Оператор InputIterator::operator==](#operator-equality)|Указывает, равен ли текущий объект InputIterator указанному объекту InputIterator.|  
|[Оператор InputIterator::operator->](#operator-arrow)|Извлекает адрес элемента, на который ссылается текущий итератор InputIterator.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `InputIterator`  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  

## <a name="ctor"></a>  InputIterator::InputIterator Constructor
Инициализирует новый экземпляр класса InputIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
InputIterator();  
explicit InputIterator(Windows::Foundation::Collections<X>^ iter);  
```  
  
### <a name="parameters"></a>Параметры  
 `iter`  
 Объект итератора.  
  


## <a name="operator-arrow"></a>  InputIterator::operator-&gt; Operator
Извлекает адрес элемента, указанного текущим итератором InputIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
pointer operator->() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес элемента, указанного текущим итератором InputIterator.  
  


## <a name="operator-dereference"></a>  InputIterator::operator* Operator
Извлекает ссылку на элемент, указанный текущим итератором InputIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, указанный текущим итератором InputIterator.  
  


## <a name="operator-equality"></a>  InputIterator::operator== Operator
Указывает, равен ли текущий объект InputIterator указанному объекту InputIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool operator== (const InputIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект InputIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если текущий объект InputIterator равен объекту `other`, в противном случае — значение `false`.  
  


## <a name="operator-increment"></a>  InputIterator::operator++ Operator
Выполняет приращение текущего итератора InputIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```    
InputIterator& operator++();   
InputIterator operator++(int);  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый синтаксис выполняет приращение текущего итератора InputIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора InputIterator, а затем выполняет приращение текущего итератора InputIterator.  
  
### <a name="remarks"></a>Примечания  
 Первый синтаксис InputIterator выполняет приращение текущего итератора InputIterator перед его использованием.  
  
 Второй синтаксис выполняет приращение текущего итератора InputIterator после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.  
  


## <a name="operator-inequality"></a>  InputIterator::operator!= Operator
Указывает, отличен ли текущий объект InputIterator от указанного объекта InputIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool operator!=(const InputIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект InputIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если текущий объект InputIterator не равен объекту `other`, в противном случае — значение `false`.   

  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](platform-namespace-c-cx.md)