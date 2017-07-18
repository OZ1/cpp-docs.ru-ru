---
title: "Функции &lt;chrono&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 68c68070265c8cc7ff4d6c5c070b4e7849d50a91
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="ltchronogt-functions"></a>Функции &lt;chrono&gt;
||||  
|-|-|-|  
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|  
  

##  <a name="duration_cast"></a>duration_cast
 Приводит объект `duration` к указанному типу.  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `duration` типа `To`, представляющий интервал времени `Dur`, который усекается, если должен соответствовать целевому типу.  
  
### <a name="remarks"></a>Примечания  
 Если `To` является экземпляром `duration`, эта функция не участвует в разрешении перегрузки.  
  
##  <a name="time_point_cast"></a>time_point_cast
 Приводит объект [time_point](../standard-library/time-point-class.md) к указанному типу.  
  
```  
template <class To, class Clock, class Duration>  
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `time_point`, который имеет длительность типа `To`.  
  
### <a name="remarks"></a>Примечания  
 Если `To` не является экземпляром [duration](../standard-library/duration-class.md), эта функция не участвует в разрешении перегрузки.  
  
## <a name="see-also"></a>См. также  
 [\<chrono>](../standard-library/chrono.md)

