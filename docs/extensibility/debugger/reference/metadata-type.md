---
description: "The METADATA_TYPE structure specifies information about a field type taken from metadata."
title: METADATA_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- METADATA_TYPE
helpviewer_keywords:
- METADATA_TYPE structure
ms.assetid: 2d8b78f6-0aef-4d79-809a-cff9b2c24659
author: maiak
ms.author: maiak
manager: jmartens
ms.technology: vs-ide-debug
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
---
# METADATA_TYPE

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]
This structure specifies information about a field type taken from metadata.

## Syntax

### [C#](#tab/csharp)
```csharp
public struct METADATA_TYPE {
   public uint ulAppDomainID;
   public Guid guidModule;
   public int  tokClass;
};
```
### [C++](#tab/cpp)
```cpp
typedef struct _tagTYPE_METADATA {
   ULONG32  ulAppDomainID;
   GUID     guidModule;
   _mdToken tokClass;
} METADATA_TYPE;
```
---

## Parameters
 `ulAppDomainID`\
 ID of the application from which the symbol came. This is used to uniquely identify an instance of the application.

 `guidModule`\
 The GUID of the module that contains this field.

 `tokClass`\
 The metadata token ID of this type.

 [C++] `_mdToken` is a `typedef` for a 32-bit `int`.

## Remarks
 This structure appears as part of the union in the [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) structure when the `dwKind` field of the `TYPE_INFO` structure is set to `TYPE_KIND_METADATA` (a value from the [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) enumeration).

 The `tokClass` value is a metadata token that uniquely identifies a type. For details on how to interpret the upper bits of the metadata token ID, see the `CorTokenType` enumeration in the corhdr.h file in the .NET Framework SDK.

## Requirements
 Header: sh.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## See also
- [Structures and Unions](../../../extensibility/debugger/reference/structures-and-unions.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)
- [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)
