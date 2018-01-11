---
title: "Стандарт C++ атрибуты | Документы Microsoft"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: d2dcce6b0e289588c426792a334ee4ec38d1ab5f
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="attributes-in-c"></a>Атрибуты в C++

Стандарт C++ определяет набор атрибутов, а также позволяет поставщикам компилятора определить свои собственные атрибуты (в пространстве имен поставщика), но компиляторы должны распознает только те атрибуты, которые определены в стандарте.

В некоторых случаях стандартные атрибуты перекрываться с параметрами declspec специфичные для компилятора. В Visual C++ можно использовать `[[deprecated]]` атрибута вместо `declspec(deprecated)` и атрибут распознается любой компилятор соответствует стандартам. Для всех остальных параметров declspec как dllimport и dllexport не имеет еще атрибут эквивалента, поэтому необходимо продолжать использовать синтаксис declspec. Атрибуты, не влияют на системе типов, и они не изменить смысл программы. Компиляторы игнорировать значения атрибутов, которые не удается распознать.

**Visual Studio 2017 г 15,3 и более поздних версий** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): В области списка атрибутов, можно указать пространство имен для всех имен с одним `using` introducer:

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>Стандартные атрибуты

В C ++ 11 атрибуты предоставляют стандартный способ добавить заметку конструкций C++ (включая, но не ограничиваясь классов, функции, переменные и блоки) с дополнительными сведениями, которые могут поддерживаться или не может быть поставщика. Компилятор может использовать эти сведения для создания информационных сообщений или для применения специальной логики, при компиляции кода с атрибутами. Компилятор игнорирует все атрибуты, которые не распознает, что означает, что невозможно определить собственные настраиваемые атрибуты, используя следующий синтаксис. Атрибуты заключены в двойные квадратные скобки:

```cpp
[[deprecated]]
void Foo(int);
```

Атрибуты представляют стандартизированные альтернативу расширения поставщика, например директивы #pragma, __declspec() (Visual C++), или &#95; &#95; атрибут &#95; &#95; (GNU). Однако по-прежнему нужно использовать конструкции поставщика для большинства целей. В настоящее время стандартной задает следующие атрибуты, которые следует распознавать соответствующим компилятором:

- `[[noreturn]]`Указывает, что функция никогда не возвращается; Другими словами он всегда создает исключение. Компилятор, можно настроить ее компиляции правила для `[[noreturn]]` сущностей.

- `[[carries_dependency]]`Указывает, что функция распространяет данные зависимостей упорядочение по отношению к синхронизации потоков. Атрибут может применяться для одного или нескольких параметров, чтобы указать, что переданный аргумент имеет зависимостей в теле функции. Атрибут может применяться в саму функцию, чтобы указать, что возвращаемое значение имеет зависимость выходит из функции. Компилятор может использовать эти сведения для создания более эффективный код.

- `[[deprecated]]`**Visual Studio 2015 и более поздних версий:** указывает, что функция не предназначена для использования и может отсутствовать в будущих версиях интерфейс библиотеки. Компилятор может использовать это для создания информационное сообщение, если код клиента пытается вызвать функцию. Могут применяться к объявлению класса, имя typedef, переменной, нестатические данные-член, функции, пространство имен, перечисления, перечислитель или специализации шаблона.  

- `[[fallthrough]]`**2017 и более поздней версии visual Studio:** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) `[[fallthrough]]` атрибут может использоваться в контексте [переключения](switch-statement-cpp.md) инструкции как подсказку для компилятор (или любой пользователь в коде), поведение передачи управления предназначено. Компилятор Visual C++ в настоящее время не предупреждать о fallthrough поведение, поэтому этот атрибут имеет поведение компилятора не влияет.

- `[[nodiscard]]`**15,3 и более поздних версий 2017 г. visual Studio:** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) указывает возвращаемое значение функции не является будут отменены. Вызывает предупреждение C4834, как показано в следующем примере:

   ```cpp
   [[nodiscard]]
   int foo(int i) { return i * i; }

   int main()
   {
       foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
       return 0;
   }
   ```

- `[[maybe_unused]]`**15,3 и более поздних версий 2017 г. visual Studio:** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) указывает, что переменной, функции, класса, typedef, специализации шаблона члена, enum или нестатических данных может намеренно не следует использовать. Компилятор не предупреждать, когда сущность помечена как `[[maybe_unused]]` не используется. Повторное объявление сущности, которая объявлена без атрибута можно позже с атрибутом и наоборот. Сущность считается помеченные после анализа его первым объявлением, помеченного и в оставшейся части перевод текущей записи преобразования.

## <a name="microsoft-specific-attributes"></a>Атрибуты, зависящие от корпорации Майкрософт

- `[[gsl::suppress(rules)]]`Этот атрибут характерные для Майкрософт используется для подавления предупреждений в данный момент применения [библиотеки поддержки рекомендации (GSL)](https://github.com/Microsoft/GSL) правила в коде. Например рассмотрим следующий фрагмент кода:

    ```cpp
    void main()
    {
        int arr[10]; // GSL warning 26494 will be fired
        int* p = arr; // GSL warning 26485 will be fired
        [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
        {
            int* q = p + 1; // GSL warning 26481 suppressed
            p = q--; // GSL warning 26481 suppressed
        }
    }
    ```

   Пример вызывает следующие предупреждения:

   - 26494 (тип правила 5: всегда инициализировать объект.)

   - 26485 (границы правила 3: нет массива критичной указателя.)

   - 26481 (границы правила 1: не используйте арифметических операций над указателями. Использовать диапазон.)

   Первые два предупреждения срабатывать при компиляции кода с помощью средства анализа кода CppCoreCheck установлен и активирован. Но не запускает третье предупреждение из-за атрибута. Можно подавить весь профиль границы, написав [[gsl::suppress(bounds)]], не включая номер конкретного правила. Основные правила C++ предназначены для упрощения написания кода, повышения и безопаснее. Отключение атрибут позволяет легко отключить предупреждения, когда они не нужны.