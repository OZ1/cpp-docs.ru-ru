---
title: "Сообщения AFX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SB_LINELEFT
- SB_THUMBTRACK
- AFX_TOOLTIP_TYPE_EDIT
- AFX_WM_ON_HSCROLL
- SB_PAGERIGHT
- AFX_WM_RESETPROMPT
- AFX_WM_CHANGE_RIBBON_CATEGORY
- AFX_TOOLTIP_TYPE_MINIFRAME
- AFX_WM_CUSTOMIZETOOLBAR
- AFX_WM_CHANGE_ACTIVE_TAB
- AFX_WM_ACCGETOBJECT
- AFX_WM_TOOLBARMENU
- AFX_TOOLTIP_TYPE_DOCKBAR
- AFX_WM_CUSTOMIZEHELP
- AFX_WM_ON_GET_TAB_TOOLTIP
- AFX_WM_ON_RIBBON_CUSTOMIZE
- AFX_WM_ON_DRAGCOMPLETE
- AFX_WM_RESETTOOLBAR
- AFX_WM_ON_MOVETOTABGROUP
- AFX_WM_CHECKEMPTYMINIFRAME
- AFX_WM_GETDOCUMENTCOLORS
- SB_RIGHT
- AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU
- AFX_WM_ACCGETSTATE
- SB_PAGELEFT
- SB_ENDSCROLL
- AFX_WM_ON_CANCELTABMOVE
- AFX_TOOLTIP_TYPE_TAB
- AFX_WM_WINDOW_HELP
- AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM
- AFX_WM_SHOWREGULARMENU
- AFX_TOOLTIP_TYPE_TOOLBAR
- AFX_WM_CHANGE_CURRENT_FOLDER
- AFX_WM_UPDATETOOLTIPS
- AFX_WM_ON_MOVE_TAB
- AFX_WM_CHANGING_ACTIVE_TAB
- AFX_WM_RESETMENU
- AFX_WM_GETDRAGBOUNDS
- AFX_WM_RESETCONTEXTMENU
- AFX_TOOLTIP_TYPE_BUTTON
- AFX_WM_ON_CLOSEPOPUPWINDOW
- AFX_TOOLTIP_TYPE_TOOLBOX
- AFX_WM_CHANGEVISUALMANAGER
- SB_LINERIGHT
- AFX_WM_ON_RENAME_TAB
- AFX_TOOLTIP_TYPE_DEFAULT
- AFX_WM_ON_TABGROUPMOUSEMOVE
- SB_LEFT
- AFX_WM_DELETETOOLBAR
- AFX_WM_PROPERTY_CHANGED
- AFX_TOOLTIP_TYPE_ALL
- AFX_WM_ACCHITTEST
- AFX_WM_ON_AFTER_SHELL_COMMAND
- AFX_WM_ON_PRESS_CLOSE_BUTTON
- AFX_WM_RESETKEYBOARD
- AFX_WM_ON_MOVETABCOMPLETE
- AFX_WM_CREATETOOLBAR
- SB_THUMBPOSITION
- AFX_WM_POSTSETPREVIEWFRAME
dev_langs:
- C++
helpviewer_keywords:
- AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41f300f285fb4eaf1a6154a21cbbabc0253fc730
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="afx-messages"></a>Сообщения AFX
Эти сообщения используются в MFC.  
  
## <a name="messages"></a>Сообщения  
 В следующей таблице перечислены сообщения, которые используются в библиотеке MFC:  
  
