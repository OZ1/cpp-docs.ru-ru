---
title: Норма, normf, norml | Документы Microsoft
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- norm
- normf
- norml
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- norm
- normf
- norml
- complex/norm
- complex/normf
- complex/norml
dev_langs:
- C++
helpviewer_keywords:
- norm function
- normf function
- norml function
ms.assetid: 9786ecfe-0019-4553-b378-0af6c691e15c
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28c8e05dfc2cc9e42584324a78ba14f37a9b951d
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2018
---
# <a name="norm-normf-norml"></a>norm, normf, norml

Возвращает абсолютное значение комплексного числа в квадрате.

## <a name="syntax"></a>Синтаксис

```C
double norm( _Dcomplex z );
float normf( _Fcomplex z );
long double norml( _Lcomplex z );
```

```cpp
float norm( _Fcomplex z );  // C++ only
long double norm( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Параметры

*z*<br/>
Комплексное число.

## <a name="return-value"></a>Возвращаемое значение

Квадрат величина *z*.

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки `norm` , которые принимают **_Fcomplex** или **_Lcomplex** значений и возвращают **float** или **long двойные** значения. В программе на языке C `norm` всегда принимает **_Dcomplex** значения и возвращает **двойные** значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|`norm`, `normf`, `norml`|\<complex.h>|\<ccomplex>|

**_Fcomplex**, **_Dcomplex**, и **_Lcomplex** типы являются эквивалентами характерные для Майкрософт нереализованные собственных типов C99 **float _Complex** , **двойные _Complex**, и **long double _Complex**соответственно.  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)<br/>
