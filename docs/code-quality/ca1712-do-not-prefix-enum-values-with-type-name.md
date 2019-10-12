---
title: "CA1712: Do not prefix enum values with type name"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
  - "CA1712"
  - "DoNotPrefixEnumValuesWithTypeName"
helpviewer_keywords:
  - "CA1712"
  - "DoNotPrefixEnumValuesWithTypeName"
ms.assetid: df0e3a12-67bf-48f1-a10b-2ef60484a5c7
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
 - CPP
 - CSharp
 - VB
ms.workload:
  - "multiple"
---
# CA1712: Do not prefix enum values with type name

|||
|-|-|
|TypeName|DoNotPrefixEnumValuesWithTypeName|
|CheckId|CA1712|
|Category|Microsoft.Naming|
|Breaking change|Breaking|

## Cause
An enumeration contains a member whose name starts with the type name of the enumeration.

## Rule description
Names of enumeration members are not prefixed with the type name because type information is expected to be provided by development tools.

Naming conventions provide a common look for libraries that target the common language runtime. This reduces the time that is required for to learn a new software library, and increases customer confidence that the library was developed by someone who has expertise in developing managed code.

## How to fix violations
To fix a violation of this rule, remove the type name prefix from the enumeration member.

## When to suppress warnings
Do not suppress a warning from this rule.

## Example
The following example shows an incorrectly named enumeration followed by the corrected version.

[!code-csharp[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/CSharp/ca1712-do-not-prefix-enum-values-with-type-name_1.cs)]
[!code-cpp[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/CPP/ca1712-do-not-prefix-enum-values-with-type-name_1.cpp)]
[!code-vb[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/VisualBasic/ca1712-do-not-prefix-enum-values-with-type-name_1.vb)]

## Related rules
[CA1711: Identifiers should not have incorrect suffix](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)

[CA1027: Mark enums with FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

[CA2217: Do not mark enums with FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## See also

- <xref:System.Enum?displayProperty=fullName>