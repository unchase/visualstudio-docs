---
title: Toggle Breakpoint Command
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
  - "debug.togglebreakpoint"
helpviewer_keywords:
  - "ToggleBreakpoint command"
  - "Debug.ToggleBreakPoint command"
  - "Toggle Breakpoint command"
ms.assetid: d50dfadb-ce79-4d5e-9c09-1cfddd57876d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
---
# Toggle Breakpoint Command
Turns the breakpoint either on or off, depending on its current state, at the current location in the file.

## Syntax

```
Debug.ToggleBreakpoint [text]
```

## Arguments

`text`\
Optional. If text is specified, the line is marked as a named breakpoint. Otherwise, the line is marked as an unnamed breakpoint, which is similar to what happens when you press F9.

## Example
The following example toggles the current breakpoint.

```
>Debug.ToggleBreakpoint
```

## See Also

- [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)
- [Command Window](../../ide/reference/command-window.md)
- [Find/Command Box](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)