||||||  
|-|-|-|-|-|  
|Сообщение|Описание:|[in] `wParam`|`lParam`(Все параметры являются [in] Если не указано иное.)|Возвращаемое значение|  
|AFX_WM_ACCGETOBJECT|Не используется.|Не используется.|Неприменимо.|Неприменимо.|  
|AFX_WM_ACCGETSTATE|Используется для поддержки специальных возможностей. Отправить это сообщение, чтобы `CMFCPopupMenu` или `CMFCRibbonPanelMenu` для получения состояния текущего элемента.|Индекс элемента, который может быть кнопки меню или разделителей.|Не используется.|Состояние элемента. Это значение -1, если индекс является недопустимым, 0, если эта кнопка меню имеет отсутствуют специальные атрибуты. В противном случае это сочетание следующих флагов:<br /><br /> TBBS_DISABLED — элемент отключен<br /><br /> TBBS_CHECKED: флажок элемента<br /><br /> TBBS_BUTTON — элемент является стандартной кнопки<br /><br /> TBBS_PRESSED: кнопка нажата<br /><br /> TBBS_INDETERMINATE — неопределенное состояние<br /><br /> TBBS_SEPARATOR - вместо кнопки меню, этот элемент создает разделения между другими элементами меню|  
|AFX_WM_CHANGE_ACTIVE_TAB|Платформа отправляет сообщение в элемент управления панели изменяемого размера элемента управления. Обработать это сообщение, чтобы получать уведомления из `CMFCTabCtrl` объектов, когда пользователь изменяет активной вкладке.|Индекс вкладки.|Не используется.|Ненулевое значение.|  
|AFX_WM_CHANGE_CURRENT_FOLDER|Платформа отправляет сообщение на родительский объект `CMFCShellListCtrl` когда пользователь изменил текущей папки.|Не используется.|Не используется.|Не используется.|  
|AFX_WM_CHANGEVISUALMANAGER|Платформа отправляет сообщение для всех фреймов, когда пользователь изменяет текущий диспетчер Visual. В ответ на данное сообщение окно фрейма пересчитывает ее области и настраивает другие параметры, при необходимости. Можно обработать сообщение AFX_WM_CHANGEVISUALMANAGER в приложении, если требуется получать уведомления о данном событии. Необходимо вызвать метод базового класса обработчика (`OnChangeVisualManager`) чтобы убедиться, что платформа внутренней происходит обработка этого события.|Не используется.|Не используется.|Не используется.|  
|AFX_WM_CHANGING_ACTIVE_TAB|Отправлены на родительский объект `CMFCTabCtrl` объекта.  Обработать это сообщение, если вы хотите получать уведомления от `CMFCTabCtrl` объекты, если пользователь сбросит вкладки.|Индекс вкладки, которая активируется.|Не используется.|Ненулевое значение.|  
|AFX_WM_CHECKEMPTYMINIFRAME|Только для внутреннего использования.|Неприменимо.|Неприменимо.|Неприменимо.|  
|AFX_WM_CREATETOOLBAR|Отправленные `CMFCToolBarsListPropertyPage` когда пользователь создает новую панель инструментов в процессе настройки. Можно обработать это сообщение, чтобы создать экземпляр пользовательского объекта CMFCToolBar производным. Если обработать это сообщение и создать собственную панель инструментов, можно пропустите вызов обработчика по умолчанию.|Не используется.|Указатель на строку, содержащую имя панели инструментов.|Указатель на только что созданный панели инструментов. Значение NULL указывает отмены создания панели инструментов.|  
|AFX_WM_CUSTOMIZEHELP|Страница свойств настройки отправленных фрейма главного окна `CMFCToolbarCustomize Dialog` при нажатии **справки** клавиши F1 или кнопки.|Указывает на активную страницу набора свойств настройки.|Указатель на объект `CMFCToolbarCustomize Dialog`.|Ноль.|  
|AFX_WM_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize Dialog` Отправляет это сообщение, чтобы уведомить родительского фрейма, пользователь создает новую панель инструментов.|`TRUE`При запуске настройки `FALSE` после завершения настройки.|Не используется.|Ноль.|  
|AFX_WM_DELETETOOLBAR|Когда пользователь собирается удалить панель инструментов в режиме настройки отправляется фрейма главного окна.<br /><br /> Обработать это сообщение для выполнения дополнительных действий, когда пользователь удаляет панель инструментов в режим настройки. Вам также следует вызвать обработчик по умолчанию (`OnToolbarDelete`), которая удаляет панели инструментов. Обработчик по умолчанию возвращает значение, указывающее, возможна ли удаление панели инструментов.|Не используется.|Указатель на `CMFCToolBar` объект для удаления.|Ненулевое значение, если не удается удалить панель инструментов; в противном случае — 0.|  
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton`отправляет сообщение в основную область окна для извлечения цвета документа.|Не используется.|[in, out] Указатель на `CList<COLORREF, COLORREF>` объект.|Ноль.|  
|AFX_WM_GETDRAGBOUNDS|Только для внутреннего использования.|Неприменимо.|Неприменимо.|Неприменимо.|  
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|Отправляется фрейма главного окна, когда пользователь выделяет элемент списка ленты.|Индекс выделенного элемента|Указатель на`CMFCBaseRibbonElement`|Не используется.|  
|AFX_WM_ON_AFTER_SHELL_COMMAND|Отправляемые является родительским для `CMFCShellListCtrl` или `CMFCShellTreeCtrl` определяет, когда пользователь завершает выполнение команды операционной системы.|Идентификатор команды, выполняемые пользователем|Не используется.|Если приложение обрабатывает это сообщение, оно должно возвращать ноль.|  
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|Платформа родительского ленты отправляет это сообщение перед отображением контекстного меню. Можно обработать это сообщение и в любое время изменить всплывающих меню.|Не используется.|Указатель на`CMFCBaseRibbonElement`|Не используется.|  
|AFX_WM_ON_CANCELTABMOVE|Только для внутреннего использования.|Неприменимо.|Неприменимо.||  
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|Платформа отправляет сообщение главного фрейма в том случае, когда пользователь изменяет активную категорию элемента управления ленты.|Не используется.|Указатель на `CMFCRibbonBar` которого категория была изменена.|Не используется.|  
|AFX_WM_ON_CLOSEPOPUPWINDOW|Платформа отправляет это сообщение, чтобы сообщить об `CMFCDesktopAlertWnd` что окно является будет закрыта.|Не используется.|Указатель на `CMFCDesktopAlertWnd` объект.|Не используется.|  
|AFX_WM_ON_DRAGCOMPLETE|Только для внутреннего использования.|Неприменимо.|Неприменимо.|Неприменимо.|  
|AFX_WM_ON_GET_TAB_TOOLTIP|Когда окно вкладки собирается отображения всплывающей подсказки для вкладки, если включены настраиваемые подсказки отправляется фрейма главного окна.|Не используется.|Указатель на `CMFCTabToolTipInfo` структуры.|Не используется.|  
|AFX_WM_ON_HSCROLL|Отправить в регулируемым панели управления. Обработать это сообщение, чтобы получать уведомления из `CMFCTabCtrl` объектов при возникновении события прокрутки в мини-приложение с вкладками горизонтальной полосы прокрутки.|Младшее слово указывает, что значение панель прокрутки, указывающее пользователя прокрутка запроса.  Дополнительные сведения см. в приведенной ниже таблице.|Не используется.|Ненулевое значение.|  
|AFX_WM_ON_MOVE_TAB|Отправляемые родительского окна с вкладками, когда пользователь перетаскивает вкладки на новое место.|Отсчитываемый от нуля индекс вкладки в исходное положение.|[out] Отсчитываемый от нуля индекс вкладки в новое место.|Ноль.|  
|AFX_WM_ON_MOVETABCOMPLETE|Только для внутреннего использования.|Неприменимо.|Неприменимо.|Неприменимо.|  
|AFX_WM_ON_MOVETOTABGROUP|Отправляется фрейма главного окна, когда пользователь перемещает дочернего окна MDI из одной группы с вкладками в другую.|Дескриптор окна с вкладками (`CMFCTabCtrl`), из которого был удален дочернего окна MDI.|[out] Дескриптор окна с вкладками (`CMFCTabCtrl`) для уже есть дочернее окно MDI.|Не обрабатывается.|  
|AFX_WM_ON_PRESS_CLOSE_BUTTON|Отправляемые является родительским для `CDockablePane` при щелчке **закрыть** кнопки в заголовке панели элементов управления.|Не используется.|Указатель на закрепляемую панель, на котором пользователь щелкнул **закрыть** кнопки.|`TRUE`Если область не может быть закрыт; в противном случае — значение FALSE.|  
|AFX_WM_ON_RENAME_TAB|Отправленные родительского окна с вкладками после пользователь переименован вкладки для редактирования.|Отсчитываемый от нуля индекс переименованный вкладки.|[out] Указатель на строку, содержащую имя новой вкладки.|Ненулевое значение, если приложение обрабатывает сообщение; Платформа приведет к отключению вызов `CMFCBaseTabCtrl::SetTabLabel`.  Если возвращается нуль, затем `CMFCBaseTabCtrl::SetTabLabel` вызывается платформой.|  
|AFX_WM_ON_RIBBON_CUSTOMIZE|Когда пользователь начинает настройки отправлено родительского фрейма. Если вы хотите отображать собственное диалоговое окно настройки обработать это сообщение.|Не используется.|Указатель на элемент управления на ленте для специальной обработки.|Ненулевое значение, если приложение обрабатывает это сообщение и отображает свое собственное диалоговое окно настройки. Если приложение возвращает ноль, платформа отобразит диалоговое окно настроек, встроенных.|  
|AFX_WM_ON_TABGROUPMOUSEMOVE|Только для внутреннего использования.|Неприменимо.|Неприменимо.|Неприменимо.|  
|AFX_WM_POSTSETPREVIEWFRAME|Предупреждения главного фрейма, что пользователь изменил режим предварительного просмотра|`TRUE`Показывает, что задан режим предварительного просмотра. `FALSE`Указывает, что отключен, режим предварительного просмотра печати.|Не используется.|Не используется.|  
|AFX_WM_PROPERTY_CHANGED|Посылается владельцу элемента управления сетки свойств (`CMFCPropertyGridCtrl`) когда пользователь изменяет значение выбранного свойства.|Идентификатор элемента управления списка свойств.|Указатель на свойства (`CMFCPropertyGridProperty`), изменен.|Не используется.|  
|AFX_WM_RESETCONTEXTMENU|Когда пользователь сбрасывает контекстное меню во время настройки отправляется фрейма главного окна.|Идентификатор ресурса в контекстном меню.|Указатель на текущий контекстное меню `CMFCPopupMenu`.|Не используется.|  
|AFX_WM_RESETKEYBOARD|Платформа отправляет это сообщение фрейма главного окна, когда пользователь сбрасывает все сочетания клавиш во время настройки.|Не используется.|Не используется.|Не используется.|  
|AFX_WM_RESETMENU|Платформа отправляет сообщение с владельцем меню (окно фрейма) когда пользователь сбрасывает меню фрейма приложения во время настройки|Идентификатор ресурса меню|Не используется.|Не используется.|  
|AFX_WM_RESETPROMPT|Платформа отправляет сообщение, если сброс пользователя в панели инструментов на панели инструментов настраиваемое диалоговое окно. Обработчик по умолчанию отображает окно сообщения с запросом ли пользователь хочет сбрасывать панели инструментов.|Не используется.|Не используется.|Не используется.|  
|AFX_WM_RESETTOOLBAR|Объект `CMFCToolBar` объект отправляет это сообщение, когда панель инструментов восстанавливается в исходное состояние, то есть, загруженных из ресурсов. Обработать это сообщение снова ввести кнопки панели инструментов, классы являются производными от `CMFCToolbarButton`. Дополнительные сведения см. в разделе `CMFCToolbarComboBoxButton`.|Идентификатор ресурса панели инструментов, состояние которого была восстановлена.|Не используется.|Ноль.|  
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton`его владельцу объекта отправляет сообщение, когда пользователь нажимает кнопку Обычное меню. Обработать это сообщение при каждом использовании `CMFCToolbarMenuButton` для отображения всплывающего меню, когда пользователь нажимает кнопку.|Идентификатор команды кнопки, которая отправляет сообщения.|Экранные координаты курсора. Младшее слово указывает по оси x. Старшее слово задает координату по оси y.|Не используется.|  
|AFX_WM_TOOLBARMENU|Отправляемые фрейма главного окна при отпускании правой кнопки мыши, если указатель мыши находится в области клиента или неклиентской области.|Не используется.|Экранные координаты указателя мыши. Младшее слово указывает по оси x. Старшее слово задает координату по оси y.|Нуль, если приложение обрабатывает сообщение; в противном случае — ненулевое значение.|  
|AFX_WM_UPDATETOOLTIPS|Отправляется для всех владельцев всплывающей подсказки, чтобы указать, следует заново создавать их всплывающих подсказок.|Тип элемента управления, который должен обработать данное сообщение. См. Далее в этом разделе список возможных значений в таблице.|Не используется.|Не используется.|  
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog`отправляет сообщение родительского фрейма, когда пользователь щелкает **справки** кнопку или переходит в режим справки, нажав кнопку **справки** клавиши F1 или кнопки заголовка.|Не используется.|Указатель на экземпляр `CMFCWindowsManagerDialog`.|Не используется.|  
  
 Следующая таблица показывает значения для младшее слово `lParam` параметр метода AFX_WM_HSCROLL:  
  
