---
title: "Неустранимая ошибка NMAKE U1100 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1100
dev_langs:
- C++
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d1e2dad3730a7b2b6ec42b6ad469352beff49f2b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="nmake-fatal-error-u1100"></a>Неустранимая ошибка NMAKE U1100
макрос «имя макроса» недопустим в контексте пакетного правила «правило»  
  
 NMAKE создает эту ошибку, если блок команд правила пакетного режима прямо или косвенно ссылается на макрос специальный файл, который не является $<.></.>  
  
 $< is the only allowed macro for batch-mode rules. is="" the="" only="" allowed="" macro="" for="" batch-mode=""></ is the only allowed macro for batch-mode rules.>