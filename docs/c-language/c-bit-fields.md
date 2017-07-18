---
title: "Битовые поля в C | Microsoft Docs"
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
  - "битовые поля"
  - "разряды"
ms.assetid: 9faf74c4-7fd5-4b44-ad18-04485193d06e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Битовые поля в C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представлять собой заданное количество бит, т. е. "битовое поле", могут не только деклараторы для членов структуры или объединения, но и декларатор структуры. Указание его длины отделяется от декларатора имени поля двоеточием.  Битовое поле интерпретируется как целочисленный тип.  
  
## Синтаксис  
 *декларатор\-структуры*:  
 *декларатор*  
  
 *спецификатор\-типа декларатор*  необяз. **:** *константное\-выражение*  
  
 *Константное\-выражение* задает ширину поля в битах.  *Спецификатор\-типа* для `declarator` должен иметь тип `unsigned int`, **signed int** или `int`, а *константное\-выражение* должно быть неотрицательными целочисленным значением.  Если указано значение 0, то объявление не содержит `declarator`.  Массивы битовых полей, указатели на битовые поля, а также функции, возвращающие битовые поля, не допускаются.  Необязательный параметр `declarator` задает имя битового поля.  Битовые поля могут объявляться только в рамках структуры.  Оператор взятия адреса \(**&**\) не может применяться к компонентам битового поля.  
  
 Создавать ссылки на неименованные битовые поля невозможно; их содержимое во время выполнения непредсказуемо.  Их можно использовать в качестве фиктивных полей в целях выравнивания.  Неименованное битовое поле, для которого задана ширина 0, гарантирует, что область хранения для члена, который следует за ним в *списке\-объявлений\-структуры*, начнется на границе `int`.  
  
 Битовые поля должны иметь достаточную длину, чтобы вмещать в себя битовый шаблон.  Например, следующие два оператора недопустимы.  
  
```  
short a:17;        /* Illegal! */  
int long y:33;     /* Illegal! */  
```  
  
 В этом примере определен двумерный массив структур с именем `screen`.  
  
```  
struct   
{  
    unsigned short icon : 8;  
    unsigned short color : 4;  
    unsigned short underline : 1;  
    unsigned short blink : 1;  
} screen[25][80];  
```  
  
 Массив содержит 2000 элементов.  Каждый элемент представляет собой отдельную структуру с четырьмя членами, каждый из которых представляет собой битовое поле: `icon`, `color`, `underline` и `blink`.  Размер каждой структуры равен 2 байтам.  
  
 Битовые поля имеют одну и ту же семантику, что и целочисленный тип.  Это означает, что битовое поле используется в выражениях точно так же, как использовалась бы переменная того же базового типа, независимо от количества битов в битовом поле.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Битовые поля, определенные как `int`, обрабатываются как знаковые.  Расширения Microsoft к стандарту ANSI C допускают битовые поля типов `char` и **long** \(как **signed**, так и `unsigned`\).  Неименованные битовые поля с базовым типом **long**, **short** или `char` \(будь то **signed** или `unsigned`\) принудительно устанавливают выравнивание по границе с учетом базового типа.  
  
 Битовые поля в целом числе назначаются в направлении от младшего разряда к старшему.  В приведенном ниже коде  
  
```  
struct mybitfields  
{  
    unsigned short a : 4;  
    unsigned short b : 5;  
    unsigned short c : 7;  
} test;  
  
int main( void );  
{  
    test.a = 2;  
    test.b = 31;  
    test.c = 0;  
}  
```  
  
 биты размещаются следующим образом:  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 Поскольку в процессорах семейства 8086 младший байт целочисленных значений размещается перед старшим байтом, указанное выше целое число `0x01F2` будет храниться в физической памяти как `0xF2`, за которым следует `0x01`.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Объявления структур](../c-language/structure-declarations.md)