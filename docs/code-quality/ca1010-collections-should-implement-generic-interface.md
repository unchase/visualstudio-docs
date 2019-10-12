---
title: "CA1010: Collections should implement generic interface"
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
  - "CA1010"
  - "CollectionsShouldImplementGenericInterface"
helpviewer_keywords:
  - "CA1010"
  - "CollectionsShouldImplementGenericInterface"
ms.assetid: c7d7126f-fa70-40be-8f93-3243e1760dc5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
---
# CA1010: Collections should implement generic interface

|||
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|CheckId|CA1010|
|Category|Microsoft.Design|
|Breaking change|Non-breaking|

## Cause

A type implements the <xref:System.Collections.IEnumerable?displayProperty=fullName> interface but does not implement the <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interface, and the containing assembly targets .NET. This rule ignores types that implement <xref:System.Collections.IDictionary?displayProperty=fullName>.

By default, this rule only looks at externally visible types, but this is [configurable](#configurability).

## Rule description

To broaden the usability of a collection, implement one of the generic collection interfaces. Then the collection can be used to populate generic collection types such as the following:

- <xref:System.Collections.Generic.List%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## How to fix violations

To fix a violation of this rule, implement one of the following generic collection interfaces:

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>
- <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>
- <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## When to suppress warnings

It is safe to suppress a warning from this rule; however, the use of the collection will be more limited.

## Configurability

If you're running this rule from [FxCop analyzers](install-fxcop-analyzers.md) (and not with legacy analysis), you can configure which parts of your codebase to run this rule on, based on their accessibility. For example, to specify that the rule should run only against the non-public API surface, add the following key-value pair to an .editorconfig file in your project:

```ini
dotnet_code_quality.ca1010.api_surface = private, internal
```

You can configure this option for just this rule, for all rules, or for all rules in this category (Design). For more information, see [Configure FxCop analyzers](configure-fxcop-analyzers.md).

## Example violation

The following example shows a class (reference type) that derives from the non-generic `CollectionBase` class, which violates this rule.

[!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]

To fix a violation of this rule, do one of the following:

- Implement the generic interfaces.
- Change the base class to a type that already implements both the generic and non-generic interfaces, such as the `Collection<T>` class.

## Fix by base class change

The following example fixes the violation by changing the base class of the collection from the non-generic `CollectionBase` class to the generic `Collection<T>` (`Collection(Of T)` in Visual Basic) class.

[!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]

Changing the base class of an already released class is considered a breaking change to existing consumers.

## Fix by interface implementation

The following example fixes the violation by implementing these generic interfaces: `IEnumerable<T>`, `ICollection<T>`, and `IList<T>` (`IEnumerable(Of T)`, `ICollection(Of T)`, and `IList(Of T)` in Visual Basic).

[!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]

## Related rules

- [CA1005: Avoid excessive parameters on generic types](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1000: Do not declare static members on generic types](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002: Do not expose generic lists](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006: Do not nest generic types in member signatures](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004: Generic methods should provide type parameter](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1003: Use generic event handler instances](../code-quality/ca1003-use-generic-event-handler-instances.md)
- [CA1007: Use generics where appropriate](../code-quality/ca1007-use-generics-where-appropriate.md)

## See also

- [Generics](/dotnet/csharp/programming-guide/generics/index)