---
title: "Объявления Typedef | Microsoft Docs"
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
  - "объявления, typedef"
  - "объявления typedef"
  - "типы [C], объявления"
ms.assetid: e92a3b82-9269-4bc6-834a-6f431ccac83e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Объявления Typedef
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объявление typedef — это объявление с typedef в качестве класса хранения.  Декларатор становится новым типом.  Объявления typedef можно использовать для создания более коротких или более понятных имен для типов, уже определенных в языке C или объявленных пользователем.  Имена typedef позволяют инкапсулировать детали реализации, которые могут измениться.  
  
 Объявление typedef интерпретируется точно так же, как и объявление переменной или функции, но идентификатор становится синонимом типа, а не принимает тип, указанный в объявлении.  
  
## Синтаксис  
 `declaration`:  
 *спецификаторы\-объявления список\-инициализаторов\-и\-деклараторов*  необ. **;**  
  
 *спецификаторы\-объявления*:  
 *спецификатор\-класса\-хранения спецификаторы\-объявления*  необ  
  
 *спецификатор\-типа спецификаторы\-объявления*  необ  
  
 *квалификатор\-типа спецификаторы\-объявления*  необ  
  
 *спецификатор\-класса\-хранения*:  
 `typedef`  
  
 *спецификатор\-типа*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **целое число**  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **без знака**  
  
 *спецификатор\-struct\-или\-union*  
  
 *спецификатор\-enum*  
  
 *имя\-typedef*  
  
 *имя\-определения\-типа*:  
 *identifier*  
  
 Обратите внимание, что объявление typedef не создает типы.  Оно создает синонимы для существующих типов или имена для типов, которые могут определяться другими способами.  Если имя typedef используется как спецификатор типа, его можно использовать в сочетании с определенными спецификаторами типа \(но нельзя использовать с другими спецификаторами\).  К допустимым модификаторам относятся **const** и `volatile`.  
  
 Имена typedef используют то же пространство имен, что и обычные идентификаторы \(дополнительные сведения см. в разделе [Пространства имен](../c-language/name-spaces.md)\).  Поэтому в программе может присутствовать имя typedef и идентификатор с тем же именем в локальной области.  Например:  
  
```  
typedef char FlagType;  
  
int main()  
{  
}  
  
int myproc( int )  
{  
    int FlagType;  
}  
```  
  
 При объявлении в локальной области идентификатора с тем же именем, что и имя typedef, или при объявлении члена структуры либо объединения в той же области или во внутренней области обязательно должен указываться спецификатор типа.  Следующий пример иллюстрирует это ограничение:  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 Чтобы повторно использовать имя `FlagType` для идентификатора, члена структуры или члена объединения, необходимо указать тип:  
  
```  
const int FlagType;  /* Type specifier required */  
```  
  
 Недостаточно написать  
  
```  
const FlagType;      /* Incomplete specification */  
```  
  
 поскольку `FlagType` воспринимается как часть типа, а не как заново объявляемый идентификатор.  Это объявление недопустимо, как и  
  
```  
int;  /* Illegal declaration */  
```  
  
 С помощью typedef можно объявить любой тип, включая типы указателей, функций и массивов.  Имя typedef для типа указателя на структуру или объединение можно объявить до определения типа структуры или объединения, если только определение находится в той же области видимости, что и объявление.  
  
 Имена typedef можно использовать, чтобы сделать код более понятным.  Все три следующих объявления `signal` задают один и тот же тип, причем в первом объявлении имена typedef не используются.  
  
```  
typedef void fv( int ), (*pfv)( int );  /* typedef declarations */  
  
void ( *signal( int, void (*) (int)) ) ( int );  
fv *signal( int, fv * );   /* Uses typedef type */  
pfv signal( int, pfv );    /* Uses typedef type */  
```  
  
## Примеры  
 В следующих примерах показаны объявления typedef:  
  
```  
typedef int WHOLE; /* Declares WHOLE to be a synonym for int */  
```  
  
 Обратите внимание, что теперь имя `WHOLE` может использоваться в объявлении переменных, например `WHOLE i;` или `const WHOLE i;`.  Однако объявление `long WHOLE i;` недопустимо.  
  
```  
typedef struct club   
{  
    char name[30];  
    int size, year;  
} GROUP;  
```  
  
 Этот оператор объявляет имя `GROUP` как тип структуры с тремя членами.  Поскольку также указан тег структуры, `club`, в объявлениях можно использовать как имя typedef \(`GROUP`\), так и тег структуры.  С тегом необходимо использовать ключевое слово struct; с именем typedef использование ключевого слова struct не допускается.  
  
```  
typedef GROUP *PG; /* Uses the previous typedef name   
                      to declare a pointer            */  
```  
  
 Тип `PG` объявлен как указатель на тип `GROUP`, который, в свою очередь, определен как тип структуры.  
  
```  
typedef void DRAWF( int, int );  
```  
  
 В этом примере задан тип `DRAWF` для функции, не возвращающей никакого значения и принимающей два аргумента int.  Это означает, например, что объявление  
  
```  
DRAWF box;   
```  
  
 эквивалентно объявлению  
  
```  
void box( int, int );  
```  
  
## См. также  
 [\(NOTINBUILD\)typedef Specifier](http://msdn.microsoft.com/ru-ru/cc96cf26-ba93-4179-951e-695d1f5fdcf1)