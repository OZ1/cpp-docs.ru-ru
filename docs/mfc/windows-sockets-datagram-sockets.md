---
title: "Сокеты Windows: Сокеты датаграмм | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8c19280645edad0d449708434ebbc0ee646e981
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-datagram-sockets"></a>Сокеты Windows. Сокеты датаграмм
В этой статье описывается сокеты датаграмм, один из двух доступных типов Windows Socket. (Другой тип — [сокета потока](../mfc/windows-sockets-stream-sockets.md).)  
  
 Сокеты датаграмм поддерживают двунаправленный поток данных, не обязательно быть виртуализации или unduplicated. Также датаграммы не гарантируется на надежность; они не поступают. Датаграмм может поступать не по порядку и возможно дублирование, но сохраняются записи границ в данных, при условии, что записи, меньше, чем ограничение на размер внутреннего получателя. Вы несете ответственность за управление виртуализации и надежности. (Надежность подход может быть хорошим в локальной сети [LAN], но меньше и т. д. глобальной сети [WAN], например Интернета.)  
  
 Датаграммы являются «без установления соединения», то есть без явного подключения; Отправить сообщение с датаграммами для заданного сокета и может получать сообщения из указанного сокета.  
  
 Примером сокета датаграмм является приложение, которое сохраняет системными часами в сети синхронизированы. Это показывает это дополнительная возможность сокеты датаграмм в по крайней мере некоторые параметры: широковещательная рассылка сообщений по большое количество сетевых адресов.  
  
 Сокеты датаграмм лучше, чем сокеты потока для записи данных. Дополнительные сведения о сокеты датаграмм см. в спецификации Windows Sockets, доступных в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)   
 [Сокеты Windows. Фон](../mfc/windows-sockets-background.md)

