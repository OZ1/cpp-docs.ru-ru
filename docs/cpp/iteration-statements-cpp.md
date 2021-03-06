---
title: "Операторы перебора (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c06ae1c043551bbb4ed6469ab3f87d1ed86fd92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iteration-statements-c"></a>Операторы перебора (C++)
Операторы итерации приводят к тому, что операторы (или составные операторы) выполняются ноль или более раз в соответствии с некоторыми критериями завершения цикла. Если эти операторы являются составными операторами, они выполняются в порядке, за исключением случаев либо [разрыв](../cpp/break-statement-cpp.md) инструкции или [Продолжить](../cpp/continue-statement-cpp.md) инструкции.  
  
 C++ предоставляется четыре оператора итерации — [при](../cpp/while-statement-cpp.md), [сделать](../cpp/do-while-statement-cpp.md), [для](../cpp/for-statement-cpp.md), и [на основе диапазонов для](../cpp/range-based-for-statement-cpp.md). Каждый из них выполняет итерацию до его завершения выражение принимает значение ноль (false) или цикл будет принудительно завершен с **разрыв** инструкции. В следующей таблице приведены сводные сведения об этих операторах и их действии. Дополнительные сведения о каждом из них см. в последующих разделах.  
  
### <a name="iteration-statements"></a>Операторы итерации  
  
|Оператор|Время вычисления|Инициализация|Increment|  
|---------------|------------------|--------------------|---------------|  
|`while`|Начало цикла|Нет|Нет|  
|**do**|Конец цикла|Нет|Нет|  
|**for**|Начало цикла|Да|Да|  
|**на основе диапазонов для**|Начало цикла|Да|Да|  
  
 Часть оператора итерации не может быть объявлением. Однако она может быть составным оператором, содержащим объявление.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)