---
title: "Печать | Microsoft Docs"
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
  - "документы, печать"
  - "печать [MFC]"
  - "печать [MFC], с платформы"
  - "классы представлений, операции печати"
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Печать
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Реализует независимо от Microsoft Windows для отображения.  В MFC, это означает, что такие же вызовы рисования, в функции\-члене `OnDraw` класса представления, ответственных за создание на экране и на других устройствах, таких как принтеров.  Для предварительного просмотра целевое устройство смоделированной вывод принтера для отображения.  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a> Роль пользователя в роли печати и .NET Framework  
 Класс представления имеет следующие обязанности.  
  
-   Уведомляет платформу количество страниц в документе.  
  
-   Исключение, что напечатал заданной страницы, создайте этой части документа.  
  
-   Выделите и отменить все шрифты или других ресурсов \(GDI\) приборного интерфейса графических объектов, необходимых для печати.  
  
-   При необходимости отправлять все коды escape\-последовательности, необходимые для изменения режима принтера перед выводом на данной странице, например, чтобы изменить ориентацию печати на каждой странице по отдельности.  
  
 Обязанностью платформы следующим образом:  
  
-   Отобразите диалоговое окно **Печать**.  
  
-   Создайте объект [CDC](../Topic/CDC%20Class.md) для принтера.  
  
-   Вызовите функции\-члены [StartDoc](../Topic/CDC::StartDoc.md) и [EndDoc](../Topic/CDC::EndDoc.md) объекта `CDC`.  
  
-   Повторно вызовите функцию\-член [StartPage](../Topic/CDC::StartPage.md) объекта `CDC`, уведомляет класс представления, страница должна быть напечатана и вызовите функцию\-член [EndPage](../Topic/CDC::EndPage.md) объекта `CDC`.  
  
-   Вызов функций переопределяемого метода в представлении в соответствующие моменты.  
  
 В следующих статьях рассматривается как платформа поддерживает печать и предварительный просмотр:  
  
### Дополнительные сведения  
  
-   [Как принтер по умолчанию выполняется](../Topic/How%20Default%20Printing%20Is%20Done.md)  
  
-   [Multipage документы](../mfc/multipage-documents.md)  
  
-   [Заголовки и нижние колонтитулы](../mfc/headers-and-footers.md)  
  
-   [Выделение ресурсов GDI для печати](../mfc/allocating-gdi-resources.md)  
  
-   [Предварительный просмотр](../mfc/print-preview-architecture.md)  
  
## См. также  
 [Печать и предварительный просмотр печати](../mfc/printing-and-print-preview.md)