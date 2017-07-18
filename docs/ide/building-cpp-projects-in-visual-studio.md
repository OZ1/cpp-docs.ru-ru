---
title: "Построение проектов C++ в Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "построения [C++], сведения о построении в Visual Studio"
  - "проекты [C++], построение"
  - "проекты Visual C++, построение"
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Построение проектов C++ в Visual Studio
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Интегрированная среда разработки \(IDE\) Visual Studio предлагает несколько способов сборки всего решения или отдельных проектов в его составе.  Чтобы повысить эффективность процесса разработки, можно также изменить параметры сборки и настроить пользовательские шаги сборки.  
  
 Чтобы выполнить сборку решения, открытого в [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] и выбранного в **Обозревателе решений**, можно выполнить указанные ниже действия.  
  
-   В строке меню последовательно выберите **Сборка** и **Собрать решение**.  
  
-   Либо в области **Обозреватель решений** откройте контекстное меню для решения и выберите пункт **Собрать решение**.  
  
-   Либо нажмите клавишу F7.  \(Это клавиша по умолчанию для открытия параметров разработки C\/C\+\+.\)  
  
-   Либо в области [Командное окно](../Topic/Command%20Window.md) \(в меню **Вид** последовательно выберите пункты **Другие окна** и **Командное окно**\) введите `Build.BuildSolution`.  
  
-   Либо в поле [Быстрый запуск](../Topic/Quick%20Launch,%20Environment,%20Options%20Dialog%20Box.md) введите `сборка решения`.  
  
 Чтобы выполнить сборку проекта, выбранного в **Обозревателе решений**, можно выполнить указанные ниже действия.  
  
-   В меню **Сборка** выберите пункт **Собрать \<имя проекта\>**.  
  
-   Либо в области **Обозреватель решений** откройте контекстное меню для проекта и выберите пункт **Собрать**.  
  
-   Либо в области "Командное окно" \(в меню **Вид** последовательно выберите пункты **Другие окна** и **Командное окно**\) введите `Build.BuildOnlyProject`.  
  
-   Либо в поле "Быстрый запуск" введите `собрать только проект <имя проекта>`.  
  
 При сборке приложения Visual C\+\+ в Visual Studio можно изменить многие из параметров сборки, приведенных в диалоговом окне "Страницы свойств" проекта.  Сведения о настройке свойств проекта см. в статье [Работа со свойствами проектов](../ide/working-with-project-properties.md).  
  
 Пример использования среды IDE для создания, сборки и отладки проекта C\+\+ см. в статье [Пошаговое руководство по использованию C\+\+ в среде IDE Visual Studio](../Topic/Getting%20Started%20with%20C++%20in%20Visual%20Studio.md).  Пример использования среды IDE для сборки проекта C\+\+\/CLR см. в статье [Пошаговое руководство. Компиляция программы на языке C\+\+, предназначенной для среды CLR, в Visual Studio](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md).  Пример использования среды IDE для создания приложения среды выполнения Windows см. в статье [Создание первого приложения среды выполнения Windows на C\+\+](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx).  
  
 Узнать больше о выполнении сборки, изменении параметров сборки и настройке пользовательских шагов сборки можно в приведенных ниже статьях.  
  
## В этом подразделе  
 [Сведения об этапах настраиваемого построения и событиях построения.](../ide/understanding-custom-build-steps-and-build-events.md)  
 Описывается настройка процесса сборки в интегрированной среде разработки.  
  
 [Макросы для команд и свойств построения](../ide/common-macros-for-build-commands-and-properties.md)  
 Список макросов, которые можно использовать в тех случаях, когда допустимы строки.  
  
 [Построение внешних проектов](../ide/building-external-projects.md)  
 Рассматривается сборка проектов, в которых используются средства, не входящие в интегрированную среду разработки.  
  
 [Файлы проекта](../ide/project-files.md)  
 Описывается XML\-структура файла VCXPROJ.  
  
## Связанные подразделы  
 [VC\+\+ Directories, Projects, Options Dialog Box](http://msdn.microsoft.com/ru-ru/e027448b-c811-4c3d-8531-4325ad3f6e02)  
 Описывается процедура изменения пути поиска для исполняемых файлов, включаемых файлов, файлов библиотек и файлов исходного кода во время сборки.  
  
 [Построение приложений в Visual Studio](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)  
 Содержит информацию о сборке в Visual Studio.  
  
 [Сборка программ C\/C\+\+](../build/building-c-cpp-programs.md)  
 Содержит ссылки на статьи, в которых описывается процесс сборки программы из командной строки или из интегрированной среды разработки Visual Studio.  
  
 [Образец построения C\/C\+\+](../Topic/C-C++%20Building%20Reference.md)  
 Содержит ссылки на статьи, содержащие общие сведения о сборке программ на C\+\+, о параметрах компилятора и компоновщика и о дополнительных средствах построения.  
  
 [Обновление проектов, созданных в предыдущих версиях Visual C\+\+](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 Содержит ссылки на статьи, в которых описываются проблемы обновления проектов Visual С\+\+ 6.0 и более поздних версий до Visual C\+\+ .NET.  
  
 [Porting and Upgrading Programs](http://msdn.microsoft.com/ru-ru/c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)  
 Содержит подробные сведения о переносе приложений и о файлах makefile.  
  
## См. также  
 [Roadmap for Windows Store apps using C\+\+](http://msdn.microsoft.com/ru-ru/0b71e4a4-5d8a-4a20-b2ec-e40062675ec1)