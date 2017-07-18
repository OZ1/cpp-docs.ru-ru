---
title: "Ошибка компилятора C2348 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2348"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2348"
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2348
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"имя типа": не зарегистрировано в стиле C, невозможно экспортировать во внедренный IDL  
  
 Чтобы поместить `struct` в IDL\-файл с атрибутом [экспорт](../../windows/export.md), `struct` должен содержать только данные.  
  
 Следующий пример приводит к возникновению ошибки C2348:  
  
```  
// C2348.cpp  
// C2348 error expected  
[ module(name="SimpleMidlTest") ];  
  
[export]  
struct Point {  
   // Delete the following two lines to resolve.  
   Point() : m_i(0), m_j(0) {}  
   Point(int i, int j) : m_i(i), m_j(j) {}  
  
   int m_i;  
   int m_j;  
};  
```