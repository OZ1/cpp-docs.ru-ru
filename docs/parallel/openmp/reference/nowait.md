---
title: "nowait | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- nowait
dev_langs:
- C++
helpviewer_keywords:
- nowait OpenMP clause
ms.assetid: 8a74265d-879c-46cf-8071-a1084f24f16e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 968045d24fb4add0af95f0136160092a7d68fe54
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="nowait"></a>nowait
Переопределяет неявно в директиве барьера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
nowait  
```  
  
## <a name="remarks"></a>Примечания  
 `nowait` применяется к следующие директивы:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 Дополнительные сведения см. в разделе [2.4.1 конструкция for](../../../parallel/openmp/2-4-1-for-construct.md), [2.4.2 конструкция sections](../../../parallel/openmp/2-4-2-sections-construct.md), и [создания единого 2.4.3](../../../parallel/openmp/2-4-3-single-construct.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_nowait.cpp  
// compile with: /openmp /c  
#include <stdio.h>  
  
#define SIZE 5  
  
void test(int *a, int *b, int *c, int size)   
{  
    int i;  
    #pragma omp parallel  
    {  
        #pragma omp for nowait  
        for (i = 0; i < size; i++)  
            b[i] = a[i] * a[i];  
  
        #pragma omp for nowait  
        for (i = 0; i < size; i++)  
            c[i] = a[i]/2;  
    }  
}  
  
int main( )   
{  
    int a[SIZE], b[SIZE], c[SIZE];  
    int i;  
  
    for (i=0; i<SIZE; i++)  
        a[i] = i;  
  
    test(a,b,c, SIZE);  
  
    for (i=0; i<SIZE; i++)  
        printf_s("%d, %d, %d\n", a[i], b[i], c[i]);  
}  
```  
  
```Output  
0, 0, 0  
1, 1, 0  
2, 4, 1  
3, 9, 1  
4, 16, 2  
```  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)