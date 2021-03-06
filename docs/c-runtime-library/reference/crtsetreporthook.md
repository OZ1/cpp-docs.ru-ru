---
title: "_CrtSetReportHook | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtSetReportHook
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _CrtSetReportHook
- CrtSetReportHook
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8c7b3a8954c39e8157834297ab5ac3a747420af8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook
Устанавливает определяемую клиентом функцию отчетов путем ее прикрепления к процессу создания отчетов среды выполнения языка C (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_CRT_REPORT_HOOK _CrtSetReportHook(   
   _CRT_REPORT_HOOK reportHook   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `reportHook`  
 Новая определяемая клиентом функция отчетов, которую необходимо прикрепить к процессу создания отчетов среды выполнения языка C.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает предыдущую определяемую клиентом функцию отчетов.  
  
## <a name="remarks"></a>Примечания  
 `_CrtSetReportHook` позволяет приложению использовать собственную функцию отчетов в процессе создания отчетов отладочной библиотеки времени выполнения языка C. В результате всякий раз, когда для создания отчета отладки вызывается функция [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md), сначала вызывается функция отчетов приложения. Эта функциональность позволяет приложению выполнять такие операции, как фильтрация отчетов отладки, чтобы сосредоточиться на выделениях памяти конкретного типа или отправлять отчет в пункты назначения, которые недоступны при использовании `_CrtDbgReport`. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtSetReportHook` удаляются на этапе предварительной обработки.  
  
 Более надежную версию функции `_CrtSetReportHook` см. в разделе [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md).  
  
 Функция `_CrtSetReportHook` устанавливает новую определяемую клиентом функцию отчетов, указанную в параметре `reportHook`, и возвращает предыдущую определенную клиентом функцию-обработчик. В следующем примере показано, как должен быть объявлен прототип определяемого клиентом обработчика отчетов:  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 где `reportType` — тип отчета отладки (`_CRT_WARN`, `_CRT_ERROR` или `_CRT_ASSERT`), `message` — полностью собранное пользовательское отладочное сообщение, которое будет содержаться в отчете, и `returnValue` — значение, указанное определяемой клиентом функцией отчетов, которое должно возвращаться функцией `_CrtDbgReport`. Полное описание доступных типов отчетов см. в описании функции [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md).  
  
 Если определяемая клиентом функция отчетов полностью обрабатывает сообщение отладки и дальнейшая выдача отчета не требуется, функция должна возвращать значение `TRUE`. Если функция возвращает значение `FALSE`, для создания отчета отладки с использованием текущих параметров типа, режима и файла отчета вызывается функция `_CrtDbgReport`. Кроме того, указав возвращаемое значение функции `_CrtDbgReport` в параметре `returnValue`, приложение может контролировать, происходит ли прерывание при отладке. Полное описание настройки и создания отчета об отладке см. в описании функций `_CrtSetReportMode`, [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) и `_CrtDbgReport`.  
  
 Дополнительные сведения о других допускающих подключение функциях среды выполнения и написании собственных определяемых клиентом функциях-ловушках см. в разделе [Написание функций отладочных ловушек](/visualstudio/debugger/debug-hook-function-writing).  
  
> [!NOTE]
>  Если приложение компилировано с параметром `/clr` и функция отчетов вызывается после того, как приложение выходит из функции main, среда CLR вызывает исключение, если функция отчетов вызывает какие-либо функции CRT.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtSetReportHook`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Подпрограммы отладки](../../c-runtime-library/debug-routines.md)   
 [_CrtGetReportHook](../../c-runtime-library/reference/crtgetreporthook.md)