---
title: "Расширенные атрибуты классов хранения в C | Microsoft Docs"
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
  - "__declspec - ключевое слово [C]"
  - "расширенные атрибуты"
  - "расширенные атрибуты классов хранения"
  - "спецификаторы классов хранения, C - классы хранения"
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Расширенные атрибуты классов хранения в C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Уточненные сведения по этой теме см. в разделе [\_\_declspec \(Справочник по C\+\+\)](../cpp/declspec.md).  
  
 Расширенный синтаксис атрибутов упрощает и стандартизирует расширения для систем Microsoft в соответствии с правилами языка C.  К атрибутам класса хранения, в которых используется расширенный синтаксис атрибутов, относятся: thread, naked, dllimport и dllexport.  
  
 Расширенный синтаксис атрибутов для указания информации о классе памяти использует ключевое слово , которое указывает, что экземпляр заданного типа должен храниться с соответствующим атрибутом класса хранения для систем Microsoft \(thread, naked, dllimport или dllexport\).  Имеются и другие модификаторы класса хранения: ключевые слова static и extern.  Однако эти ключевые слова входят в стандарт ANSI C, и как таковые они не используются с расширенным синтаксисом атрибутов.  
  
## Синтаксис  
 *спецификатор\-класса\-хранения*:  
 `__declspec` \( *последовательность\-модификаторов\-расширенного\-объявления* \) \/\* Относится только к системам Microsoft \*\/  
  
 *последовательность\-модификаторов\-расширенного\-объявления*:  
 *модификатор\-расширенного\-объявления*  необ  
  
 *последовательность\-модификаторов\-расширенного\-объявления модификатор\-расширенного\-объявления*  
  
 *модификатор\-расширенного\-объявления*:  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
 Модификаторы объявления разделяются пробелами.  Обратите внимание, что *последовательность\-модификаторов\-расширенного\-объявления* может быть пустой; в этом случае ключевое слово \_\_declspec не применяется.  
  
 Атрибуты класса хранения thread, naked, dllimport и dllexport являются свойством только объявления данных или функции, к которому они применяются; они не переопределяют атрибуты типа самой функции.  Атрибут thread влияет только на данные.  Атрибут naked влияет только на функции.  Атрибуты dllimport и dllexport влияют на функции и данные.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Объявления и типы](../c-language/declarations-and-types.md)