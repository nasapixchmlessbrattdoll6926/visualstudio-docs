---
description: "Retrieves the children of the symbol that are valid at a specified relative virtual address (RVA)."
title: "IDiaSymbol::findChildrenExByRVA"
ms.date: "11/04/2016"
ms.topic: "reference"
dev_langs:
  - "C++"
helpviewer_keywords:
  - "IDiaSymbol::findChildrenExByRVA"
author: "mikejo5000"
ms.author: "mikejo"
manager: jmartens
ms.subservice: debug-diagnostics
---
# IDiaSymbol::findChildrenExByRVA

Retrieves the children of the symbol that are valid at a specified relative virtual address (RVA).

## Syntax

```C++
HRESULT findChildrenExByRVA ( 
   enum SymTagEnum   symtag,
   LPCOLESTR         name,
   DWORD             compareFlags,
   DWORD             address,
   IDiaEnumSymbols** ppResult
);
```

#### Parameters
 `symtag`

[in] Specifies the symbol tags of the children to be retrieved, as defined in the [SymTagEnum Enumeration](../../debugger/debug-interface-access/symtagenum.md). Set to `SymTagNull` for all children to be retrieved.

 `name`

[in] Specifies the name of the children to be retrieved. Set to `NULL` for all children to be retrieved.

 `compareFlags`

[in] Specifies the comparison options to be applied to name matching. Values from the [NameSearchOptions Enumeration](../../debugger/debug-interface-access/namesearchoptions.md) enumeration can be used alone or in combination.

 `address`

[in] Specifies the RVA.

 `ppResult`

[out] Returns an [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) object that contains a list of the child symbols retrieved.

## Return Value
 Returns `S_OK` if at least one child of the symbol was found, or returns `S_FALSE` if no children were found; otherwise, returns an error code.

## Remarks
 The local symbols that are returned include live range information.

## Requirements
 Header: Dia2.h

 Library: diaguids.lib

 DLL: msdia100.dll

## See also
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum Enumeration](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)
- [NameSearchOptions Enumeration](../../debugger/debug-interface-access/namesearchoptions.md)
