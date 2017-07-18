---
title: "Поддержка базы данных, мастер приложений MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.database"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Мастер приложений MFC, поддержка баз данных"
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Поддержка базы данных, мастер приложений MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

На этой странице представлены параметры, позволяющие указать уровень поддержки базы данных \(и источника данных, если необходимо\) для проекта.  
  
 **Поддержка базы данных**  
 Задает уровень поддержки базы данных для проекта.  
  
|Команда|Описание|  
|-------------|--------------|  
|**Нет**|Поддержка баз данных отсутствует.  Этот параметр используется по умолчанию.|  
|**Только файлы заголовков**|Предоставляет базовый уровень поддержки базы данных для приложения.<br /><br /> <ul><li>Если в разделе **Тип клиента** выбрана поддержка ODBC, мастер приложений MFC включает в проект файл заголовка AFXDB.H.  Он добавляет библиотеки, но не создает классы, определяемые базой данных.  Позднее можно создать наборы записей и использовать их для проверки и обновления записей.</li><li>Если в разделе **Тип клиента** выбрана поддержка ODBC, в проект включаются следующие файлы заголовков:<br /><br /> <ul><li>ATLBASE.H</li><li>AFXOLEDB.H</li><li>ATLPLUS.H</li></ul></li></ul>|  
|**Представление баз данных без поддержки файлов**|Включает файлы заголовков баз данных, библиотеки компоновки, представление записей и набор записей. \(Доступно только для приложений, у которых на странице [Тип приложения](../Topic/Application%20Type,%20MFC%20Application%20Wizard.md) выбран параметр **Поддержка архитектуры "документ\/представление"**.\) Этот параметр включает поддержку документа, но не поддержку сериализации.  При выборе включения представления базы данных необходимо указать источник данных.|  
|**Представление баз данных с поддержкой файлов**|Включает файлы заголовков баз данных, библиотеки компоновки, представление записей и набор записей. \(Доступно только для приложений, у которых на странице **Тип приложения** выбран параметр **Поддержка архитектуры "документ\/представление"**.\) Этот параметр поддерживает сериализацию документов, которую можно использовать, например, для обновления файла профиля пользователя.  Приложения баз данных обычно выполняются на основе записей, а не файлов, поэтому сериализация не требуется.  Однако можно найти особое применение для сериализации.  При выборе включения представления базы данных необходимо указать источник данных.|  
  
> [!NOTE]
>  Если в разделе **Поддержка базы данных** выбрать параметр **Представление баз данных без поддержки файлов** или **Представление баз данных с поддержкой файлов**, результат в окне классов будет отличаться в зависимости от выбора, сделанного в разделе **Тип клиента**, следующим образом:  
  
-   Если в разделе **Тип клиента** выбран параметр **ODBC**, то класс представления приложения является производным от [CRecordView](../../mfc/reference/crecordview-class.md).  Этот класс связан с производным от [CRecordset](../Topic/CRecordset%20Class.md) классом, который создается мастером приложений MFC.  Данный параметр предоставляет приложение с поддержкой форм, в котором представление записей используется для просмотра и обновления записей в наборе записей.  
  
-   Если в разделе **Тип клиента** выбран параметр **OLE DB**, то класс представления является производным от [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md) и связан с классом, производным от [CTable](../../data/oledb/ctable-class.md) или [CCommand](../../data/oledb/ccommand-class.md).  
  
 **Тип клиента**  
 Указывает, используются ли в проекте классы OLE DB или ODBC.  
  
|Команда|Описание|  
|-------------|--------------|  
|**OLE DB**|Если выбран этот параметр, нажмите кнопку **Источник данных**, чтобы вызвать мастер **свойств каналов передачи данных**, с помощью которого можно создать подключение к источнику данных OLE DB.|  
|**ODBC**|Если выбран этот параметр, нажмите кнопку **Источник данных**, чтобы вызвать мастер **выбора источника данных**, с помощью которого можно создать подключение к источнику данных ODBC.|  
  
 **Источник данных**  
 Нажмите кнопку **Источник данных**, чтобы установить источник данных, используя указанный драйвер или поставщика и базу данных.  Если в разделе **Тип клиента** выбран параметр OLE DB, при нажатии этой кнопки отображается диалоговое окно **Свойства связи с данными**.  Если в разделе **Тип клиента** выбран параметр ODBC, при нажатии этой кнопки отображается диалоговое окно **Выбрать источник данных**.  Этот параметр доступен только в том случае, если вы выбираете включение представления базы данных в приложение.  
  
|Команда|Описание|  
|-------------|--------------|  
|**Свойства связи с данными** \(OLE DB\)|Устанавливает указанный источник данных с использованием заданного поставщика OLE DB.  Необходимо указать поставщика OLE DB, расположение данных, источник данных, идентификатор входа и \(необязательно\) пароль.  Подробные сведения об этом диалоговом окне см. в разделе **Источник данных** в [мастере потребителей OLE DB библиотеки ATL](../../atl/reference/atl-ole-db-consumer-wizard.md).|  
|**Выбрать источник данных** \(ODBC\)|Устанавливает указанный источник данных с использованием заданного драйвера ODBC.  Необходимо выбрать имя источника данных, чтобы выбрать таблицу для источника данных.  Мастер выполняет привязку всех столбцов таблицы к переменным\-членам класса, производного от `CRecordset`.  Подробные сведения об этом диалоговом окне см. в разделе **Источник данных** в [мастере потребителей ODBC библиотеки MFC](../../mfc/reference/mfc-odbc-consumer-wizard.md).|  
  
> [!NOTE]
>  В предыдущих выпусках при нажатии кнопки **Источник данных** с одновременным удержанием клавиши Shift открывалось диалоговое окно "Открытие файла", в котором можно было выбрать файл канала передачи данных \(UDL\-файл\).  Эти функциональные возможности больше не поддерживаются.  
  
 **Создать класс базы данных с атрибутами**  
 Доступно только для клиентов OLE DB.  Указывает, используют ли классы баз данных атрибуты в создаваемом проекте.  
  
 **Привязать все столбцы**  
 Доступно только для клиентов ODBC.  Указывает, привязаны ли все столбцы выбранной таблицы.  Если этот флажок установлен, все столбцы привязаны; в противном случае столбцы не привязаны, и необходимо привязать их вручную в классе наборов записей.  
  
 **Тип**  
 Доступно только для клиентов ODBC.  Указывает, является ли набор записей динамическим подмножеством данных или моментальным снимком \(см. описание в приведенной ниже таблице\).  
  
|Команда|Описание|  
|-------------|--------------|  
|**Динамическое подмножество данных**|Указывает, что набор записей является динамическим подмножеством данных.  Динамическое подмножество является результатом запроса, предоставляющим индексированное представление в запрошенных данных базы данных.  Динамическое подмножество кэширует только интегральный индекс исходных данных и, таким образом, обеспечивает повышение производительности, по сравнению с моментальным снимком.  Индекс указывает непосредственно на каждую найденную в результате запроса запись и определяет, удалена ли запись.  Имеется также доступ к обновленным данным в запрошенных записях.|  
|Моментальный снимок|Указывает, что набор записей является моментальным снимком.  Моментальный снимок является результатом запроса и представлением базы данных в отдельно взятый момент времени.  Все найденные в результате запроса записи кэшируются, так что не видны изменения в исходных записях.|  
  
## См. также  
 [мастер приложений MFC](../Topic/MFC%20Application%20Wizard.md)