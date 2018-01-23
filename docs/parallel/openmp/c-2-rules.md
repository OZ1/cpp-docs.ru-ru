---
title: "C.2 правила | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4d52fef7-3eb7-4480-a335-8ed48681092b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e5efa8d0e7cf4118362b7695bafcd4710b4021f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="c2-rules"></a>C.2 Правила
Нотация описан в разделе 6.1 стандарта C. В этом приложении грамматики показывает расширения Грамматика базовый язык для директивы OpenMP C и C++.  
  
 **/\*в C++ (ISO/IEC 14882:1998)\*/**  
  
 *оператор объявления*:  
  
 *statement*  
  
 *Директива OpenMP*  
  
 *оператор объявления оператора*  
  
 *оператор объявления openmp директива*  
  
 **/\*в C90 (ISO/IEC 9899: 1990)\*/**  
  
 *statement-list*:  
  
 *statement*  
  
 *Директива OpenMP*  
  
 *statement-list statement*  
  
 *список операторов openmp директива*  
  
 **/\*в C99 (ISO/IEC 9899: 1999)\*/**  
  
 *элемент блока*:  
  
 *declaration*  
  
 *statement*  
  
 *Директива OpenMP*  
  
 *statement*:  
  
 **/\*стандартные инструкции\*/**  
  
 *Конструкция OpenMP*  
  
 *Конструкция OpenMP*:  
  
 *Конструкция Parallel*  
  
 *для конструкции*  
  
 *создать разделы*  
  
 *Конструкция одного*  
  
 *параллельный для конструкции*  
  
 *параллельно, разделы, конструкция*  
  
 *Образец construc*  
  
 *Конструкция Critical*  
  
 *Конструкция atomic*  
  
 *упорядоченные конструкция*  
  
 *Директива OpenMP*:  
  
 *Барьер директива*  
  
 *Директива Flush*  
  
 *структурированный блок*:  
  
 *statement*  
  
 *Конструкция Parallel*:  
  
 *структурированный блок параллельного директива*  
  
 *Директива параллельного*:  
  
 **# Директива #pragma omp parallel***параллельного предложение*optseq *новой строки*   
  
 *предложение параллельного*:  
  
 *Уникальный параллельного предложения*  
  
 *предложение данных*  
  
 *Уникальный параллельного предложение*:  
  
 **Если (** *выражение* **)**  
  
 **num_threads (** *выражение* **)**  
  
 *для конструкции*:  
  
 *оператор итерации для директивы*  
  
 *для директивы*:  
  
 **# Директива #pragma omp для** *для предложения*optseq *новой строки*  
  
 *для предложения*:  
  
 *Уникальный для предложения*  
  
 *предложение данных*  
  
 **nowait**  
  
 *Уникальный для предложения*:  
  
 **упорядоченные**  
  
 **расписание (** *вид расписания* **)**  
  
 **расписание (** *вид расписания* **,** *выражение* **)**  
  
 *Вид расписания*:  
  
 **static**  
  
 **dynamic**  
  
 **Интерактивная**  
  
 **Среда выполнения**  
  
 *Конструкция разделов*:  
  
 *раздел области разделов директива*  
  
 *Директива разделов*:  
  
 **# Директива #pragma omp разделы** *разделы предложение*optseq *новой строки*  
  
 *предложение разделов*:  
  
 *предложение данных*  
  
 **nowait**  
  
 *раздел области*:  
  
 *{раздел последовательность}*  
  
 *раздел последовательности*:  
  
 *директивы Section*необ *структурированный блок*  
  
 *раздел последовательности директивы section структурированного блока*  
  
 *директивы Section*:  
  
 **# Директива #pragma omp раздел** *новой строки*  
  
 *Конструкция одного*:  
  
 *структурированный блок одной директивы*  
  
 *Директива одного*:  
  
 **# Директива #pragma omp один** *одного предложения*optseq *новой строки*  
  
 *предложение одного*:  
  
 *предложение данных*  
  
 **nowait**  
  
 *параллельный для конструкции*:  
  
 *оператор итерации параллельного для директивы*  
  
 *параллельный для директивы*:  
  
 **# Директива #pragma omp parallel для** *параллельного для предложения*optseq *новой строки*  
  
 *параллельный для предложения*:  
  
 *Уникальный параллельного предложения*  
  
 *Уникальный для предложения*  
  
 *предложение данных*  
  
 *параллельный разделах конструкция*:  
  
 *раздел параллельного разделах директива области видимости*  
  
 *параллельный разделах директива*:  
  
 **# директивы #pragma omp parallel разделы** *параллельного разделах предложения*optseq *новой строки*  
  
 *параллельный разделах предложения*:  
  
 *Уникальный параллельного предложения*  
  
 *предложение данных*  
  
 *Конструкция master*:  
  
 *структурированный блок master директива*  
  
 *Директива master*:  
  
 **# Директива #pragma omp master** *новой строки*  
  
 *Конструкция Critical*:  
  
 *структурированный блок директиву Critical*  
  
 *директиву Critical*:  
  
 **# Директива #pragma omp критических** *область фразу*необ *новой строки*  
  
 *Регион фразу*:  
  
 *(идентификатор)*  
  
 *Директива барьера*:  
  
 **# Директива #pragma omp барьера** *новой строки*  
  
 *Конструкция atomic*:  
  
 *оператор выражения атомарная директива*  
  
 *атомарная директива*:  
  
 **# Директива #pragma omp atomic** *новой строки*  
  
 *Директива Flush*:  
  
 **# Директива #pragma omp очистки** *переменных Сброс*необ *новой строки*  
  
 *Сброс переменных*:  
  
 *(переменная список)*  
  
 *упорядоченные конструкция*:  
  
 *структурированный блок упорядоченные директива*  
  
 *упорядоченные директива*:  
  
 **Директива #pragma omp # упорядоченные** *новой строки*  
  
 *объявление*:  
  
 **/\*Стандартная объявления\*/**  
  
 *Директива threadprivate*  
  
 *Директива threadprivate*:  
  
 **# Директива #pragma omp threadprivate (** *списка переменной***)** *новой строки*   
  
 *предложение данных*:  
  
 **закрытый (** *списка переменной* **)**  
  
 **copyprivate (***списка переменной***)**   
  
 **firstprivate (***списка переменной***)**   
  
 **lastprivate (** *списка переменной***)**   
  
 **Общие (** *списка переменной* **)**  
  
 **по умолчанию (совместно используемые)**  
  
 **по умолчанию (нет)**  
  
 **Уменьшение (***оператором редукции***:***списка переменной***)**   
  
 **copyin (***списка переменной***)**   
  
 *оператором редукции*:  
  
 *Один из*:  **+  \* -& ^ &#124; & & &#124; &#124;**  
  
 **/\*в языке C\*/**  
  
 *Список переменной*:  
  
 *identifier*  
  
 *Список переменной* **,** *идентификатор*  
  
 **/\*в C++\*/**  
  
 *Список переменной*:  
  
 *Идентификатор выражения*  
  
 *Список переменной* **,** *идентификатор выражения*