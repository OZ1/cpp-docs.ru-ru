---
title: "Автоматизация | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Automation servers, about Automation servers
- clients, Automation
- programmatic control [MFC]
- properties [MFC], Automation
- MFC, COM support
- OLE Automation
- Automation
- servers [MFC], Automation
- Automation clients
- sample applications [MFC], Automation
- methods [MFC]
- passing parameters, Automation
- Automation method [MFC]
- Automation, passing parameters
- Automation property [MFC]
- MFC COM, Automation
- methods [MFC], Automation
ms.assetid: 329117f0-c1aa-4680-a901-bfb71277dfba
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 31406418b14c6b3008fc734d53be6ca6319df8c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="automation"></a>автоматизация
Автоматизация (ранее известная как OLE-автоматизация) позволяет одному приложению управлять объектами, реализованными в другом приложении, или выделять объекты для управления.  
  
 [Сервер автоматизации](../mfc/automation-servers.md) — это приложение (тип COM-сервера), предоставляющее свои функции через COM-интерфейсы другим приложениям, называемым [клиентами автоматизации](../mfc/automation-clients.md). Это позволяет клиентам автоматизировать некоторые функции путем прямого доступа к объектам и использования предоставляемых ими возможностей.  
  
 Серверы и клиенты автоматизации используют COM-интерфейсы, которые всегда являются производными от `IDispatch` , и принимают и возвращают определенный набор типов данных, называемых типами автоматизации. Предоставив методы и свойства, доступные из других приложений, можно автоматизировать любой объект, который позволяет обращаться к интерфейсу автоматизации. Автоматизация доступна для OLE- и COM-объектов. Автоматизированный объект может быть локальным или удаленным (на другом компьютере, доступном по сети), поэтому существует две категории автоматизации.  
  
-   Автоматизация (локальная).  
  
-   [Удаленная автоматизация](../mfc/remote-automation.md) (через сеть с использованием DCOM).  
  
 Предоставление доступа к объектам полезно в том случае, когда приложения предлагают функциональные возможности, полезные для других приложений. Например элемент управления ActiveX — это тип сервера автоматизации. Приложение, в котором размещается элемент управления ActiveX, является клиентом автоматизации этого элемента управления.  
  
 Другой пример: текстовый процессор может предоставлять свои функции по проверке орфографии другим программам. Благодаря доступу к объектам поставщики способны совершенствовать свои приложения с помощью готовых функциональных возможностей других приложений. Таким образом, автоматизация применяет некоторые принципы объектно-ориентированного программирования, такие как возможность многократного использования и инкапсуляции, на уровне самих приложений.  
  
 Особое значение имеет поддержка, предоставляемая автоматизацией пользователям и поставщикам решений. За счет доступа к функциональным возможностям приложений через стандартный и четко определенный интерфейс автоматизации позволяет создавать комплексные решения на одном общем языке программирования, например Visual Basic, а не прибегать к различным связанным с конкретными приложениями макроязыкам.  
  
 Многие коммерческие приложения, например Microsoft Excel и Microsoft Visual C++, допускают автоматизацию большей части своих функциональных возможностей. Например в Visual C++, можно написать макросы VBScript для автоматизации построений, аспектов редактирования кода или задач отладки.  
  
##  <a name="_core_passing_parameters_in_automation"></a> Передача параметров в автоматизации  
 Одна из сложностей при создании методов автоматизации заключается в обеспечении согласованного безопасного механизма для передачи данных между серверами и клиентами автоматизации. Для передачи данных автоматизация использует тип **VARIANT** . Тип **VARIANT** является помеченным объединением. У него есть элемент данных для значения (это анонимное объединение C++) и элемент данных, указывающий тип сведений, хранящихся в объединении. Тип **VARIANT** поддерживает ряд стандартных типов данных: 2- и 4-байтовые целые числа, 4- и 8-байтовые числа с плавающей запятой, строки и логические значения. Кроме того, он поддерживает типы `HRESULT` (коды ошибок OLE), **CURRENCY** (числовой тип с фиксированной запятой) и **DATE** (абсолютное значение даты и времени), а также указатели на интерфейсы **IUnknown** и `IDispatch` .  
  
 Тип **VARIANT** инкапсулирован в класс [COleVariant](../mfc/reference/colevariant-class.md) . Поддерживаемые классы **CURRENCY** и **DATE** инкапсулированы в классы [COleCurrency](../mfc/reference/colecurrency-class.md) и [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) .  
  
## <a name="automation-samples"></a>Примеры автоматизации  
  
-   [AUTOCLIK](../visual-cpp-samples.md) Используйте этот пример, чтобы освоить приемы автоматизации и изучить основы удаленной автоматизации.  
  
-   [ACDUAL](../visual-cpp-samples.md) Добавляет сдвоенные интерфейсы в приложение сервера автоматизации.  
  
-   [CALCDRIV](../visual-cpp-samples.md) Приложение клиента автоматизации для реализации MFCCALC.  
  
-   [INPROC](../visual-cpp-samples.md) Демонстрирует приложение внутрипроцессного сервера автоматизации.  
  
-   [CALCDRIV](../visual-cpp-samples.md) Приложение клиента автоматизации для реализации INPROC.  
  
-   [MFCCALC](../visual-cpp-samples.md) Демонстрирует приложение клиента автоматизации.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Клиенты автоматизации](../mfc/automation-clients.md)  
  
-   [Серверы автоматизации](../mfc/automation-servers.md)  
  
-   [Удаленная автоматизация](../mfc/remote-automation.md)  
  
-   [OLE](../mfc/ole-in-mfc.md)  
  
-   [Active - технология](../mfc/mfc-com.md)  
  
## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать  
  
-   [Добавление класса автоматизации](../mfc/automation-servers.md)  
  
-   [Использование библиотек типов](../mfc/automation-clients-using-type-libraries.md)  
   
-   [Доступ к серверам автоматизации](../mfc/automation-servers.md)  
  
-   [Написание клиентов автоматизации на C++](../mfc/automation-clients.md)  
  
## <a name="see-also"></a>См. также  
 [MFC COM](../mfc/mfc-com.md)