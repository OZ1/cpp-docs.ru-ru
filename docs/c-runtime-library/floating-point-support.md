---
title: Поддержка математических функций для чисел с плавающей запятой | Документы Майкрософт
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- c.math
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, math routines
- math routines
- floating-point numbers
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f78b7c09a1ce004b1d685c86eaaeb98580aa8e3
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2018
---
# <a name="math-and-floating-point-support"></a>Поддержка математических функций для чисел с плавающей запятой

Библиотека среды выполнения Microsoft C (CRT) предоставляет множество математических функций с плавающей точкой, включая все функции, предусмотренные ISO C99. Эти функции предназначены для балансировки производительности и правильности. Так как получение правильно округленного результата может оказаться неоправданно дорогим, эти функции позволяют получить значение, максимально приближенное к правильно округленному результату. В большинстве случаев результат будет соответствовать правильно округленному значению +/–1 ULP, хотя в некоторых случаях погрешность может быть выше.

Во многих функциях математической библиотеки с плавающей точкой используются различные реализации разной архитектуры ЦП. Например, в 32-разрядных CRT x86 могут использоваться не такие реализации, как в 64-разрядных CRT x64. Кроме того, некоторые функции могут содержать сразу несколько реализаций заданной архитектуры ЦП. Наиболее эффективная реализация выбирается в среде выполнения динамически в зависимости от того, какие наборы инструкций поддерживает ЦП. Например, в 32-разрядных CRT x86 некоторые функции включают сразу две реализации — x87 и SSE2. При работе на ЦП, который поддерживает SSE2, используется более быстрая реализация SSE2. При работе на ЦП, который не поддерживает SSE2, используется более медленная реализация x87. Так как различные реализации функций математической библиотеки могут использовать для получения результатов различные инструкции ЦП и разнообразные алгоритмы, эти функции могут давать различные результаты на разных ЦП. В большинстве случаев результаты находятся в пределах +/–1 ULP от правильно округленного результата, но фактические результаты могут отличаться в зависимости от ЦП.

В предыдущих 16-разрядных версиях Microsoft C/C++ и Microsoft Visual C++ тип **long double** поддерживался как тип данных с плавающей точкой 80-битной точности. В более поздних версиях Visual C++ тип данных **long double** представляет собой тип данных с плавающей запятой 64-битной точности, идентичный типу **double**. Компилятор трактует типы **long double** и **double** как разные типы, но функции для типа **long double** идентичны соответствующим функциям для типа **double**. Для обеспечения совместимости с исходным кодом ISO C99 в библиотеке CRT предоставляются версии математических функций для типа **long double**, но следует иметь в виду, что двоичное представление этих функций может быть не таким, как в других компиляторах.

## <a name="supported-math-and-floating-point-routines"></a>Поддерживаемые математические функции для чисел с плавающей запятой

[abs, labs, llabs, _abs64](../c-runtime-library/reference/abs-labs-llabs-abs64.md)

[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)

[acosh, acoshf, acoshl](../c-runtime-library/reference/acosh-acoshf-acoshl.md)

[asin, asinf, asinl](../c-runtime-library/reference/asin-asinf-asinl.md)

[asinh, asinhf, asinhl](../c-runtime-library/reference/asinh-asinhf-asinhl.md)

[atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)

[atanh, atanhf, atanhl](../c-runtime-library/reference/atanh-atanhf-atanhl.md)

[_atodbl, _atodbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)

[atof, _atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)

[_atoflt, _atoflt_l, _atoldbl, _atoldbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)

[cbrt, cbrtf, cbrtl](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)

[ceil, ceilf, ceill](../c-runtime-library/reference/ceil-ceilf-ceill.md)

[_chgsign, _chgsignf, _chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)

[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)

[conj, conjf, conjl](../c-runtime-library/reference/conj-conjf-conjl.md)

[_control87, \__control87_2, _controlfp](../c-runtime-library/reference/control87-controlfp-control87-2.md)

[_controlfp_s](../c-runtime-library/reference/controlfp-s.md)

[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)

[cos, cosf, cosl](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)

[cosh, coshf, coshl](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)

[div](../c-runtime-library/reference/div.md)

[_ecvt](../c-runtime-library/reference/ecvt.md)

[ecvt](../c-runtime-library/reference/posix-ecvt.md)

[_ecvt_s](../c-runtime-library/reference/ecvt-s.md)

[erf, erff, erfl, erfc, erfcf, erfcl](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)

[exp, expf, expl](../c-runtime-library/reference/exp-expf.md)

[exp2, exp2f, exp2l](../c-runtime-library/reference/exp2-exp2f-exp2l.md)

[expm1, expm1f, expm1l](../c-runtime-library/reference/expm1-expm1f-expm1l.md)

[fabs, fabsf](../c-runtime-library/reference/fabs-fabsf-fabsl.md)

[_fcvt](../c-runtime-library/reference/fcvt.md)

[fcvt](../c-runtime-library/reference/posix-fcvt.md)

[_fcvt_s](../c-runtime-library/reference/fcvt-s.md)

[fdim, fdimf, fdiml](../c-runtime-library/reference/fdim-fdimf-fdiml.md)

[feclearexcept](../c-runtime-library/reference/feclearexcept1.md)

[fegetenv](../c-runtime-library/reference/fegetenv1.md)

