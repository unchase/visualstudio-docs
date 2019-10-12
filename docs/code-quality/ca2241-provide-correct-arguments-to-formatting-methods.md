---
title: "CA2241: Provide correct arguments to formatting methods"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
  - "CA2241"
  - "Provide correct arguments to formatting methods"
  - "ProvideCorrectArgumentsToFormattingMethods"
helpviewer_keywords:
  - "ProvideCorrectArgumentsToFormattingMethods"
  - "CA2241"
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
 - CSharp
 - VB
ms.workload:
  - "multiple"
---
# CA2241: Provide correct arguments to formatting methods

|||
|-|-|
|TypeName|ProvideCorrectArgumentsToFormattingMethods|
|CheckId|CA2241|
|Category|Microsoft.Usage|
|Breaking change|Non-breaking|

## Cause
The `format` string argument passed to a method such as <xref:System.Console.WriteLine%2A>,  <xref:System.Console.Write%2A>, or  <xref:System.String.Format%2A?displayProperty=fullName> does not contain a format item that corresponds to each object argument, or vice versa.

## Rule description
The arguments to methods such as <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, and <xref:System.String.Format%2A> consist of a format string followed by several <xref:System.Object?displayProperty=fullName> instances. The format string consists of text and embedded format items of the form, {index[,alignment][:formatString]}. 'index' is a zero-based integer that indicates which of the objects to format. If an object does not have a corresponding index in the format string, the object is ignored. If the object specified by 'index' does not exist, a <xref:System.FormatException?displayProperty=fullName> is thrown at run time.

## How to fix violations
To fix a violation of this rule, provide a format item for each object argument and provide an object argument for each format item.

## When to suppress warnings
Do not suppress a warning from this rule.

## Example
The following example shows two violations of the rule.

[!code-vb[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/VisualBasic/ca2241-provide-correct-arguments-to-formatting-methods_1.vb)]
[!code-csharp[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/CSharp/ca2241-provide-correct-arguments-to-formatting-methods_1.cs)]