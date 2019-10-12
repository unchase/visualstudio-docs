---
title: "CA1047: Do not declare protected members in sealed types"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
  - "DoNotDeclareProtectedMembersInSealedTypes"
  - "CA1047"
helpviewer_keywords:
  - "CA1047"
  - "DoNotDeclareProtectedMembersInSealedTypes"
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
 - CSharp
 - VB
ms.workload:
  - "multiple"
---
# CA1047: Do not declare protected members in sealed types

|||
|-|-|
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|
|CheckId|CA1047|
|Category|Microsoft.Design|
|Breaking change|Non-breaking|

## Cause
A public type is `sealed` (`NotInheritable` in Visual basic) and declares a protected member or a protected nested type. This rule does not report violations for <xref:System.Object.Finalize%2A> methods, which must follow this pattern.

## Rule description
Types declare protected members so that inheriting types can access or override the member. By definition, you cannot inherit from a sealed type, which means that protected methods on sealed types cannot be called.

The C# compiler issues a warning for this error.

## How to fix violations
To fix a violation of this rule, change the access level of the member to private, or make the type inheritable.

## When to suppress warnings
Do not suppress a warning from this rule. Leaving the type in its current state can cause maintenance issues and does not provide any benefits.

## Example
The following example shows a type that violates this rule.

[!code-vb[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/VisualBasic/ca1047-do-not-declare-protected-members-in-sealed-types_1.vb)]
[!code-csharp[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/CSharp/ca1047-do-not-declare-protected-members-in-sealed-types_1.cs)]