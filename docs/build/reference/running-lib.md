---
title: "Запуск программы LIB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.TargetMachine"
  - "Lib"
  - "VC.Project.VCLibrarianTool.PrintProgress"
  - "VC.Project.VCLibrarianTool.SuppressStartupBanner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ - файлы команд"
  - "/MACHINE - параметр целевой платформы"
  - "/NOLOGO - параметр управления библиотекой"
  - "/VERBOSE - параметр управления библиотекой"
  - "файлы команд с двоеточием"
  - "командные файлы"
  - "командные файлы, LIB"
  - "спецификатор - тире"
  - "косая черта - спецификатор"
  - "LIB [C++], запуск программы LIB"
  - "MACHINE параметр целевой платформы"
  - "-MACHINE параметр целевой платформы"
  - "NOLOGO - параметр управления библиотекой"
  - "-NOLOGO - параметр управления библиотекой"
  - "точка с запятой, командные файлы"
  - "косая черта (/)"
  - "VERBOSE - параметр управления библиотекой"
  - "-VERBOSE - параметр управления библиотекой"
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Запуск программы LIB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Для управления программой LIB доступно множество параметров командной строки  
  
## Командная строка LIB  
 Для выполнения программы LIB введите команду `lib` с последующими параметрами и именами файлов задач, для выполнения которых вы используете программу LIB.  LIB также принимает строчные команды в командных файлах, которые описаны в следующем разделе.  LIB не использует переменную среды.  
  
> [!NOTE]
>  Если вы привыкли к инструментам LINK32.exe и LIB32.exe, предоставленным в Microsoft Win32 Software Development Kit для Windows NT, вы, возможно, уже пользовались либо командой `link32 -lib`, либо `lib32` для управления библиотеками и для создания библиотек импорта.  Убедитесь в том, что в файлы makefile и пакетные файлы внесены необходимые изменения для использования команд `lib`.  
  
## Командные файлы LIB  
 Вы можете передать аргументы командной строки программе LIB в командном файле с помощью следующего синтаксиса:  
  
```  
LIB @commandfile  
```  
  
 Файл `commandfile` является текстовым.  Не допускается использование пробелов или знаков табуляции между символом "@" и именем файла.  Расширение по умолчанию отсутствует; вам необходимо задать полное имя файла, включая какое\-либо расширение.  Подстановочные знаки использоваться не могут.  Вам необходимо указать абсолютный или относительный путь с именем файла.  
  
 В качестве разделителей аргументов в командном файле можно использовать пробелы или знаки табуляции, как в командной строке; также можно использовать символы новой строки.  Для обозначения комментариев используется точка с запятой \(;\).  Программа LIB игнорирует весь текст после точки с запятой и до конца строки.  
  
 Вы можете указать либо всю командную строку, либо ее часть в командном файле и использовать более одного командного файла в команде LIB.  Программа LIB принимает ввод из командного файла, будто он вводится посредством командной строки, с соблюдением позиций.  Командные файлы не могут быть вложены в другие файлы.  Если не используется параметр \/NOLOGO, то программа LIB отображает содержание командного файла на экране.  
  
## Использование параметров LIB  
 Имени параметра предшествует спецификатор, которым является либо знак дефиса \( – \), либо косая черта \( \/ \).  Нельзя сокращать имена параметров.  Некоторые параметры принимают аргумент, который отделяется двоеточием \(:\).  Не допускается использование пробелов и символов табуляции внутри параметра.  Параметры в командной строке следует разделять одним или несколькими пробелами и символами табуляции.  Имена параметров и их ключевые слова или аргументы имен файлов не чувствительны к регистру, но идентификаторы, используемые в качестве аргументов, чувствительны к регистру.  Программа LIB обрабатывает параметры в порядке их следования в командной строке и в командном файле.  Если параметр повторяется с различными аргументами, преимущество имеет последний.  
  
 Следующие параметры применяются ко всем режимам LIB:  
  
 \/ERRORREPORT \[NONE &#124; PROMPT &#124; QUEUE &#124; SEND\]  
 Если происходит сбой во время выполнения lib.exe, вы можете воспользоваться параметром \/ERRORREPORT для отправки информации о внутренних ошибках в адрес Microsoft.  
  
 Дополнительные сведения о параметре \/ERRORREPORT см. в разделе [Параметр \/errorReport \(отчет о внутренних ошибках компилятора\)](../Topic/-errorReport%20\(Report%20Internal%20Compiler%20Errors\).md).  
  
 \/LTCG  
 Инициирует построение библиотеки с помощью создания кода времени компоновки.  Дополнительные сведения см. в описании [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  
  
 \/MACHINE  
 Задание целевой платформы для программы.  Обычно необходимость в параметре \/MACHINE отсутствует.  Тип компьютера определяется программой LIB из OBJ\-файлов.  Однако в некоторых случаях программа LIB не может определить тип компьютера и выдает сообщение об ошибке.  При возникновении такой ошибки следует задать параметр \/MACHINE.  В режиме \/EXTRACT этот параметр используется исключительно для проверки.  Для просмотра доступных типов компьютеров воспользуйтесь командой `lib /?` .  
  
 \/NOLOGO  
 Отключает вывод программой LIB уведомления об авторских правах и номере версии, а также отображение команд командного файла.  
  
 \/VERBOSE  
 Отображает подробные сведения о ходе сеанса, включая имена добавляемых OBJ\-файлов.  Информация отправляется на стандартный поток вывода и может быть перенаправлена в файл.  
  
 \/WX\[:NO\]  
 Обработка предупреждений, как ошибок.  Дополнительные сведения см. в разделе [\/WX \(Обрабатывать предупреждения компоновщика как ошибки\)](../../build/reference/wx-treat-linker-warnings-as-errors.md).  
  
 Остальные параметры применимы только в отдельных режимах работы LIB.  Эти параметры рассмотрены в разделах, посвященных конкретным режимам.  
  
## См. также  
 [Справочник по LIB](../../build/reference/lib-reference.md)