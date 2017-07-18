---
title: "Неустранимая ошибка C1010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1010"
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Неустранимая ошибка C1010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

непредвиденный конец файла во время поиска предкомпилированного заголовка.Возможно, вы забыли добавить директиву "'\#include name'" в источник.  
  
 Файл заголовка, указанный с [\/Yu](../../build/reference/yu-use-precompiled-header-file.md), не указан в исходном файле.  Этот параметр включен по умолчанию в большинстве типов проектов Visual C\+\+, а "stdafx.h" является именем файла заголовка по умолчанию, заданным этим параметром.  
  
 Для разрешения этой ошибки в среде Visual Studio используйте один из следующих методов:  
  
-   Если вы не используете предварительно скомпилированные заголовки, установите для параметра **Создавать или использовать предкомпилированный заголовок** значение **Не использовать предкомпилированный заголовок**.  Для этого выполните следующее:  
  
    1.  В обозревателе решений окна проекта щелкните правой кнопкой мыши имя проекта и выберите **Свойства**.  
  
    2.  В левом окне выберите папку **C\/C\+\+**.  
  
    3.  Выберите узел **Предкомпилированные заголовки**.  
  
    4.  В правом окне выберите **Создать или использовать предкомпилированный заголовок** и щелкните **Не использовать предкомпилированный заголовок**.  
  
-   Убедитесь, что не был случайно удален, переименован или перемещен файл заголовка \(по умолчанию — stdafx.h\) из текущего проекта.  Этот файл должен быть включен до какого\-либо кода в исходном файле с помощью **\#include "stdafx.h"**. \(Этот файл заголовка указан как свойство проекта **Создать или использовать PCH во всем файле**.\)