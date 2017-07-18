---
title: "2.9 Directive Nesting | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.9 Directive Nesting
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Динамическое вложение директив должен соответствовать следующим правилам:  
  
-   A **Параллельно** директива динамически внутри других  **Параллельно** логический задает новую рабочую группу, которая состоит из текущего потока, только если во вложенном параллелизм не включена.  
  
-   **для**"  **Разделы**и  **Одинарный** директивы, которые связываются с этим же  **Параллельно** не следует разрешать, чтобы вложить в друга.  
  
-   **Критические** директивы с таким же именем не могут быть вложены в друга.  Обратите внимание на это ограничение не достаточны, чтобы предотвратить взаимоблокировку.  
  
-   **для**"  **Разделы**и  **Одинарный** директивы не разрешены в динамической экстенты  **Критические**"  **Упорядочено**и  **Образец** если директивы области связываются с одинаковым  **Параллельно** в качестве области.  
  
-   **барьер** директивы не разрешены в динамической экстенты  **для**"  **Упорядочено**"  **Разделы**"  **Одинарный**"  **Образец**и  **Критические** если директивы области связываются с одинаковым  **Параллельно** в качестве области.  
  
-   **Образец** директивы не разрешены в динамической экстенты  **для**"  **Разделы**и  **Одинарный** если директивы  **Образец** привязка к одним и тем же директив  **Параллельно** как рабочий\-совместно с помощью директивы.  
  
-   **Упорядочено** директивы не разрешены в динамической экстенты  **Критические** если директивы области связываются с одинаковым  **Параллельно** в качестве области.  
  
-   Any директива, которая используется при выполнении динамически в параллельной области также разрешено выполняться вне параллельной области.  При выполнении динамически вне параллельной области пользователь\-определенная директива выполняется командой структурной только главного потока.