[fegetexceptflag](../c-runtime-library/reference/fegetexceptflag2.md)

[fegetround](../c-runtime-library/reference/fegetround-fesetround2.md)

[feholdexcept](../c-runtime-library/reference/feholdexcept2.md)

[feraiseexcept](../c-runtime-library/reference/feraiseexcept.md)

[ferror](../c-runtime-library/reference/ferror.md)

[fesetenv](../c-runtime-library/reference/fesetenv1.md)

[fesetexceptflag](../c-runtime-library/reference/fesetexceptflag2.md)

[fesetround](../c-runtime-library/reference/fegetround-fesetround2.md)

[fetestexcept](../c-runtime-library/reference/fetestexcept1.md)

[feupdateenv](../c-runtime-library/reference/feupdateenv.md)

[_finite, _finitef](../c-runtime-library/reference/finite-finitef.md)

[floor, floorf, floorl](../c-runtime-library/reference/floor-floorf-floorl.md)

[fma, fmaf, fmal](../c-runtime-library/reference/fma-fmaf-fmal.md)

[fmax, fmaxf, fmaxl](../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)

[fmin, fminf, fminl](../c-runtime-library/reference/fmin-fminf-fminl.md)

[fmod, fmodf](../c-runtime-library/reference/fmod-fmodf.md)

[_fpclass, _fpclassf](../c-runtime-library/reference/fpclass-fpclassf.md)

[fpclassify](../c-runtime-library/reference/fpclassify.md)

[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)

[_fpreset](../c-runtime-library/reference/fpreset.md)

[frexp](../c-runtime-library/reference/frexp.md)

[gcvt](../c-runtime-library/reference/posix-gcvt.md)

[_gcvt](../c-runtime-library/reference/gcvt.md)

[_gcvt_s](../c-runtime-library/reference/gcvt-s.md)

[_get_FMA3_enable, _set_FMA3_enable](../c-runtime-library/reference/get-fma3-enable-set-fma3-enable.md)

[hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)

[ilogb, ilogbf, ilogbl](../c-runtime-library/reference/ilogb-ilogbf-ilogbl2.md)

[imaxabs](../c-runtime-library/reference/imaxabs.md)

[imaxdiv](../c-runtime-library/reference/imaxdiv.md)

[isnan, _isnan, _isnanf](../c-runtime-library/reference/isnan-isnan-isnanf.md)

[_j0, _j1, _jn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)

[ldexp](../c-runtime-library/reference/ldexp.md)

[ldiv, lldiv](../c-runtime-library/reference/ldiv-lldiv.md)

[lgamma, lgammaf, lgammal](../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)

[llrint, llrintf, llrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)

[llround, llroundf, llroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)

[log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)

[log1p, log1pf, log1pl](../c-runtime-library/reference/log1p-log1pf-log1pl2.md)

[log2, log2f, log2l](../c-runtime-library/reference/log2-log2f-log2l.md)

[logb, logbf, logbl, _logb, _logbf](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)

[lrint, lrintf, lrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)

[_lrotl, _lrotr](../c-runtime-library/reference/lrotl-lrotr.md)

[lround, lroundf, lroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)

[_matherr](../c-runtime-library/reference/matherr.md)

[__max](../c-runtime-library/reference/max.md)

[__min](../c-runtime-library/reference/min.md)

[modf, modff](../c-runtime-library/reference/modf-modff-modfl.md)

[nan, nanf, nanl](../c-runtime-library/reference/nan-nanf-nanl.md)

[nanf](../c-runtime-library/reference/nan-nanf-nanl.md)

[nanl](../c-runtime-library/reference/nan-nanf-nanl.md)

[nearbyint, nearbyintf, nearbyintl](../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)

[nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl](../c-runtime-library/reference/nextafter-functions.md)

[pow, powf, powl](../c-runtime-library/reference/pow-powf-powl.md)

[remainder, remainderf, remainderl](../c-runtime-library/reference/remainder-remainderf-remainderl.md)

[remquo, remquof, remquol](../c-runtime-library/reference/remquo-remquof-remquol.md)

[rint, rintf, rintl](../c-runtime-library/reference/rint-rintf-rintl.md)

[_rotl, _rotl64, _rotr, _rotr64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)

[round, roundf, roundl](../c-runtime-library/reference/round-roundf-roundl.md)

[_scalb](../c-runtime-library/reference/scalb.md)

[scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)

[_set_controlfp](../c-runtime-library/reference/set-controlfp.md)

[_set_SSE2_enable](../c-runtime-library/reference/set-sse2-enable.md)

[sin, sinf, sinl](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)

[sinh, sinhf, sinhl](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)

[sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)

[_status87, _statusfp, _statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)

[strtof, _strtof_l](../c-runtime-library/reference/strtof-strtof-l-wcstof-wcstof-l.md)

[strtold, _strtold_l](../c-runtime-library/reference/strtold-strtold-l-wcstold-wcstold-l.md)

[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)

[tanh, tanhf, tanhl](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)

[tgamma, tgammaf, tgammal](../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)

[trunc, truncf, truncl](../c-runtime-library/reference/trunc-truncf-truncl.md)

[_wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)

[_y0, _y1, _yn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)

## <a name="see-also"></a>См. также

[Подпрограммы среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
