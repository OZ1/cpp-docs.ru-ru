---
title: pgomgr | Документы Microsoft
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 743665bbe0ee9c3df08d197d203e95d08542f613
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2018
---
# <a name="pgomgr"></a>pgomgr

Добавляет данные профиля из одного или нескольких файлов PGC в PGD-файл.

## <a name="syntax"></a>Синтаксис

> **pgomgr** [*options*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>Параметры

*options*<br/>
Можно указать следующие параметры для **pgomgr**:

- **/ help** или **/?** Выводит доступную **pgomgr** параметры.

- **/ clear** вызывает PGD-файл очистить все данные профиля. Нельзя указать .pgc файл появляется, когда **/clear** указано.

- **/ detail** отображает подробную статистику, включая сведения о действии диаграмм потока.

- **/ summary** отображает по функциям статистики.

- **/ unique** при использовании с **/summary**, внутренних имен функций для отображения. Значение по умолчанию, когда **/ unique** не используется, то для отображать имена объявление функции.

- **/ merge**[**: *** n*] в результате данные в PGC-файл или файлы для добавления в PGD-файл. Необязательный параметр *n*, позволяет указать, что данные должны быть добавлены *n* раз. Например, если сценарий должен done шесть раз для отражения того, как часто выполняется клиентами, можно один раз выполнить тестовый запуск и добавить его в PGD-файл в шесть раз с **pgomgr /merge:6**.

*pgcfiles*<br/>
Один или несколько PGC-файлов, данные профиля, которые необходимо объединить в PGD-файл. Можно указать один или несколько PGC-файлов. Если не указан, все файлы .pgc **pgomgr** выполняет слияние всех файлов, имена которых совпадают с PGD-файла.

*pgdFile* PGD-файл, в который слияние данных из PGC-файл или файлы.

## <a name="remarks"></a>Примечания

> [!NOTE]
> Это средство можно запустить только из командной строки разработчика Visual Studio. В системной командной строке или проводнике это невозможно.

## <a name="example"></a>Пример

В этом примере команда удаляет файл myapp.pgd данных профиля:

`pgomgr /clear myapp.pgd`

В этом примере команда добавляет данные профиля в файле myapp1.pgc в PGD-файл три раза:

`pgomgr /merge:3 myapp1.pgc myapp.pgd`

В этом примере добавляется файл myapp.pgd данных профиля из всех файлов myapp # .pgc.

`pgomgr -merge myapp1.pgd`

## <a name="see-also"></a>См. также

[Профильная оптимизация](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>
