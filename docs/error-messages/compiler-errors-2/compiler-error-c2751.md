---
title: "Ошибка компилятора C2751 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2751"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2751"
ms.assetid: 44a3abdf-8a87-4a09-b34b-532c220c310a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2751
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"параметр": имя параметра функции не может быть полным именем  
  
 Нельзя использовать полное имя в качестве параметра функции.  
  
 Следующий пример приводит к возникновению ошибки C2751:  
  
```  
// C2751.cpp  
namespace std {  
   template<typename T>  
   class list {};  
}  
  
#define list std::list  
void f(int &list){}   // C2751  
```