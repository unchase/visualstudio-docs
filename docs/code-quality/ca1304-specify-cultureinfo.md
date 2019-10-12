---
title: "CA1304: Specify CultureInfo"
ms.date: 06/30/2018
ms.topic: reference
f1_keywords:
  - "SpecifyCultureInfo"
  - "CA1304"
helpviewer_keywords:
  - "SpecifyCultureInfo"
  - "CA1304"
ms.assetid: b912d76a-54fd-4c93-b25d-16491e0ae319
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
---
# CA1304: Specify CultureInfo

|||
|-|-|
|TypeName|SpecifyCultureInfo|
|CheckId|CA1304|
|Category|Microsoft.Globalization|
|Breaking change|Non-breaking|

## Cause

A method or constructor calls a member that has an overload that accepts a <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> parameter, and the method or constructor does not call the overload that takes the <xref:System.Globalization.CultureInfo> parameter. This rule ignores calls to the following methods:

- <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>

## Rule description

When a <xref:System.Globalization.CultureInfo> or <xref:System.IFormatProvider?displayProperty=nameWithType> object is not supplied, the default value that is supplied by the overloaded member might not have the effect that you want in all locales. Also, .NET members choose default culture and formatting based on assumptions that might not be correct for your code. To ensure the code works as expected for your scenarios, you should supply culture-specific information according to the following guidelines:

- If the value will be displayed to the user, use the current culture. See <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.

- If the value will be stored and accessed by software, that is, persisted to a file or database, use the invariant culture. See <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.

- If you do not know the destination of the value, have the data consumer or provider specify the culture.

Even if the default behavior of the overloaded member is appropriate for your needs, it is better to explicitly call the culture-specific overload so that your code is self-documenting and more easily maintained.

> [!NOTE]
> <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> is used only to retrieve localized resources by using an instance of the <xref:System.Resources.ResourceManager?displayProperty=nameWithType> class.

## How to fix violations

To fix a violation of this rule, use the overload that takes a <xref:System.Globalization.CultureInfo> argument.

## When to suppress warnings

It is safe to suppress a warning from this rule when it is certain that the default culture is the correct choice, and where code maintainability is not an important development priority.

## Example showing how to fix violations

In the following example, `BadMethod` causes two violations of this rule. `GoodMethod` corrects the first violation by passing the invariant culture to <xref:System.String.Compare%2A?displayProperty=nameWithType>, and corrects the second violation by passing the current culture to <xref:System.String.ToLower%2A?displayProperty=nameWithType> because `string3` is displayed to the user.

[!code-csharp[FxCop.Globalization.CultureInfo#1](../code-quality/codesnippet/CSharp/ca1304-specify-cultureinfo_1.cs)]

## Example showing formatted output

The following example shows the effect of current culture on the default <xref:System.IFormatProvider> that is selected by the <xref:System.DateTime> type.

[!code-csharp[FxCop.Globalization.IFormatProvider#1](../code-quality/codesnippet/CSharp/ca1304-specify-cultureinfo_2.cs)]

This example produces the following output:

```txt
6/4/1900 12:15:12 PM
06/04/1900 12:15:12
```

## Related rules

- [CA1305: Specify IFormatProvider](../code-quality/ca1305-specify-iformatprovider.md)

## See also

- [Using the CultureInfo Class](/dotnet/standard/globalization-localization/globalization#work-with-culture-specific-settings)