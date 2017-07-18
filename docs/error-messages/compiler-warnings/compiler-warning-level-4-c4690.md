---
title: "Компилятор C4690 предупреждение (уровень 4) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4690
dev_langs:
- C++
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 62ed23d95c79ff4899d061d91b6bc6f329cdef62
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4690"></a>Предупреждение компилятора (уровень 4) C4690
[ emitidl( pop ) ]: операций извлечения (POP) больше, чем операций занесения (PUSH)  
  
 [Emitidl](../../windows/emitidl.md) атрибут был извлечен еще раз, она была отправлена.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению предупреждения C4690:  
  
```  
// C4690.cpp  
// compile with: /c /W4  
[emitidl(pop)];   // C4690  
class x {};  
```