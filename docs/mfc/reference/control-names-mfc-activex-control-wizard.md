---
title: "Имена элементов управления, мастер элементов управления ActiveX MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.ctl.names
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 28ef331cb66ee184c4bc104fedddf69e9296367c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="control-names-mfc-activex-control-wizard"></a>Имена элементов управления, мастер элементов управления ActiveX MFC
Укажите имена для класса элемента управления и класса страницы свойств, имена типов и идентификаторы типов для элемента управления. За исключением элемента **короткое имя**, все поля, которые могут изменяться независимо друг от друга. Если изменить текст для **короткое имя**, это изменение отражается в имена всех других полей на этой странице. Эти принципы именования позволяют легко определить по вы все имена разработки элементов управления.  
  
 **Краткое имя**  
 Укажите сокращенное имя для элемента управления. По умолчанию это имя основано на имени проекта, указанный в **новый проект** диалоговое окно. Имя определяет имена классов, имена типов и идентификаторы типов, можно только после изменения этих полей по отдельности.  
  
 **Имя класса элемента управления**  
 По умолчанию имя класса элемента управления основан на короткое имя с `C` префиксом и `Ctrl` как суффикс. Например, если элемент управления короткое имя должен `Price`, имя класса элемента управления — `CPriceCtrl`.  
  
 **H-файл элемента управления**  
 По умолчанию имени файла заголовка берется краткое имя с `Ctrl` суффиксом и `.h` расширением файла. Например, если элемент управления короткое имя должен `Price`, имя файла заголовка будет `PriceCtrl.h`. Имя в этом поле должно соответствовать имени класса элемента управления.  
  
 **CPP-файл элемента управления**  
 По умолчанию имени файла заголовка берется краткое имя с `Ctrl` суффиксом и `.cpp` расширением файла. Например, если элемент управления короткое имя должен `Price`, имя файла заголовка будет `PriceCtrl.cpp`. В этом поле имя должно соответствовать имени заголовка.  
  
 **Имя типа элемента управления**  
 По умолчанию имя типа элемента управления основан на короткое имя, за которым следует `Control`. Например, если элемент управления короткое имя должен `Price`, является именем типа класса элемента управления `Price Control`. Если изменить значение в этом поле, убедитесь, что имя указывает наследования.  
  
 **Идентификатор типа элемента управления**  
 Задает идентификатор типа класса элемента управления. Элемент управления эта строка записывается в реестр, при добавлении в проект. Приложения контейнера использовать данную строку для создания экземпляра элемента управления.  
  
 По умолчанию идентификатор типа элемента управления основан на имени проекта, которое вы указываете в **новый проект** диалоговое окно и короткое имя. Это имя должно совпадать с именем типа.  
  
 По умолчанию идентификатор типа элемента управления выглядит следующим образом:  
  
 *ProjectName.ShortName*CTRL.1.  
  
 Если изменить краткое имя в этом диалоговом окне, идентификатор типа элемента управления выглядит следующим образом:  
  
 *ProjectName.NewShortName*CTRL.1.  
  
 **Имя класса PropPage**  
 По умолчанию имя класса страницы свойств основан на короткое имя с `C` префиксом и `PropPage` как суффикс. Например, если элемент управления короткое имя должен `Price`, имя класса страницы свойств будет `CPricePropPage`. Это имя должно соответствовать имени класса элемента управления, с добавлением `PropPage`.  
  
 **PropPage h-файл**  
 По умолчанию имя файла заголовка страницы свойств основано на короткое имя с как `PropPage` суффиксом и `.h` расширением файла. Например, если элемент управления короткое имя должен `Price`, имя файла заголовка страницы свойств будет `PricePropPage.h`. Это имя должно соответствовать имени класса.  
  
 **PropPage CPP-файл**  
 По умолчанию имя файла реализации страницы свойств основано на короткое имя с как `PropPage` суффиксом и `.cpp` расширением файла. Например, если элемент управления короткое имя должен `Price`, имя файла заголовка страницы свойств будет `PricePropPage.cpp`. Это имя должно соответствовать имени файла заголовка.  
  
 **Имя типа PropPage**  
 По умолчанию имени типа страницы свойств берется краткое имя, за которым следует `Property Page`. Например, если элемент управления короткое имя должен `Price`, имя типа страницы свойств будет `Price Property Page`. Если изменить значение в этом поле, убедитесь, что имя указывает на класс элемента управления.  
  
 **Идентификатор типа PropPage**  
 Задает идентификатор класса страницы свойств. Эта строка записывается элемента управления в реестре при применении к проекту. Эта строка используется в приложении-контейнере для создания экземпляра страницы свойств элемента управления.  
  
 По умолчанию идентификатор типа страницы свойств основан на имени проекта, которое вы указываете в **новый проект** диалоговое окно и короткое имя. Это имя должно совпадать с именем типа.  
  
 По умолчанию идентификатор типа страницы свойств выглядит следующим образом:  
  
 *ProjectName.ShortName*PropPage.1  
  
 Если изменить краткое имя в этом диалоговом окне, идентификатор типа страницы свойств выглядит следующим образом:  
  
 *ProjectName.NewShortName*PropPage.1  
  
## <a name="see-also"></a>См. также  
 [Мастер элементов управления ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Параметры приложения, мастер элементов управления ActiveX MFC](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [Параметры элементов управления, мастер элементов управления ActiveX MFC](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)   
 [Типы файлов, создаваемых для проектов Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md)

