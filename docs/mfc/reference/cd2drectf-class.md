---
title: "Класс CD2DRectF | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: cc43fd636955573f7c163623775053c9c283fada
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="cd2drectf-class"></a>Класс CD2DRectF
Программа-оболочка для `D2D1_RECT_F`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRectF::CD2DRectF](#cd2drectf)|Перегружен. Создает `CD2DRectF` объекта из `D2D1_RECT_F` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRectF::ISNULL](#isnull)|Возвращает `boolean` значение, указывающее, является ли выражение содержит недопустимые данные ( `null`).|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRectF::operator CRect](#operator_crect)|Преобразует `CD2DRectF` для `CRect` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `D2D1_RECT_F`  
  
 `CD2DRectF`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="cd2drectf"></a>CD2DRectF::CD2DRectF  
 Создает объект CD2DRectF из CRect объекта.  
  
```  
CD2DRectF(const CRect& rect);  
CD2DRectF(const D2D1_RECT_F& rect);  
  CD2DRectF(const D2D1_RECT_F* rect);

 
CD2DRectF(
    FLOAT fLeft = 0.,  
    FLOAT fTop = 0.,  
    FLOAT fRight = 0.,  
    FLOAT fBottom = 0.);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 исходного прямоугольника  
  
 `fLeft`  
 Координата левой источника  
  
 `fTop`  
 Координата верхней источника  
  
 `fRight`  
 Источник справа координат  
  
 `fBottom`  
 Нижняя координата источника  
  
##  <a name="isnull"></a>CD2DRectF::ISNULL  
 Возвращает логическое значение, указывающее, является ли выражение содержит недопустимые данные (Null).  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если верхней прямоугольника, левую, нижнюю и правильные значения, все равно 0; в противном случае — значение FALSE.  
  
##  <a name="operator_crect"></a>CD2DRectF::operator CRect  
 Преобразует CD2DRectF CRect.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение прямоугольника D2D.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
