---
title: Ошибка компилятора C3850 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3850
dev_langs:
- C++
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f5c79f1ab90348ea234e006ae6838d5e80e46c3e
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="compiler-error-c3850"></a>Ошибка компилятора C3850
char: универсальное имя символа определяет недопустимый символ  
  
 Символы, представленные универсальными именами символов, должны представлять допустимые кодовые точки Юникода в диапазоне 0–10FFFF. Универсальное имя символа не может содержать значение в суррогатном диапазоне Юникода (D800–DFFF) или закодированной суррогатной паре. Компилятор создает суррогатную пару из допустимой кодовой точки автоматически.  
  
 В коде, скомпилированном как C, универсальное имя символа не должно представлять символ в диапазоне 0000–009F включительно, за исключением символов 0024 ("$"), 0040 ("@") и 0060 ("`").  
  
 В коде, скомпилированном как C++, универсальное имя символа может использовать любую допустимую кодовую точку Юникода в строковом или символьном литерале. За пределами литерала универсальное имя символа не должно представлять управляющий символ в диапазонах 0000–001F или 007F–009F (включительно для обоих диапазонов) или элемент основной кодировки исходного кода.  Дополнительные сведения см. в разделе [наборов символов](../../cpp/character-sets.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано возникновение ошибки C3850 и приводятся сведения по ее устранению.  
  
```cpp  
// C3850.cpp  
int main() {  
   int \u0019 = 0;   // C3850, not in allowed range for an identifier  
   const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair  
   const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point  
}  
```