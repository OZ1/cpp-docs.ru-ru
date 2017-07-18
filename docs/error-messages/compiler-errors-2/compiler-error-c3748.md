---
title: "Ошибка компилятора C3748 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3748"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3748"
ms.assetid: 6fe71a0a-dd93-4ce6-9729-b9616360cf34
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3748
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"интерфейс": управляемые интерфейсы не могут порождать события  
  
 Ключевое слово [\_\_event](../../cpp/event.md) не может отображаться внутри интерфейса.  
  
 Следующий пример приводит к возникновению ошибки C3748:  
  
```  
// C3748.cpp  
__interface I {  
// try the following line instead  
// struct I {  
   __event void f();   // C3748  
};  
  
int main() {  
}  
```