---
title: "Операторы &lt;tuple&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- tuple/std::operator!=
- tuple/std::operator>
- tuple/std::operator>=
- tuple/std::operator<
- tuple/std::operator<=
- tuple/std::operator==
dev_langs:
- C++
ms.assetid: f25752dc-d3e2-4e12-b5ac-9a8682ca60ed
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: b397aa72bff4c2f1f46b7faf32030c21683f1e51
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="lttuplegt-operators"></a>Операторы &lt;tuple&gt;
||||  
|-|-|-|  
|[оператор!=](#op_neq)|[оператор&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|  
|[оператор&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[оператор==](#op_eq_eq)|  
  
##  <a name="op_neq"></a> operator!=  
 Сравнивает объекты `tuple` на неравенство.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator!=(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Параметры  
 `TN`  
 Тип N-го элемента кортежа.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает значение false, если `N` равно 0; в противном случае — значение `get<0>(tpl1) != get<0>(tpl2) || get<1>(tpl1) != get<1>(tpl2) || ... || get<N - 1>(tpl1) == get<N - 1>(tpl2)`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__tuple__operator_ne.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 != c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 != c1);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
false  
true  
```  
  
##  <a name="op_lt"></a> operator&lt;  
 Сравнение объектов `tuple` на предмет меньшинства.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator<(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Параметры  
 `TN`  
 Тип N-го элемента кортежа.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает значение true, если `N` больше 0, а первое отличающееся значение в `tpl1` при сравнении оказывается меньше, чем соответствующее значение `tpl2`; в противном случае возвращается значение false.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__tuple__operator_lt.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 < c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 < c1);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
false  
true  
```  
  
##  <a name="op_lt_eq"></a> operator&lt;=  
 Сравнение объектов `tuple` на предмет отношения меньше или равно.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator<=(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Параметры  
 `TN`  
 Тип N-го элемента кортежа.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает `!(tpl2 < tpl1)`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__tuple__operator_le.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 <= c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c1 <= c0);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
true  
false  
```  
  
##  <a name="op_eq_eq"></a> operator==  
 Сравнение объектов `tuple` на равенство.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator==(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Параметры  
 `TN`  
 Тип N-го элемента кортежа.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает значение true, если `N` равно 0; в противном случае — значение `get<0>(tpl1) == get<0>(tpl2) && get<1>(tpl1) == get<1>(tpl2) && ... && get<N - 1>(tpl1) == get<N - 1>(tpl2)`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__tuple__operator_eq.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 == c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 == c1);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
true  
false  
```  
  
##  <a name="op_gt"></a> operator&gt;  
 Сравнение объектов `tuple` на предмет большинства.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator>(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Параметры  
 `TN`  
 Тип N-го элемента кортежа.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает `tpl2 < tpl1`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__tuple__operator_gt.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 > c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c1 > c0);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
false  
true  
```  
  
##  <a name="op_gt_eq"></a> operator&gt;=  
 Сравнение объектов `tuple` на предмет большинства или равенства.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator>=(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Параметры  
 `TN`  
 Тип N-го элемента кортежа.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает `!(tpl1 < tpl2)`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__tuple__operator_ge.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 >= c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 >= c1);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
true  
false  
```  
  
## <a name="see-also"></a>См. также  
 [\<tuple>](../standard-library/tuple.md)

