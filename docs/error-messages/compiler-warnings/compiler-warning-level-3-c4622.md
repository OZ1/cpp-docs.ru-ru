---
title: "Предупреждение (уровень 3) C4622 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4622
dev_langs:
- C++
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 1bfc4c631f1f35ebd9a63a965e9d87854e5720bb
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4622"></a>Предупреждение компилятора (уровень 3) C4622
перезапись отладочной информации, сформированной во время создания предкомпилированного заголовка в объектном файле: "файл"  
  
 Информация CodeView в указанном файле была утеряна, при компиляции с [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (использование предкомпилированных заголовков).  
  
 Переименуйте объектный файл (с помощью [/Fo](../../build/reference/fo-object-file-name.md)) при создании или использовании предкомпилированного заголовка и выполните компоновку с использованием нового объектного файла.