---
title: "Использование общего элемента управления как дочернего окна | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "дочерние окна, стандартные элементы управления как"
  - "стандартные элементы управления [C++], дочерние окна"
  - "элементы управления [MFC], использование в качестве дочерних окон"
  - "окна [C++], стандартные элементы управления как"
  - "общие элементы управления Windows [C++], дочерние окна"
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Использование общего элемента управления как дочернего окна
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Все общие элементы управления Windows можно использовать в качестве дочернее окно любого другого окна.  В следующей процедуре описывается создание общий элемент управления динамически и затем работать с ней.  
  
### Использовать общий элемент управления как дочернее окно  
  
1.  Определение элемента управления в связанном классе или обработчик.  
  
2.  Использование элемента управления переопределение метода [CWnd::Create](../Topic/CWnd::Create.md) для создания элемента управления Windows.  
  
3.  После того как будет создан элемент управления \(начиная с обработчика `OnCreate` при подкласс элемента управления\), можно управлять с помощью элемента управления его функции\-члены.  См. описание отдельных элементов управления на [Элементы управления](../mfc/controls-mfc.md) сведения о методах.  
  
4.  После окончания работы с элементом управления, используйте [CWnd::DestroyWindow](../Topic/CWnd::DestroyWindow.md) для удаления элемента управления.  
  
## См. также  
 [Создание и использование элементов управления](../mfc/making-and-using-controls.md)   
 [Элементы управления](../mfc/controls-mfc.md)