---
title: "Ошибка компилятора C2195 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2195"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2195"
ms.assetid: 9f9f035c-9c51-4173-a8ea-c6f907fc5c63
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2195
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор" : сегмент данных  
  
 Прагма\-директива `code_seg` использует имя сегмента, указанное в прагма\-директиве `data_seg`.  
  
 Следующий пример приводит к возникновению ошибки C2195:  
  
```  
// C2195.cpp  
#pragma data_seg("MYDATA")  
#pragma code_seg("MYDATA")   // C2195  
#pragma code_seg("MYDATA2")   // OK  
```