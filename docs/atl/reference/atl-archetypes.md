---
title: "ATL Archetypes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "archetype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, archetypes"
ms.assetid: 809fb0af-c0f4-4cc0-b5bc-afe3de5d9722
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ATL Archetypes
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом контексте *архетип* теоретический класс, который предоставляет коллекцию методов элементов данных статических функций typedef или других функций.  Архетип также включает описание семантики необходимой для создания или использовал класс для представления указанный понятие.  Классы, передразнивают архетип, предоставляя те же функции овеществляют одинаковое понятие и могут использоваться где бы ни архетипу можно использовать.  
  
 Архетипы полезны в C\+\+ для описания функций допустимых значений для параметров шаблона.  Конструктор шаблона имеют представление о том ясную обязательных и достаточных функций параметра шаблона, и компилятор требует синтаксических компонентов во время построения, но пользователю шаблона необходимо описать семантику документация и связи между архетипами и классами, которые необходимо узнать, как ожидания.  
  
 Примеры архетипов в стандартной библиотеке C\+\+ различные типы итератора и контейнера.  Эти архетипы описаны в разделах, [соглашения итератора](../Topic/Iterators.md) и [Контейнеров STL](../../standard-library/stl-containers.md).  
  
 Сервер ATL определяет следующие архетипы:  
  
|Имя|Описание|  
|---------|--------------|  
|[Архетип работы](../../atl/reference/worker-archetype.md)|Классы, соответствующие архетипу *рабочего* процесса предоставляют код в очереди элементы работы в пуле потоков.|  
  
## См. также  
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)