---
title: "Предупреждение (уровень 1) C4632 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4632
dev_langs:
- C++
helpviewer_keywords:
- C4632
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
caps.latest.revision: 9
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 15bb34a0c418be4bd357cd3527c277157d01d2d8
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4632"></a>Предупреждение компилятора (уровень 1) C4632
Комментарий XML-документ: доступе к файлу отказано: причина  
  
 Путь к XDC-файлу (`file`) является недопустимым и не .xdc создан файл.  
  
 Следующий пример приводит к возникновению ошибки C4632:  
  
```  
// C4632.cpp  
// compile with: /clr /docv:\\falsedir /LD /W1  
// C4632 expected  
  
/// Text for class MyClass.  
public ref class MyClass {};  
```