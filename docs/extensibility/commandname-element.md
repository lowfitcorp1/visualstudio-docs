---
title: CommandName Element | Microsoft Docs
description: The CommandName element specifies the text that appears in the keyboard category in the Options dialog box and in the Commands list in the Customize dialog box.
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- CommandName element (VSCT XML schema)
- VSCT XML schema elements, CommandName
ms.assetid: a338b767-aa7e-4536-9908-e19a50ab60ac
author: maiak
ms.author: maiak
manager: jmartens
ms.technology: vs-ide-sdk
ms.workload:
- vssdk
---
# CommandName element

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]
The `CommandName` element specifies the text that appears in the keyboard category in the **Options** dialog box, and in the **Commands** list in the **Customize** dialog box.

## Syntax

```
<CommandName>MyCommand</CommandName>
```

## Attributes and elements
 The following sections describe attributes, child elements, and parent elements.

### Attributes
 None.

### Child elements
 None.

### Parent elements

|Element|Description|
|-------------|-----------------|
|[Strings element](../extensibility/strings-element.md)|Groups text elements, such as `ButtonText` and `CommandName`.|

## See also
- [Visual Studio command table (.vsct) files](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