|||  
|-|-|  
|Значение|Значение|  
|SB_ENDSCROLL|Пользователь завершает прокрутки.|  
|SB_LEFT|Пользователь выполняет прокрутку в левом верхнем углу.|  
|SB_RIGHT|Пользователь выполняет прокрутку в правом нижнем углу.|  
|SB_LINELEFT|Пользователь выполняет прокрутку влево на одну единицу.|  
|SB_LINERIGHT|Пользователь выполняет прокрутку вправо на одну единицу.|  
|SB_PAGELEFT|Пользователь выполняет прокрутку влево по ширине окна.|  
|SB_PAGERIGHT|Пользователь выполняет прокрутку вправо по ширине окна.|  
|SB_THUMBPOSITION|У пользователя есть перетащить полосы прокрутки (бегунком) и освобождения кнопки мыши. Старшее слово указывает положение полосы прокрутки в конце операции перетаскивания.|  
|SB_THUMBTRACK|Пользователь перетаскивает полосу прокрутки. AFX_WM_ON_HSCROLL сообщение отправляется с этим значением несколько раз, пока пользователь отпускает кнопку мыши. Старшее слово указывает на позицию, к которому перемещенного полосы прокрутки.|  
  
> [!NOTE]
>  Старшие слова `lParam` параметр задает текущее положение полосы прокрутки, если младшее слово SB_THUMBPOSITION или SB_THUMBTRACK; в противном случае это слово не используется.  
  
 В следующей таблице перечислены значения флага для `lParam` AFX_WM_UPDATETOOLTIPS сообщения:  
  
|||  
|-|-|  
|Flag|Значение|  
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|  
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|  
|AFX_TOOLTIP_TYPE_TAB|0x0004|  
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|  
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|  
|AFX_TOOLTIP_TYPE_EDIT|0x0020|  
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|  
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|  
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
