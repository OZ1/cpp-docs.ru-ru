---
title: "Поддержка Юникода в компиляторе и компоновщике | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.UseUnicodeResponseFiles"
  - "VC.Project.VCLibrarianTool.UseUnicodeResponseFiles"
  - "VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles"
  - "VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Юникод, Visual C++"
ms.assetid: acc1d322-56b9-4696-a30e-2af891a4e288
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Поддержка Юникода в компиляторе и компоновщике
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В данном разделе рассматривается поддержка Юникода в инструментах построения Visual C\+\+.  
  
 Имена файлов  
 Имена файлов, указываемые в командной строке или директивах компилятора \(например, \#include\), теперь могут содержать символы Юникода.  
  
 Файлы исходного кода  
 Символы Юникода теперь поддерживаются в идентификаторах, макросах, строковых и символьных литералах, а также в комментариях.  Также поддерживаются универсальные имена.  
  
 Символы Юникода могут вводиться в файлы исходного кода в следующих кодировках.  
  
-   UTF\-16 с прямым порядком байтов, с отметкой порядка байтов или без нее  
  
-   UTF\-16 с обратным порядком байтов, с отметкой порядка байтов или без нее  
  
-   UTF\-8 с отметкой порядка байтов  
  
 Output  
 В процессе компиляции компилятор выводит на консоль диагностические сообщения в кодировке UTF\-16.  Символы, которые могут отображаться на консоли, зависят от свойств окна консоли.  Выходные данные компилятора, перенаправляемые в файл, имеют кодировку текущей кодовой страницы ANSI консоли.  
  
 DEF\-файлы и файлы отклика компоновщика  
 Файлы отклика и DEF\-файлы могут иметь либо кодировку UTF\-16 с отметкой порядка байтов, либо кодировку ANSI.  Ранее поддерживалась только кодировка ANSI.  
  
 Файлы дампа ASM и COD  
 Файлы дампа COD и ASM по умолчанию имеют кодировку ANSI в целях совместимости с MASM.  Для вывода в кодировке UTF\-8 используйте параметр \/FAu.  Обратите внимание, что при указании параметра \/FAs смешанный источник будет печататься напрямую и выводиться в искаженном виде. Например, если исходный код имеет кодировку UTF\-8, а параметр \/FAsu не указан.  
  
 Имена файлов в Юникоде можно включить в среде разработки \([Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md)\), выбрав соответствующий инструмент и затем выбрав свойство **Использовать Юникод файлы ответа**, которое включено по умолчанию.  Одной из причин, по которой может понадобиться изменить данную настройку по умолчанию, является необходимость в настройке среды разработки на использование компилятора, не поддерживающего формат Юникода.  
  
## См. также  
 [Построение из командной строки](../Topic/Building%20on%20the%20Command%20Line.md)