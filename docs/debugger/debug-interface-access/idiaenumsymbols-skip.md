---
description: "Skips a specified number of symbols in an enumeration sequence."
title: "IDiaEnumSymbols::Skip | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "reference"
dev_langs:
  - "C++"
helpviewer_keywords:
  - "IDiaEnumSymbols::Skip method"
ms.assetid: e601fbc9-b10b-41c7-8180-959e57efabe8
author: "mikejo5000"
ms.author: "mikejo"
manager: jmartens
ms.technology: vs-ide-debug
ms.workload:
  - "multiple"
---
# IDiaEnumSymbols::Skip

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]
Skips a specified number of symbols in an enumeration sequence.

## Syntax

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### Parameters
 celt

[in] The number of symbols in the enumeration sequence to skip.

## Return Value
 If successful, returns `S_OK`; otherwise, returns `S_FALSE` if there are no more symbols to skip.

## See also
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
