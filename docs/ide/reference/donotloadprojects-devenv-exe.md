---
title: -DoNotLoadProjects (devenv.exe)
ms.date: 04/30/2019
ms.topic: reference
helpviewer_keywords:
  - "Devenv, /DoNotLoadProjects switch"
  - "/DoNotLoadProjects Devenv switch"
  - "DoNotLoadProjects Devenv switch"
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
---
# /DoNotLoadProjects (devenv.exe)

**New for Visual Studio 2019 version 16.1**

Opens the specified solution without loading any projects. For more information, see [Filtered solutions in Visual Studio](../filtered-solutions.md).

## Syntax

```shell
devenv /DoNotLoadProjects SolutionName
```

## Arguments

*SolutionName*

Required. The full path and name of the solution to be opened.

## Example

The example opens the solution MySln.sln without loading any projects.

```shell
devenv /donotloadprojects MySln.sln
```

## See also

- [Filtered solutions in Visual Studio](../filtered-solutions.md)
- [Devenv command-line switches](../../ide/reference/devenv-command-line-switches.md)
