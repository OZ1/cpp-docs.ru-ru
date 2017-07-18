---
title: "Класс normal_distribution | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- normal_distribution
- random/std::normal_distribution
- random/std::normal_distribution::reset
- random/std::normal_distribution::mean
- random/std::normal_distribution::stddev
- random/std::normal_distribution::param
- random/std::normal_distribution::min
- random/std::normal_distribution::max
- random/std::normal_distribution::operator()
- random/std::normal_distribution::param_type
- random/std::normal_distribution::param_type::mean
- random/std::normal_distribution::param_type::stddev
- random/std::normal_distribution::param_type::operator==
- random/std::normal_distribution::param_type::operator!=
- random/std::normal_distribution::param_type
dev_langs:
- C++
helpviewer_keywords:
- normal_distribution class
ms.assetid: bf92cdbd-bc72-4d4a-b588-173d748f0d7d
caps.latest.revision: 19
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 16b8c59395ae727e47be88e32aeb87c32b2e403d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="normaldistribution-class"></a>Класс normal_distribution
Формирует нормальное распределение.  
  
## <a name="syntax"></a>Синтаксис  
```  
template<class RealType = double>
class normal_distribution  
   {  
public:  
   // types  
   typedef RealType result_type;  
   struct param_type;  

   // constructors and reset functions  
   explicit normal_distribution(result_type mean = 0.0, result_type stddev = 1.0);
   explicit normal_distribution(const param_type& parm);
   void reset();

   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions  
   result_type mean() const;
   result_type stddev() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
```  
  
### <a name="parameters"></a>Параметры  
*RealType*  
По умолчанию тип с плавающей запятой имеет тип `double`. Возможные типы см. в разделе [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Примечания  
Класс шаблона описывает распределение, которое формирует значения указанного пользователем целочисленного типа или типа `double` (если тип не указан), распределенные в соответствии с нормальным распределением. В следующей таблице представлены ссылки на статьи об отдельных членах.  
  
||||  
|-|-|-|  
|[normal_distribution](#normal_distribution)|`normal_distribution::mean`|`normal_distribution::param`|  
|`normal_distribution::operator()`|`normal_distribution::stddev`|[param_type](#param_type)|  
  
Функции свойств `mean()` и `stddev()` возвращают значения для хранимых параметров распределения `mean` и `stddev` соответственно.  
  
Член свойства `param()` устанавливает или возвращает хранимый пакет параметров распределения `param_type`.  

Функции-члены `min()` и `max()` возвращают наименьший и наибольший из возможных результатов соответственно.  
  
Функция-член `reset()` удаляет любые кэшированные значения, чтобы результат следующего вызова `operator()` не зависел от любых значений, полученных от механизма перед вызовом.  
  
Функции-члены `operator()` возвращают следующее значение, созданное механизмом РГСЧ, из текущего или указанного пакета параметров.
  
Дополнительные сведения о классах распределения и их членах см. в разделе [\<random>](../standard-library/random.md).  
  
Подробные сведения о нормальном распределении см. статью в Wolfram MathWorld [Нормальное распределение](http://go.microsoft.com/fwlink/LinkId=400924).  
  
## <a name="example"></a>Пример  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
using namespace std;  
  
void test(const double m, const double s, const int samples) {  
  
    // uncomment to use a non-deterministic seed  
    //    random_device gen;  
    //    mt19937 gen(rd());  
    mt19937 gen(1701);  
  
    normal_distribution<> distr(m, s);  
  
    cout << endl;  
    cout << "min() == " << distr.min() << endl;  
    cout << "max() == " << distr.max() << endl;  
    cout << "m() == " << fixed << setw(11) << setprecision(10) << distr.mean() << endl;  
    cout << "s() == " << fixed << setw(11) << setprecision(10) << distr.stddev() << endl;  
  
    // generate the distribution as a histogram  
    map<double, int> histogram;  
    for (int i = 0; i < samples; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    cout << "Distribution for " << samples << " samples:" << endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        cout << fixed << setw(11) << ++counter << ": "  
            << setw(14) << setprecision(10) << elem.first << endl;  
    }  
    cout << endl;  
}  
  
int main()  
{  
    double m_dist = 1;  
    double s_dist = 1;  
    int samples = 10;  
  
    cout << "Use CTRL-Z to bypass data entry and run using default values." << endl;  
    cout << "Enter a floating point value for the 'mean' distribution parameter: ";  
    cin >> m_dist;  
    cout << "Enter a floating point value for the 'stddev' distribution parameter (must be greater than zero): ";  
    cin >> s_dist;  
    cout << "Enter an integer value for the sample count: ";  
    cin >> samples;  
  
    test(m_dist, s_dist, samples);  
}  
  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'mean' distribution parameter: 0  
Enter a floating point value for the 'stddev' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == -1.79769e+308  
max() == 1.79769e+308  
m() == 0.0000000000  
s() == 1.0000000000  
Distribution for 10 samples:  
    1: -0.8845823965  
    2: -0.1995761116  
    3: -0.1162665130  
    4: -0.0685154932  
    5: 0.0403741461  
    6: 0.1591327792  
    7: 1.0414389924  
    8: 1.5876269426  
    9: 1.6362637713  
    10: 2.7821317338  
```  
  
## <a name="requirements"></a>Требования  
**Заголовок:** \<random>  
  
**Пространство имен:** std  
  
##  <a name="normal_distribution"></a>  normal_distribution::normal_distribution  
Формирует распределение.  
  
```  
explicit normal_distribution(result_type mean = 0.0, result_type stddev = 1.0);
explicit normal_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Параметры  
*mean*  
Параметр распределения `mean`.  
  
*stddev*  
Параметр распределения `stddev`.  
  
*parm*  
Структура параметров, используемая для формирования распределения.  
  
### <a name="remarks"></a>Примечания  
**Предварительные условия:** `0.0 ≤ stddev`  
  
Первый конструктор создает объект, чье хранимое значение `mean` равно *mean*, а хранимое значение `stddev` — *stddev*.  
  
Второй конструктор создает объект, хранимые параметры которого инициализируются из *parm*. Вы можете получить и задать текущие параметры существующего распределения, вызвав функцию-член `param()`.  
  
##  <a name="param_type"></a>  normal_distribution::param_type  
Сохраняет параметры распределения.  
  
```cpp  
struct param_type {  
   typedef normal_distribution<result_type> distribution_type;  
   param_type(result_type mean = 0.0, result_type stddev = 1.0);
   result_type mean() const;
   result_type stddev() const;
  
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
### <a name="parameters"></a>Параметры  
*mean*  
Параметр распределения `mean`.  
  
*stddev*  
Параметр распределения `stddev`.  
  
*right*  
Структура `param_type`, используемая для сравнения.  
  
### <a name="remarks"></a>Примечания  
**Предварительные условия:** `0.0 ≤ stddev`  
  
Эту структуру можно передать конструктору класса распределения во время создания экземпляра, функции-члену `param()` для установки хранимых параметров существующего распределения и `operator()` для использования вместо хранимых параметров.  
  
## <a name="see-also"></a>См. также  
 [\<random>](../standard-library/random.md)



