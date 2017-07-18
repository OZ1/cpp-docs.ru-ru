---
title: "Предупреждение (уровень 1) C4276 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4276
dev_langs:
- C++
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
caps.latest.revision: 7
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
ms.openlocfilehash: 88871206840e06fb06b90ed669f5684647bd5ce5
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4276"></a>Предупреждение компилятора (уровень 1) C4276
«функция»: не предоставлен прототип; предполагается отсутствие параметров  
  
 При получении адреса функции с [__stdcall](../../cpp/stdcall.md) соглашение о вызовах, необходимо предоставить прототип, чтобы компилятор мог создать декорированное имя функции. Поскольку *функция* не имеет прототипа, компилятор, создавая декорированное имя, предполагается, что функция не имеет параметров.