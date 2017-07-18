---
title: "Структура hash (Стандартная библиотека C++) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::hash
dev_langs:
- C++
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
caps.latest.revision: 13
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 1af8dc2f8fef535883088c413827a98a35539980
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="hash-structure-c-standard-library"></a>Структура hash (Стандартная библиотека C++)
Определяет функцию-член, возвращающую значение, которое уникально определяется с помощью `Val`. Функция-член определяет функцию [hash](../standard-library/hash-class.md), которую можно использовать для сопоставления значений типа `thread::id` с распределением значений индекса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <>  
struct hash<thread::id> :   
    public unary_function<thread::id, size_t>  
{  
    size_t operator()(thread::id Val) const;

 
};  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<поток >  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread>](../standard-library/thread.md)   
 [Структура unary_function](../standard-library/unary-function-struct.md)
