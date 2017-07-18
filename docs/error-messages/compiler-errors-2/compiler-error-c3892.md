---
title: "Ошибка компилятора C3892 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3892"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3892"
ms.assetid: 83fff42c-ea48-442f-bc2e-b33a6b99d890
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3892
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная": невозможно присваивать значения переменной, которая объявлена как константа  
  
 Изменение константной переменной после ее объявления и инициализации не допускается.  
  
 Следующий пример приводит к возникновению ошибки C3892:  
  
```  
// C3892.cpp  
// compile with: /clr  
ref struct Y1 {  
   static const int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3892  
}  
```