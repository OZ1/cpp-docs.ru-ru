---
title: "Ошибка компилятора C2326 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2326
dev_langs:
- C++
helpviewer_keywords:
- C2326
ms.assetid: 01a5ea40-de83-4e6f-a4e8-469f441258e0
caps.latest.revision: 8
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 380fd5eff72553264a396a9ad1014638becbf6e8
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2326"></a>Ошибка компилятора C2326
"оператор_объявления": функция не может обратиться к "имя"  
  
 В коде предпринимается попытка изменить переменную-член, что невозможно.  
  
## <a name="example"></a>Пример  
 При компиляции следующего примера возникнет ошибка C2326:  
  
```  
// C2326.cpp  
void MyFunc() {  
   int i;  
  
   class MyClass  {  
   public:  
      void mf() {  
         i = 4;   // C2326 i is inaccessible  
      }  
   };  
}  
```