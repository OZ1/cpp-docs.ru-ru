---
title: "Редактор сочетаний клавиш | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.accelerator.F1
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [Visual Studio], accelerator key
- accelerator keys
- resource editors, Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
- Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e078dbd3dc8d462ef4bca6e6f1056afb9ce8724c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="accelerator-editor"></a>Редактор сочетаний клавиш
Таблица сочетаний клавиш представляет собой ресурс Windows, содержащий список сочетаний клавиш и связанных с ними идентификаторов команд. В программе можно использовать несколько таблиц сочетаний клавиш.  
  
 Обычно сочетания клавиш используются для ускорения доступа к командам программы, также доступным в меню или на панели инструментов. Но таблицу сочетаний клавиш можно также использовать, чтобы определить сочетания клавиш для команд, с которыми не связаны никакие объекты пользовательского интерфейса.  
  
 Для подключения команд сочетаний клавиш к коду можно использовать [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925) .  
  
 Редактор сочетаний клавиш позволяет выполнять следующие действия:  
  
-   [задавать свойства сочетаний клавиш;](../windows/setting-accelerator-properties.md)  
  
-   [привязывать сочетания клавиш к пунктам меню;](../windows/associating-an-accelerator-key-with-a-menu-item.md)  
  
-   [редактировать таблицы сочетаний клавиш;](../windows/editing-accelerator-tables.md)  
  
-   [использовать предопределенные сочетания клавиш.](../windows/predefined-accelerator-keys.md)  
  
    > [!TIP]
    >  При использовании редактора сочетаний клавиш можно щелкнуть правой кнопкой мыши, чтобы вывести контекстное меню с часто используемыми командами. Доступные команды зависят от объекта, на который наведен указатель мыши.  
  
    > [!NOTE]
    >  Операционная система Windows не позволяет создавать пустые таблицы сочетаний клавиш. Если вы создадите таблицу сочетаний клавиш, не содержащую записей, она будет автоматически удалена при сохранении.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редакторы ресурсов](../windows/resource-editors.md)

