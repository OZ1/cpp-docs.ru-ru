---
title: "ICommandPropertiesImpl::SetProperties | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
- SetProperties
dev_langs:
- C++
helpviewer_keywords:
- SetProperties method
ms.assetid: c42132bb-16a9-4e00-aba6-dee785a98488
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 03f8c15b9319b4ef64dfd9d45e589b7e8c1fd1d9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="icommandpropertiesimplsetproperties"></a>ICommandPropertiesImpl::SetProperties
Задает свойства для объекта команды.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ICommandProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms711497.aspx) в *справочника программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)   
 [ICommandPropertiesImpl::GetProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)