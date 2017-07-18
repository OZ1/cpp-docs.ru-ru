---
title: "Совместимость ANSI с C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Ansi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ANSI [C++], C - стандарт"
  - "совместимость [C++], ANSI C"
  - "соответствие ANSI C"
  - "соглашения [C++], расширения Microsoft"
  - "расширения соглашений об именовании Microsoft"
  - "соглашения об именовании [C++], библиотека Microsoft"
  - "символы подчеркивания"
  - "символы подчеркивания, начальный"
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Совместимость ANSI с C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Соглашение об именовании для всех относящихся к системам Microsoft идентификаторов в системе времени выполнения \(например, функций, макросов, констант, переменных и определений типов\) соответствует согласно стандарту ANSI.  В этой документации любая функция времени выполнения, которая соответствует стандартам ANSI\/ISO C помечена как ANSI\-совместимая.  ANSI\-совместимые приложения должны использовать только эти соответствующие стандарту ANSI функции.  
  
 Имена функций и глобальных переменных, которые относятся к системам Microsoft начинаются с одного символа подчеркивания.  Эти имена можно переопределить только локально, находясь в области действия кода.  Например, при включении файлов заголовков времени выполнения Microsoft, по\-прежнему можно локально переопределить функцию для систем Microsoft с именем `_open`, объявив локальную переменную с таким же именем.  Однако нельзя использовать это имя для собственных глобальных функций или глобальных переменных.  
  
 Имена относящихся к системам Microsoft макросов и констант манифеста начинаются двумя символами подчеркивания или одним ведущий символом подчеркивания с идущей за ним прописной буквой.  Область видимости этих идентификаторов абсолютна.  Например, по этой причине нельзя использовать относящийся к системам Microsoft идентификатор **\_UPPER**.  
  
## См. также  
 [Совместимость](../c-runtime-library/compatibility.md)