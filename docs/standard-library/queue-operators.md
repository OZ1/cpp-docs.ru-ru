---
title: "Операторы &lt;queue&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 7c435b48-175c-45b0-88eb-24561044019c
caps.latest.revision: 13
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 7702c8ba7e5d0f9dfa5df184451d9addb19adbbd
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ltqueuegt-operators"></a>Операторы &lt;queue&gt;
||||  
|-|-|-|  
|[оператор!=](#op_neq)|[оператор&gt;](#op_gt)|[оператор&gt;=](#op_gt_eq)|  
|[оператор&lt;](#op_lt)|[оператор&lt;=](#op_lt_eq)|[оператор==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  оператор!=  
 Проверяет неравенство объекта queue слева от оператора объекту queue справа от оператора.  
  
```  
bool operator!=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **queue**.  
  
 `right`  
 Объект типа **queue**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если очереди не равны; **false**, если очереди равны.  
  
### <a name="remarks"></a>Примечания  
 Сравнение объектов-очередей основывается на попарном сравнении их элементов. Две очереди равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// queue_op_ne.cpp  
// compile with: /EHsc  
#include <queue>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queues with list base containers  
   queue <int, list<int> > q1, q2, q3;  
  
   // The following line would have caused an error because vector   
   // does not support pop_front( ) and so cannot be adapted  
   // by queue as a base container  
   // queue <int, vector<int> > q1, q2, q3;  
  
   q1.push( 1 );  
   q2.push( 1 );  
   q2.push( 2 );  
   q3.push( 1 );  
  
   if ( q1 != q2 )  
      cout << "The queues q1 and q2 are not equal." << endl;  
   else  
      cout << "The queues q1 and q2 are equal." << endl;  
  
   if ( q1 != q3 )  
      cout << "The queues q1 and q3 are not equal." << endl;  
   else  
      cout << "The queues q1 and q3 are equal." << endl;  
}  
```  
  
```Output  
The queues q1 and q2 are not equal.  
The queues q1 and q3 are equal.  
```  
  
##  <a name="op_lt"></a>  оператор&lt;  
 Проверяет, меньше ли объект queue слева от оператора, чем объект queue справа от оператора.  
  
```  
bool operator<(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **queue**.  
  
 `right`  
 Объект типа **queue**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если очередь слева от оператора меньше очереди справа от оператора (и не равна ему); в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение объектов-очередей основывается на попарном сравнении их элементов. Отношение "меньше" между двумя объектами-очередями основывается на сравнении первой пары неравных элементов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// queue_op_lt.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queues with default deque base container  
   queue <int> q1, q2, q3;  
  
   q1.push( 1 );  
   q1.push( 2 );  
   q2.push( 5 );  
   q2.push( 10 );  
   q3.push( 1 );  
   q3.push( 2 );  
  
   if ( q1 < q2 )  
      cout << "The queue q1 is less than the queue q2." << endl;  
   else  
      cout << "The queue q1 is not less than the queue q2." << endl;  
  
   if ( q1 < q3 )  
      cout << "The queue q1 is less than the queue q3." << endl;  
   else  
      cout << "The queue q1 is not less than the queue q3." << endl;  
}  
```  
  
```Output  
The queue q1 is less than the queue q2.  
The queue q1 is not less than the queue q3.  
```  
  
##  <a name="op_lt_eq"></a>  оператор&lt;=  
 Проверяет, меньше ли объект queue слева от оператора, чем объект queue справа от оператора, или равен ему.  
  
```  
bool operator<=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **queue**.  
  
 `right`  
 Объект типа **queue**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если очередь слева от оператора строго меньше очереди справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение объектов-очередей основывается на попарном сравнении их элементов. Отношение "меньше или равно" между двумя объектами-очередями основывается на сравнении первой пары неравных элементов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// queue_op_le.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2, q3;  
  
   q1.push( 5 );  
   q1.push( 10 );  
   q2.push( 1 );  
   q2.push( 2 );  
   q3.push( 5 );  
   q3.push( 10 );  
  
   if ( q1 <= q2 )  
      cout << "The queue q1 is less than or equal to "  
           << "the queue q2." << endl;  
   else  
      cout << "The queue q1 is greater than "  
           << "the queue q2." << endl;  
  
   if ( q1 <= q3 )  
      cout << "The queue q1 is less than or equal to "  
           << "the queue q3." << endl;  
   else  
      cout << "The queue q1 is greater than "  
           << "the queue q3." << endl;  
}  
```  
  
```Output  
The queue q1 is greater than the queue q2.  
The queue q1 is less than or equal to the queue q3.  
```  
  
##  <a name="op_eq_eq"></a>  оператор==  
 Проверяет равенство объекта-очереди слева от оператора объекту-очереди справа от оператора.  
  
```  
bool operator==(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **queue**.  
  
 `right`  
 Объект типа **queue**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если очереди не равны; **false**, если очереди равны.  
  
### <a name="remarks"></a>Примечания  
 Сравнение объектов-очередей основывается на попарном сравнении их элементов. Две очереди равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// queue_op_eq.cpp  
// compile with: /EHsc  
#include <queue>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queues with list base containers  
   queue <int, list<int> > q1, q2, q3;  
  
   // The following line would have caused an error because vector   
   // does not support pop_front( ) and so cannot be adapted  
   // by queue as a base container  
   // queue <int, vector<int> > q1, q2, q3;  
  
   q1.push( 1 );  
   q2.push( 2 );  
   q3.push( 1 );  
  
   if ( q1 != q2 )  
      cout << "The queues q1 and q2 are not equal." << endl;  
   else  
      cout << "The queues q1 and q2 are equal." << endl;  
  
   if ( q1 != q3 )  
      cout << "The queues q1 and q3 are not equal." << endl;  
   else  
      cout << "The queues q1 and q3 are equal." << endl;  
}  
```  
  
```Output  
The queues q1 and q2 are not equal.  
The queues q1 and q3 are equal.  
```  
  
##  <a name="op_gt"></a>  оператор&gt;  
 Проверяет, больше ли объект queue слева от оператора, чем объект queue справа от оператора.  
  
```  
bool operator>(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **queue**.  
  
 `right`  
 Объект типа **queue**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если очередь слева от оператора строго меньше очереди справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение объектов-очередей основывается на попарном сравнении их элементов. Отношение "больше" между двумя объектам-очередями основывается на сравнении первой пары неравных элементов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// queue_op_gt.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2, q3;  
  
   q1.push( 1 );  
   q1.push( 2 );  
   q1.push( 3 );  
   q2.push( 5 );  
   q2.push( 10 );  
   q3.push( 1 );  
   q3.push( 2 );  
  
   if ( q1 > q2 )  
      cout << "The queue q1 is greater than "  
           << "the queue q2." << endl;  
   else  
      cout << "The queue q1 is not greater than "  
           << "the queue q2." << endl;  
  
   if ( q1> q3 )  
      cout << "The queue q1 is greater than "  
           << "the queue q3." << endl;  
   else  
      cout << "The queue q1 is not greater than "  
           << "the queue q3." << endl;  
}  
```  
  
```Output  
The queue q1 is not greater than the queue q2.  
The queue q1 is greater than the queue q3.  
```  
  
##  <a name="op_gt_eq"></a>  оператор&gt;=  
 Проверяет, больше ли объект queue слева от оператора, чем объект queue справа от оператора, или равен ему.  
  
```  
bool operator>=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **queue**.  
  
 `right`  
 Объект типа **queue**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если очередь слева от оператора строго меньше очереди справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение объектов-очередей основывается на попарном сравнении их элементов. Две очереди равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// queue_op_ge.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2, q3;  
  
   q1.push( 1 );  
   q1.push( 2 );  
   q2.push( 5 );  
   q2.push( 10 );  
   q3.push( 1 );  
   q3.push( 2 );  
  
   if ( q1 >= q2 )  
      cout << "The queue q1 is greater than or equal to "  
           << "the queue q2." << endl;  
   else  
      cout << "The queue q1 is less than "  
           << "the queue q2." << endl;  
  
   if ( q1>= q3 )  
      cout << "The queue q1 is greater than or equal to "  
           << "the queue q3." << endl;  
   else  
      cout << "The queue q1 is less than "  
           << "the queue q3." << endl;  
}  
```  
  
```Output  
The queue q1 is less than the queue q2.  
The queue q1 is greater than or equal to the queue q3.  
```  
  
## <a name="see-also"></a>См. также  
 [\<queue>](../standard-library/queue.md)

