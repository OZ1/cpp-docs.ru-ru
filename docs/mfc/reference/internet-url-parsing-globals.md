---
title: "Глобальные объекты разбора URL-адрес Интернета и вспомогательные методы | Документы Microsoft"
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.isapi
dev_langs:
- C++
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
caps.latest.revision: 14
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
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 947ef992d58895e4638d9ffe77fca973cea8eada
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="internet-url-parsing-globals-and-helpers"></a>Глобальные объекты разбора URL-адрес Интернета и вспомогательные методы
Когда клиент отправляет запрос к Интернет-серверу, можно использовать один из глобальные объекты разбора URL-адрес для получения сведений о клиенте. Вспомогательные функции предоставляют другие функциональные возможности Интернета.
  
## <a name="internet-url-parsing-globals"></a>Глобальные объекты разбора URL-адресов  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|Анализирует строку URL-адреса и возвращает тип службы и его компонентов.|  
|[AfxParseURLEx](#afxparseurlex)|Анализирует строку URL-адреса и возвращает тип службы и его компонентов, а также указания имени пользователя и пароля.|  

## <a name="other-internet-helpers"></a>Другие вспомогательные Интернета
|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|Создает исключение, связанные с подключением к Интернету.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Определяет тип дескриптора Интернета.|
  
##  <a name="afxparseurl"></a>AfxParseURL  
 Этот глобальный используется в [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort); 
```  
  
### <a name="parameters"></a>Параметры  
 *pstrURL*  
 Указатель на строку, содержащую URL-адрес для синтаксического анализа.  
  
 `dwServiceType`  
 Указывает тип службы IIS. Ниже приведены возможные значения.  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Первый сегмент URL-адрес после типа службы.  
  
 `strObject`  
 Объект, который ссылается URL-адрес (может быть пустым).  
  
 `nPort`  
 Определить из объекта или сервер частей URL-адрес, если они существуют.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если синтаксический анализ URL-адрес был успешно завершен; в противном случае — 0, если он пуст или не содержит известный тип службы Интернета.  
  
### <a name="remarks"></a>Примечания  
 Он выполняет синтаксический анализ строки URL-адреса и возвращает тип службы и его компонентов.  
  
 Например `AfxParseURL` выполняет синтаксический анализ URL-адреса в формате **service://server/dir/dir/object.ext:port** и возвращает его компоненты, которые хранятся следующим образом:  
  
 `strServer`== «server»  
  
 `strObject`== «/ dir/dir/object/object.ext»  
  
 `nPort`== #port  
  
 `dwServiceType`== #service  
  
> [!NOTE]
>  Чтобы вызвать эту функцию, ваш проект должен включать AFXINET. З.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxinet.h  
  
##  <a name="afxparseurlex"></a>AfxParseURLEx  
 Это является расширенной версией [AfxParseURL](#afxparseurl) и используется в [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort,  
    CString& strUsername,  
    CString& strPassword,  
    DWORD dwFlags = 0); 
```  
  
### <a name="parameters"></a>Параметры  
 *pstrURL*  
 Указатель на строку, содержащую URL-адрес для синтаксического анализа.  
  
 `dwServiceType`  
 Указывает тип службы IIS. Ниже приведены возможные значения.  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Первый сегмент URL-адрес после типа службы.  
  
 `strObject`  
 Объект, который ссылается URL-адрес (может быть пустым).  
  
 `nPort`  
 Определить из объекта или сервер частей URL-адрес, если они существуют.  
  
 *названием strUsername*  
 Ссылку на `CString` объект, содержащий имя пользователя.  
  
 `strPassword`  
 Ссылку на `CString` объект, содержащий пароль пользователя.  
  
 `dwFlags`  
 Флаги управления как выполнить синтаксический анализ URL-адрес. Может быть сочетанием следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|**ICU_DECODE**|Преобразуйте % XX escape-последовательности символов.|  
|**ICU_NO_ENCODE**|Преобразования небезопасных символов в escape-последовательность.|  
|**ICU_NO_META**|Не удаляйте последовательности метаданных (например, «\». и «\»..) по URL-адресу.|  
|**ICU_ENCODE_SPACES_ONLY**|Кодирование только пробелы.|  
|**ICU_BROWSER_MODE**|Не кодирование или декодирование символов после «#» или "и не удаляет пробелы после ''. Если это значение не задано, кодируется весь URL-адрес и удалить конечные пробелы.|  
  
 Если используется значение по умолчанию MFC, являющийся флаги не, функция преобразует всех небезопасных символов и последовательностей meta (такие как \\., \.., и \\...) для escape-последовательности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если синтаксический анализ URL-адрес был успешно завершен; в противном случае — 0, если он пуст или не содержит известный тип службы Интернета.  
  
### <a name="remarks"></a>Примечания  
 Он выполняет синтаксический анализ строки URL-адреса и возвращает тип службы и его компонентов, а также указания имени пользователя и пароля. Флаги указывают, каким образом небезопасных символов обрабатываются.  
  
> [!NOTE]
>  Чтобы вызвать эту функцию, ваш проект должен включать AFXINET. З.  

### <a name="requirements"></a>Требования  
  **Заголовок** afxinet.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
 
## <a name="afxgetinternethandletype"></a>AfxGetInternetHandleType
Используйте эту глобальную функцию для определения типа дескриптора Интернета.  
   
### <a name="syntax"></a>Синтаксис  
  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );  
```
### <a name="parameters"></a>Параметры  
 `hQuery`  
 Дескриптор для запроса на Интернет.  
   
### <a name="return-value"></a>Возвращаемое значение  
 Любые типы служб Интернета, определяемый WININET. З. В разделе «Примечания» в список этих служб Интернета. Если маркер имеет значение NULL или не распознан, функция возвращает AFX_INET_SERVICE_UNK.  
   
### <a name="remarks"></a>Примечания  
 В следующем списке перечислены возможные типы Интернета, возвращенные `AfxGetInternetHandleType`.  
  
-   INTERNET_HANDLE_TYPE_INTERNET  
  
-   INTERNET_HANDLE_TYPE_CONNECT_FTP  
  
-   INTERNET_HANDLE_TYPE_CONNECT_GOPHER  
  
-   INTERNET_HANDLE_TYPE_CONNECT_HTTP  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_HTTP_REQUEST  
  
> [!NOTE]
>  Чтобы вызвать эту функцию, ваш проект должен включать AFXINET. З.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
 
## <a name="afxthrowinternetexception"></a>AfxThrowInternetException
Создает исключение Интернета.  
   
### <a name="syntax"></a>Синтаксис    
```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );  
```
### <a name="parameters"></a>Параметры  
 `dwContext`  
 Идентификатор контекста для операции, которая вызвала ошибку. Значение по умолчанию `dwContext` изначально указывается в [CInternetSession](cinternetsession-class.md) и передается [CInternetConnection](cinternetconnection-class.md)- и [классе CInternetFile](cinternetfile-class.md)-производные классы. Для определенных операций, выполняемых на подключение или файл, обычно переопределить значение по умолчанию с `dwContext` свой собственный. Это значение возвращается для [CInternetSession::OnStatusCallback](cinternetsession-class.md#onstatuscallback) для определения состояния конкретной операции. 
  
 `dwError`  
 Ошибки, вызвавшей исключение.  
   
### <a name="remarks"></a>Примечания  
 Вы несете ответственность за определение причины, по коду ошибки операционной системы.  
  
> [!NOTE]
>  Чтобы вызвать эту функцию, ваш проект должен включать AFXINET. З.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [Класс CInternetException](cinternetexception-class.md)   
 [THROW](#throw)
 

