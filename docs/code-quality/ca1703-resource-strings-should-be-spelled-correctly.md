---
title: "CA1703: Resource strings should be spelled correctly"
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
  - "ResourceStringsShouldBeSpelledCorrectly"
  - "CA1703"
helpviewer_keywords:
  - "CA1703"
  - "ResourceStringsShouldBeSpelledCorrectly"
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
---
# CA1703: Resource strings should be spelled correctly

|||
|-|-|
|TypeName|ResourceStringsShouldBeSpelledCorrectly|
|CheckId|CA1703|
|Category|Microsoft.Naming|
|Breaking change|Non-breaking|

## Cause

A resource string contains one or more words that are not recognized by the Microsoft spelling checker library.

## Rule description

This rule parses the resource string into words (tokenizing compound words) and checks the spelling of each word/token. For information about the parsing algorithm, see [CA1704: Identifiers should be spelled correctly](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).

## How to fix violations

To fix a violation of this rule, use complete words that are correctly spelled or add the words to a custom dictionary. For information about how to use custom dictionaries, see [CA1704: Identifiers should be spelled correctly](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).

## Change the dictionary language

By default, the English (en) version of the spelling checker is used. If you want to change the language of the spelling checker, you can do so by adding one of the following attributes to your *AssemblyInfo.cs* or *AssemblyInfo.vb* file:

- Use <xref:System.Reflection.AssemblyCultureAttribute> to specify the culture if your resources are in a satellite assembly.
- Use <xref:System.Resources.NeutralResourcesLanguageAttribute> to specify the *neutral culture* of your assembly if your resources are in the same assembly as your code.

> [!IMPORTANT]
> If you set the culture to anything other than an English-based culture, this code analysis rule is silently disabled.

## When to suppress warnings

Do not suppress a warning from this rule. Correctly spelled words reduce the time that is required to learn new software libraries.

## Related rules

- [CA1701: Resource string compound words should be cased correctly](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1704: Identifiers should be spelled correctly](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA2204: Literals should be spelled correctly](../code-quality/ca2204-literals-should-be-spelled-correctly.md)