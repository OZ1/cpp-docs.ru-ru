---
title: "Ошибка компилятора C3373 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3373
dev_langs:
- C++
helpviewer_keywords:
- C3373
ms.assetid: 6e7586c3-1a15-4773-ad20-f90090a400dc
caps.latest.revision: 5
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
ms.openlocfilehash: 0b7422f2ad87e55cf49410e70788c7139dcfc7ef
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3373"></a>Ошибка компилятора C3373
атрибут "атрибут" не принимает аргументов, кроме случая применения к компонентным классам  
  
 Некоторые атрибуты могут применяться к нескольким конструкциям С++, однако использование аргументов для атрибутов допустимо только в некоторых конструкциях.  
  
 Следующий пример приводит к возникновению ошибки C3373:  
  
```  
// C3373.cpp  
#include <windows.h>  
  
[module(name="MyModule")];  
  
[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface  
{  
   // arguments to source and restricted are not allowed when  
   // these attributes are applied to an interface  
   [source(IMyIface)] HRESULT f1();  
   [restricted(IMyIface)] HRESULT f2(); // C3373  
};  
  
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f) ]  
class CMyClass : public IMyIface {  
};  
  
int main() {  
}  
```