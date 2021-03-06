---
title: "Пошаговое руководство: Добавление объекта D2D в проект MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98c14611bbca828f6264c3fcfa66462c02320432
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>Пошаговое руководство. Добавление объекта D2D в проект MFC
Этом пошаговом руководстве рассматриваются способы добавления основные Direct2D (D2D) объекта в Visual C++ проект библиотеки классов Microsoft Foundation (MFC) и затем постройте проект в приложение, которое выводит «Hello, world» на градиента фона.  
  
 Пошаговом руководстве показано, как выполнять следующие задачи:  
  
-   Создайте приложение MFC.  
  
-   Создайте кисть сплошного цвета и кисти линейного градиента.  
  
-   Измените градиентной кисти, чтобы она изменялась в соответствии с изменением размера окна.  
  
-   Реализация обработчика рисования D2D.  
  
-   Проверка результатов.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства, необходимо иметь Visual Studio.  
  
### <a name="to-create-an-mfc-application"></a>Создание приложения MFC  
  
1.  В меню **Файл** выберите пункт **Создать** , а затем команду **Проект**.  
  
2.  В **новый проект** в левой области в разделе диалогового **установленные шаблоны**, разверните **Visual C++** , а затем выберите **MFC**. В средней области выберите **приложение MFC**. В поле **Имя** введите `MFCD2DWalkthrough`. Нажмите кнопку **ОК**.  
  
3.  В **мастер приложений MFC**, нажмите кнопку **Готово** без изменения любых параметров.  
  
### <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>Создание кисти сплошного цвета и кисти линейного градиента  
  
1.  В **обозревателе решений**в **MFCD2DWalkthrough** проекта **файлы заголовков** папку, откройте MFCD2DWalkthroughView.h. Добавьте следующий код в `CMFCD2DWalkthroughView` класса, чтобы создать три переменных с данными.  
  
 ```  
    CD2DTextFormat* m_pTextFormat;  
    CD2DSolidColorBrush* m_pBlackBrush;  
    CD2DLinearGradientBrush* m_pLinearGradientBrush;  
 ```  
  
     Сохраните файл и закройте его.  
  
2.  В **исходные файлы** папку, откройте MFCD2DWalkthroughView.cpp. В конструкторе для `CMFCD2DWalkthroughView` класса, добавьте следующий код.  
  
 "" * / / Включить поддержку D2D для этого окна:  
    EnableD2DSupport();

 * /, Инициализация ресурсы D2D:  
    m_pBlackBrush = новый CD2DSolidColorBrush(GetRenderTarget(), D2D1::ColorF(D2D1::ColorF::Black));

 
    m_pTextFormat = новый CD2DTextFormat(GetRenderTarget(), _T("Verdana"), 50);

    m_pTextFormat -> Get() -> SetTextAlignment(DWRITE_TEXT_ALIGNMENT_CENTER);

 m_pTextFormat -> Get() -> SetParagraphAlignment(DWRITE_PARAGRAPH_ALIGNMENT_CENTER);

 
    D2D1_GRADIENT_STOP gradientStops [2].  
 
    .color gradientStops [0] = D2D1::ColorF(D2D1::ColorF::White);

    .position gradientStops [0] = 0.f;  
    .color gradientStops [1] = D2D1::ColorF(D2D1::ColorF::Indigo);

    .position gradientStops [1] = 1.f;  
 
    m_pLinearGradientBrush = новый CD2DLinearGradientBrush(GetRenderTarget()   
    gradientStops ARRAYSIZE(gradientStops),  
    D2D1::LinearGradientBrushProperties (D2D1::Point2F (0, 0), D2D1::Point2F (0, 0)));

 ```  
  
     Save the file and close it.  
  
### To modify the gradient brush so that it will change appropriately when the window is resized  
  
1.  On the **Project** menu, click **Class Wizard**.  
  
2.  In the **MFC Class Wizard**, under **Class name**, select `CMFCD2DWalkthroughView`.  
  
3.  On the **Messages** tab, in the **Messages** box, select `WM_SIZE` and then click **Add Handler**. This action adds the `OnSize` message handler to the `CMFCD2DWalkthroughView` class.  
  
4.  In the **Existing handlers** box, select `OnSize`. Click **Edit Code** to display the `CMFCD2DWalkthroughView::OnSize` method. At the end of the method, add the following code.  
  
 ```  
    m_pLinearGradientBrush -> SetEndPoint (CPoint (cx, cy));

 ```  
  
     Save the file and close it.  
  
### To implement a D2D drawing handler  
  
1.  On the **Project** menu, click **Class Wizard**.  
  
2.  In the **MFC Class Wizard**, under **Class name**, select `CMFCD2DWalkthroughView`.  
  
3.  On the **Messages** tab, click **Add Custom Message**.  
  
4.  In the **Add Custom Message** dialog box, in the **Custom Windows Message** box, type `AFX_WM_DRAW2D`. In the **Message handler name** box, type `OnDraw2D`. Select the **Registered Message** option and then click **OK**. This action adds a message handler for the `AFX_WM_DRAW2D` message to the `CMFCD2DWalkthroughView` class.  
  
5.  In the **Existing handlers** box, select `OnDraw2D`. Click **Edit Code** to display the `CMFCD2DWalkthroughView::OnDraw2D` method. Use the following code for the `CMFCD2DWalkthroughView::OnDrawD2D` method.  
  
 ```  
    LRESULT CMFCD2DWalkthroughView::OnDraw2D(WPARAM wParam, LPARAM lParam) afx_msg  
    {  
 PRenderTarget CHwndRenderTarget * = (CHwndRenderTarget *) lParam;  
    ASSERT_VALID(pRenderTarget);

 
    CRect rect;  
    GetClientRect(rect);

 
    pRenderTarget -> FillRectangle (rect, m_pLinearGradientBrush);

    pRenderTarget -> DrawText (_T ("Hello, World!"), rect, m_pBlackBrush, m_pTextFormat);

 
    Возвращает значение TRUE;  
 }  
 ```  
  
     Save the file and close it.  
  
### To verify the results  
  
1.  Build and run the application. It should have a gradient rectangle that changes when you resize the window. “Hello World!” should be displayed in the center of the rectangle.  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)

