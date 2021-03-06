---
title: "&lt;system_error&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <system_error>
- system_error
dev_langs:
- C++
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: efd25be1567909effaa25f984acb29bd3f52c529
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltsystemerrorgt"></a>&lt;system_error&gt;
Включите заголовок `<system_error>`, чтобы определить класс исключений `system_error` и связанные шаблоны для обработки низкоуровневых системных ошибок.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <system_error>  
```  
  
### <a name="objects"></a>Объекты  
  
|||  
|-|-|  
|[generic_category](../standard-library/system-error-functions.md#generic_category)|Представляет категорию общих ошибок.|  
|[system_category](../standard-library/system-error-functions.md#system_category)|Представляет категорию ошибок, вызванных переполнением системы низкого уровня.|  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[generic_errno](../standard-library/system-error-typedefs.md#generic_errno)|Тип, который представляет перечисление, предоставляющее символьные имена для всех макросов с ошибками в коде, определяемых Posix в `<errno.h>`.|  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|Создает объект `error_code`.|  
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|Создает объект `error_condition`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор==](../standard-library/system-error-operators.md#op_eq_eq)|Проверяет равенство объекта слева от оператора объекту справа от оператора.|  
|[оператор!=](../standard-library/system-error-operators.md#op_neq)|Проверяет неравенство объекта слева от оператора объекту справа от оператора.|  
|[оператор<](../standard-library/system-error-operators.md#op_lt)|Проверяет, меньше ли какой-либо объект переданного для сравнения объекта.|  
  
### <a name="enumerations"></a>Перечисления  
  
|||  
|-|-|  
|[errc](../standard-library/system-error-enums.md#errc)|Предоставляет символьные имена для всех макросов кода ошибки, определенных Posix в `<errno.h>`.|  
  
### <a name="classes-and-structs"></a>Классы и структуры  
  
|||  
|-|-|  
|[error_category](../standard-library/error-category-class.md)|Представляет абстрактный, общий базовый класс для объектов, который описывает категорию кодов ошибок.|  
|[error_code](../standard-library/error-code-class.md)|Представляет системные ошибки низкого уровня, относящиеся к конкретной специализации.|  
|[error_condition](../standard-library/error-condition-class.md)|Представляет коды ошибок, определенные пользователем.|  
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|Представляет тип предиката, проверяющий перечисление [Класс error_code](../standard-library/error-code-class.md).|  
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|Представляет тип предиката, проверяющий перечисление [Класс error_condition](../standard-library/error-condition-class.md).|  
|[system_error](../standard-library/system-error-class.md)|Представляет базовый класс для всех исключений, создаваемых для отчета о переполнении системы низкого уровня.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<system_error>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)



