---
title: "оператор&lt; (&lt;образец контейнера&gt;) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::operator<
- operator<
- std.<
- <
- std.operator<
- std::<
dev_langs:
- C++
helpviewer_keywords:
- < operator, comparing specific objects
- operator<, valarrays
- < operator
- operator <, valarrays
ms.assetid: 31027dd6-53be-428b-b950-1dcb25393597
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: b705ee41d6793d6aa3a858298c8ac16b36d4db9a
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="operatorlt-ltsample-containergt"></a>оператор&lt; (&lt;образец контейнера&gt;)
> [!NOTE]
>  Данный раздел включен в документацию Visual C++ в качестве нефункционального примера контейнеров, используемых в стандартной библиотеке C++. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).  
  
 Перегружает **оператор<** для сравнения двух объектов класса шаблона [контейнер](../standard-library/sample-container-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Ty>  
bool operator<(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает `lexicographical_compare(left.begin, left.end, right.begin, right.end)`.  
  
## <a name="see-also"></a>См. также  
[\<образец контейнера>](../standard-library/sample-container.md)  
[begin](../standard-library/container-class-begin.md)  
[end](../standard-library/container-class-end.md)  