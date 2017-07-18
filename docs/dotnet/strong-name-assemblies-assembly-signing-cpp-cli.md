---
title: "Сборки со строгими именами (подписывание сборок) (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework [C++], подпись сборки"
  - "сборки [C++]"
  - "сборки [C++], подписывание"
  - "компоновщик [C++], подпись сборки"
  - "подписывание сборок"
  - "сборки со строгими именами [C++]"
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Сборки со строгими именами (подписывание сборок) (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В данном разделе рассматриваются способы подписывания сборок. Часто это называется присвоением сборке строгого имени.  
  
## Примечания  
 При подписывании сборок в Visual C\+\+ следует использовать параметры компоновщика во избежание проблем, связанных с атрибутами CLR для подписывания сборок:  
  
-   <xref:System.Reflection.AssemblyDelaySignAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyFileAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 Одной из причин, обуславливающих нежелательность использования атрибутов, является то, что имя ключа можно видеть в метаданных сборки, что может представлять угрозу безопасности, если в имени файла присутствуют конфиденциальные сведения.  Кроме того, при выполнении средой разработки Visual C\+\+ процесса построения ключ, используемый для подписывания сборки, станет недействительным, если для присвоения сборке строгого имени используются атрибуты CLR, после чего к сборке применяется средство завершающей обработки, такое как mt.exe.  
  
 При выполнении построения из командной строки, использовании параметров компоновщика для подписывания сборки и последующем запуске средства завершающей обработки \(например, mt.exe\) потребуется произвести повторное подписывание сборки с помощью средства sn.exe.  Также можно произвести построение и отложенное подписание сборки, завершив подписание после запуска средства завершающей обработки.  
  
 Если при построении в среде разработки используются атрибуты подписи, сборку можно с успехом подписать путем явного вызова sn.exe \([Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)\) в событии после сборки.  Для получения дополнительной информации см. [Задание событий построения](../ide/specifying-build-events.md).  При использовании атрибутов и события после сборки вместо параметров компоновщика построение может занять меньше времени.  
  
 Следующие параметры компоновщика поддерживают подписывание сборок:  
  
-   [\/DELAYSIGN \(частичное подписание сборки\)](../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE \(задание ключа или пары ключей для подписи сборки\)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER \(задание контейнера ключей для подписи сборки\)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Дополнительные сведения о строгих сборках см. в разделе [Создание и использование сборок со строгими именами](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
## См. также  
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)