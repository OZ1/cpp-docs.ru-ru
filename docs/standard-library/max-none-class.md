---
title: "Класс max_none | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- max_none
- stdext::max_none
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
dev_langs:
- C++
helpviewer_keywords:
- max_none class
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: a8d3380f89f3bd25be0c23e719dfa94df5539ae4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="maxnone-class"></a>Класс max_none
Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) нулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <std::size_t Max>  
class max_none
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Max`|Класс max, который определяет максимальное количество элементов для хранения в `freelist`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[allocated](#allocated)|Увеличивает счетчик выделенных блоков памяти.|  
|[deallocated](#deallocated)|Уменьшает счетчик выделенных блоков памяти.|  
|[full](#full)|Возвращает значение, указывающее, следует ли добавить в свободный список дополнительные блоки памяти.|  
|[released](#released)|Уменьшает количество блоков памяти в свободном списке.|  
|[saved](#saved)|Увеличивает количество блоков памяти в свободном списке.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
##  <a name="allocated"></a>  max_none::allocated  
 Увеличивает счетчик выделенных блоков памяти.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Nx`|Значение приращения.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Она вызывается после каждого успешного вызова со стороны `cache_freelist::allocate` оператора `new`. Аргумент `_Nx` представляет число блоков памяти в блоке, выделяемом оператором `new`.  
  
##  <a name="deallocated"></a>  max_none::deallocated  
 Уменьшает счетчик выделенных блоков памяти.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Nx`|Значение приращения.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Она вызывается после каждого вызова со стороны `cache_freelist::deallocate` оператора `delete`. Аргумент `_Nx` представляет число блоков памяти в блоке, который освобождается оператором `delete`.  
  
##  <a name="full"></a>  max_none::full  
 Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член всегда возвращает значение `true`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает `true`, `deallocate` помещает блок памяти в свободный список; если он возвращает false, `deallocate` вызывает оператор `delete` для освобождения блока.  
  
##  <a name="released"></a>  max_none::released  
 Уменьшает количество блоков памяти в свободном списке.  
  
```
void released();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.  
  
##  <a name="saved"></a>  max_none::saved  
 Увеличивает количество блоков памяти в свободном списке.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Вызывается методом `cache_freelist::deallocate` каждый раз, когда он помещает блок памяти свободного списка.  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)



