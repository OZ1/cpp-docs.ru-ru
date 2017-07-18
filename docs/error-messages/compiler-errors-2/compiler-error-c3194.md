---
title: "Ошибка компилятора C3194 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3194"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3194"
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3194
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член": тип, передаваемый по значению, не может иметь оператор присваивания  
  
 Специальные функции\-члены, которые требуют автоматического вызова компилятора, например конструктор копий или оператор присваивания копий, не поддерживаются в классе значений.  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C3194:  
  
```  
// C3194.cpp  
// compile with: /clr /c  
value struct MyStruct {  
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194  
};  
  
ref struct MyStruct2 {  
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK  
};  
```