---
title: "multimap::key_compare (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::key_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_compare - элемент [STL/CLR]"
ms.assetid: a6b04cfa-fef9-44dc-a328-1208fd01899f
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multimap::key_compare (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Порядок делегат для 2 ключей.  
  
## Синтаксис  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>  
    key_compare;  
```  
  
## Заметки  
 Тип синоним для делегата, определяет порядок ключевых своих аргументов.  
  
## Пример  
  
```  
// cliext_multimap_key_compare.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    Mymultimap::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mymultimap c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
  **сравнение \(L'a, L'а\) \= false**  
**сравнение \(L'a, L'б\) \= true**  
**сравнение \(L'b, L'а\) \= false**  
**сравнение \(L'a, L'а\) \= false**  
**сравнение \(L'a, L'б\) \= false**  
**сравнение \(L'b, L'а\) \= true**   
## Требования  
 **Заголовок:**\<cliext\/map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)   
 [multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)   
 [multimap::value\_compare](../Topic/multimap::value_compare%20\(STL-CLR\).md)