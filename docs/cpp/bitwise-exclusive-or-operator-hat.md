---
title: "Побитовое исключающее или оператор: ^ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6d6bd80c7144ea3f4a2288e07b7801612ed62efd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bitwise-exclusive-or-operator-"></a>Битовый оператор ИЛИ (исключительное): ^
## <a name="syntax"></a>Синтаксис  
  
```  
expression ^ expression  
```  
  
## <a name="remarks"></a>Примечания  
Оператор побитового исключающего или (**^**) сравнивает каждый бит первого операнда с соответствующим битом второго операнда. Если один бит равен 0, а другой равен 1, соответствующий бит результата устанавливается равным 1. в противном случае — нулю.  
  
Оба операнда оператора побитового эксклюзивного ИЛИ должны быть целочисленного типа. Обычные арифметические преобразования, описанные в [стандартные преобразования](standard-conversions.md) применяются к операндам.  
  
## <a name="operator-keyword-for-"></a>Ключевое слово оператора ^  
**Xor** оператор является текстовым эквивалентом  **^** . Существует два способа доступа к **xor** оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).  
  
## <a name="example"></a>Пример  
  
```cpp  
// expre_Bitwise_Exclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise exclusive OR  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xFFFF;      // pattern 1111 ...  
  
   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   


