---
title: "Метод Module::Terminate | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Terminate
dev_langs:
- C++
helpviewer_keywords:
- Terminate method
ms.assetid: cf358117-45dc-43c7-ac1e-1e1eedc59e41
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2ced22c1cc464df6e7d0c9f205fabc1de56bfe35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="moduleterminate-method"></a>Метод Module::Terminate
Приводит к завершению работы всех экземпляров фабрик, созданных модулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void Terminate();  
```  
  
## <a name="remarks"></a>Примечания  
 Освобождает фабрики в кэше.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс Module](../windows/module-class.md)