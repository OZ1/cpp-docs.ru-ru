# [Среда выполнения с параллелизмом](concurrency-runtime.md)
# [Общие сведения о среде выполнения с параллелизмом](overview-of-the-concurrency-runtime.md)
# [Обработка исключений в среде выполнения с параллелизмом](exception-handling-in-the-concurrency-runtime.md)
# [Средства диагностики параллельного выполнения (среда выполнения с параллелизмом)](parallel-diagnostic-tools-concurrency-runtime.md)
# [Создание асинхронных операций в C++ для приложений для Магазина Windows](creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)
# [Сравнение среды выполнения с параллелизмом с другими моделями параллелизма](comparing-the-concurrency-runtime-to-other-concurrency-models.md)
## [Переход от OpenMP к среде выполнения с параллелизмом](migrating-from-openmp-to-the-concurrency-runtime.md)
### [Практическое руководство. Преобразование параллельного цикла for OpenMP для использования среды выполнения с параллелизмом](how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)
### [Практическое руководство. Преобразование цикла OpenMP, использующего отмену для использования среды выполнения с параллелизмом](convert-an-openmp-loop-that-uses-cancellation.md)
### [Практическое руководство. Преобразование цикла OpenMP, использующего обработку исключений для использования среды выполнения с параллелизмом](convert-an-openmp-loop-that uses-exception-handling.md)
### [Практическое руководство. Преобразование цикла OpenMP, использующего переменную сокращения для использования среды выполнения с параллелизмом](convert-an-openmp-loop-that-uses-a-reduction-variable.md)
# [Библиотека параллельных шаблонов (PPL)](parallel-patterns-library-ppl.md)
## [Параллелизм задач (среда выполнения с параллелизмом)](task-parallelism-concurrency-runtime.md)
### [Практическое руководство. Использование функции parallel_invoke для написания программы параллельной сортировки](how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)
### [Практическое руководство. Использование функции parallel_invoke для выполнения параллельных операций](how-to-use-parallel-invoke-to-execute-parallel-operations.md)
### [Практическое руководство. Создание задачи, выполняемой после задержки](how-to-create-a-task-that-completes-after-a-delay.md)
## [Параллельные алгоритмы](parallel-algorithms.md)
### [Практическое руководство. Написание цикла parallel_for](how-to-write-a-parallel-for-loop.md)
### [Практическое руководство. Написание цикла parallel_for_each](how-to-write-a-parallel-for-each-loop.md)
### [Практическое руководство. Параллельное выполнение операций сопоставления и сокращения числа элементов](how-to-perform-map-and-reduce-operations-in-parallel.md)
## [Параллельные контейнеры и объекты](parallel-containers-and-objects.md)
### [Практическое руководство. Использование параллельных контейнеров для повышения эффективности](how-to-use-parallel-containers-to-increase-efficiency.md)
### [Практическое руководство. Использование класса combinable для повышения производительности](how-to-use-combinable-to-improve-performance.md)
### [Практическое руководство. Использование класса combinable для комбинирования наборов](how-to-use-combinable-to-combine-sets.md)
## [Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)
### [Практическое руководство. Использование отмены для выхода из параллельного цикла](how-to-use-cancellation-to-break-from-a-parallel-loop.md)
### [Практическое руководство. Использование обработки исключений для выхода из параллельного цикла](how-to-use-exception-handling-to-break-from-a-parallel-loop.md)
# [Библиотека асинхронных агентов](asynchronous-agents-library.md)
## [Асинхронные агенты](asynchronous-agents.md)
## [Асинхронные блоки сообщений](asynchronous-message-blocks.md)
## [Функции передачи сообщений](message-passing-functions.md)
## [Практическое руководство. Реализация различных шаблонов "источник-приемник"](how-to-implement-various-producer-consumer-patterns.md)
## [Практическое руководство. Предоставление рабочих функций классам call и transformer](how-to-provide-work-functions-to-the-call-and-transformer-classes.md)
## [Практическое руководство. Использование преобразователя в конвейере данных](how-to-use-transformer-in-a-data-pipeline.md)
## [Практическое руководство. Выбор среди завершенных задач](how-to-select-among-completed-tasks.md)
## [Практическое руководство. Отправка сообщений через определенные интервалы](how-to-send-a-message-at-a-regular-interval.md)
## [Практическое руководство. Использование фильтра блоков сообщений](how-to-use-a-message-block-filter.md)
# [Структуры данных синхронизации](synchronization-data-structures.md)
## [Сравнение структур данных синхронизации с интерфейсом Windows API](comparing-synchronization-data-structures-to-the-windows-api.md)
# [Планировщик задач (среда выполнения с параллелизмом)](task-scheduler-concurrency-runtime.md)
## [Экземпляры планировщика](scheduler-instances.md)
### [Практическое руководство. Управление экземпляром планировщика](how-to-manage-a-scheduler-instance.md)
## [Политики планировщика](scheduler-policies.md)
### [Практическое руководство. Задание определенных политик планировщика](how-to-specify-specific-scheduler-policies.md)
### [Практическое руководство. Создание агентов, использующих определенные политики планировщика](how-to-create-agents-that-use-specific-scheduler-policies.md)
## [Группы планирования](schedule-groups.md)
### [Практическое руководство. Использование групп планирования для определения порядка выполнения](how-to-use-schedule-groups-to-influence-order-of-execution.md)
## [Упрощенные задачи](lightweight-tasks.md)
## [Контексты](contexts.md)
### [Практическое руководство. Использование класса Context для реализации семафора, поддерживающего параллельный доступ](how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)
### [Практическое руководство. Использование лимита подписки для устранения задержек](how-to-use-oversubscription-to-offset-latency.md)
## [Функции управления памятью](memory-management-functions.md)
### [Практическое руководство. Использование функций Alloc и Free для повышения производительности операций с памятью](how-to-use-alloc-and-free-to-improve-memory-performance.md)
# [Пошаговые руководства по среде выполнения с параллелизмом](concurrency-runtime-walkthroughs.md)
## [Пошаговое руководство. Подключение с использованием задач и HTTP-запросов XML](walkthrough-connecting-using-tasks-and-xml-http-requests.md)
## [Пошаговое руководство. Создание приложения на основе агента](walkthrough-creating-an-agent-based-application.md)
## [Пошаговое руководство. Создание агента потоков данных](walkthrough-creating-a-dataflow-agent.md)
## [Пошаговое руководство. Создание сети обработки изображений](walkthrough-creating-an-image-processing-network.md)
## [Пошаговое руководство. Реализация фьючерсов](walkthrough-implementing-futures.md)
## [Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки](walkthrough-using-join-to-prevent-deadlock.md)
## [Пошаговое руководство. Удаление задач из потока пользовательского интерфейса](walkthrough-removing-work-from-a-user-interface-thread.md)
## [Пошаговое руководство. Использование среды выполнения с параллелизмом в приложениях с поддержкой модели COM](walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application.md)
## [Пошаговое руководство. Адаптация существующего кода для использования упрощенных задач](walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)
## [Пошаговое руководство. Создание пользовательского блока сообщений](walkthrough-creating-a-custom-message-block.md)
# [Рекомендации по работе со средой выполнения с параллелизмом](concurrency-runtime-best-practices.md)
## [Рекомендации по работе с библиотекой параллельных шаблонов](best-practices-in-the-parallel-patterns-library.md)
## [Рекомендации по работе с библиотекой асинхронных агентов](best-practices-in-the-asynchronous-agents-library.md)
## [Общие рекомендации в среде выполнения с параллелизмом](general-best-practices-in-the-concurrency-runtime.md)
# [Ссылки](reference/toc.md)