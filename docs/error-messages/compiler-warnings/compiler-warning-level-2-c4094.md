---
title: "Предупреждение компилятора (уровень 2) C4094 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4094"
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 2) C4094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

в 'token' без тегов не объявлены символы  
  
 Компилятор обнаружил пустое объявление с использованием структуры, объединения или класса без тегов.  Объявление игнорируется.  
  
## Пример  
  
```  
// C4094.cpp  
// compile with: /W2  
struct  
{  
};   // C4094  
  
int main()  
{  
}  
```  
  
 При таких условиях генерируется ошибка, появляющаяся только в режиме ANSI\-совместимости \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).