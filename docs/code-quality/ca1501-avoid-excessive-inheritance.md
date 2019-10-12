---
title: "CA1501: Avoid excessive inheritance"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
  - "CA1501"
  - "AvoidExcessiveInheritance"
helpviewer_keywords:
  - "AvoidExcessiveInheritance"
  - "CA1501"
ms.assetid: 9e934746-1a4d-492a-91e4-085201abafa4
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
 - CSharp
 - VB
ms.workload:
  - "multiple"
---
# CA1501: Avoid excessive inheritance

|||
|-|-|
|TypeName|AvoidExcessiveInheritance|
|CheckId|CA1501|
|Category|Microsoft.Maintainability|
|Breaking change|Breaking|

## Cause

A type is more than four levels deep in its inheritance hierarchy.

## Rule description

Deeply nested type hierarchies can be difficult to follow, understand, and maintain. This rule limits analysis to hierarchies in the same module.

## How to fix violations

To fix a violation of this rule, derive the type from a base type that is less deep in the inheritance hierarchy or eliminate some of the intermediate base types.

## When to suppress warnings

It is safe to suppress a warning from this rule. However, the code might be more difficult to maintain. Note that, depending on the visibility of base types, resolving violations of this rule might create breaking changes. For example, removing public base types is a breaking change.

## Example

The following example shows a type that violates the rule:

[!code-csharp[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/CSharp/ca1501-avoid-excessive-inheritance_1.cs)]
[!code-vb[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/VisualBasic/ca1501-avoid-excessive-inheritance_1.vb)]