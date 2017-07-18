---
title: "Ошибка компилятора C2778 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2778"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2778"
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2778
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

неправильно сформированный GUID в \_\_declspec\(uuid\(\)\)  
  
 Неверный GUID поддерживается расширенным атрибутом [uuid](../../cpp/uuid-cpp.md).  
  
 GUID должен быть строкой шестнадцатеричных чисел в следующем формате:  
  
```  
// C2778a.cpp  
// compile with: /c  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};  
```  
  
 Расширенный атрибут `uuid` принимает строку, распознанную [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589), с или без разделителей в виде фигурных скобок.  
  
 Следующий пример приводит к возникновению ошибки C2778:  
  
```  
// C2778b.cpp  
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778  
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778  
```