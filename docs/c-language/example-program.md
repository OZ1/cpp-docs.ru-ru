---
title: "Пример программы | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: fc22ef82-9caa-425f-b201-2891bc123d1f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 903e4890bfad23310f0663fde52af4065e78486e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="example-program"></a>Пример программы
Следующая исходная программа на языке C состоит из двух файлов исходного кода. В ней показаны различные объявления и определения, возможные в программе на языке C. В последующих разделах этого документа описывается, как создавать такие объявления, определения и инициализации, и как использовать ключевые слова C, например **static** и `extern`. Функция `printf` объявлена в файле заголовка C STDIO.H.  
  
 Предполагается, что функции `main` и `max` находятся в разных файлах, а выполнение программы начинается с функции `main`. Перед функцией `main` не выполняются никакие явные пользовательские функции.  
  
```  
/*****************************************************************  
                    FILE1.C - main function  
*****************************************************************/  
  
#define ONE     1  
#define TWO     2  
#define THREE   3  
#include <stdio.h>  
  
int a = 1;                       // Defining declarations      
int b = 2;                       //  of external variables      
  
extern int max( int a, int b );  // Function prototype          
  
int main()                       // Function definition         
{                                //  for main function          
    int c;                       // Definitions for      
    int d;                       //  two uninitialized  
                                 //  local variables  
  
    extern int u;                // Referencing declaration     
                                 //  of external variable       
                                 //  defined elsewhere          
    static int v;                // Definition of variable      
                                 //  with continuous lifetime   
  
    int w = ONE, x = TWO, y = THREE;  
    int z = 0;  
  
    z = max( x, y );             // Executable statements      
    w = max( z, w );  
    printf_s( "%d %d\n", z, w );  
    return 0;  
}  
  
/****************************************************************  
            FILE2.C - definition of max function  
****************************************************************/  
  
int max( int a, int b )          // Note formal parameters are     
                                 //  included in function header   
{  
    if( a > b )  
        return( a );  
    else  
        return( b );  
}  
```  
  
 Файл FILE1.C содержит прототип для функции `max`. Объявления этого типа иногда называются "опережающими", поскольку функция объявляется до ее использования. Определение функции `main` содержит вызовы функции `max`.  
  
 Строки, начинающиеся с `#define`, представляют собой директивы препроцессора. В соответствии с этими директивами препроцессор заменяет идентификаторы `ONE`, `TWO` и `THREE` в файле FILE1. C цифрами `1`, `2` и `3`, соответственно. Однако эти директивы не применяются к файлу FILE2.C, который компилируется отдельно, а затем компонуется с файлом FILE1.C. Строка, начинающаяся с `#include`, содержит указание компилятору на включение файла STDIO.H, содержащего прототип для функции `printf`. [Директивы препроцессора](../preprocessor/preprocessor-directives.md) рассматриваются в *справочнике по препроцессору*.  
  
 В файле FILE1.C используются определяющие объявления для инициализации глобальных переменных `a` и `b`. Локальные переменные `c` и `d` объявлены, но не инициализированы. Для всех этих переменных выделена память. Статические и внешние переменные, `u` и `v`, автоматически инициализируются значением 0. Поэтому при объявлении значимые значения содержат только переменные `a`, `b`, `u` и `v`, которые явно или неявно инициализированы. Файл FILE2.C содержит определение функции `max`. Это определение соответствует вызовам функции `max` из файла FILE1.C.  
  
 Время существования и область видимости идентификаторов рассматриваются в статье [Время существования, область, видимость и компоновка](../c-language/lifetime-scope-visibility-and-linkage.md). Дополнительные сведения о функциях вы найдете в [разделе, посвященном функциям](../c-language/functions-c.md).  
  
## <a name="see-also"></a>См. также  
 [Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)