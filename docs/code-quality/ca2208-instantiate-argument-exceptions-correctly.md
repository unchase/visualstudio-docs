---
title: "CA2208: Instantiate argument exceptions correctly"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
  - "CA2208"
  - "InstantiateArgumentExceptionsCorrectly"
helpviewer_keywords:
  - "InstantiateArgumentExceptionsCorrectly"
  - "CA2208"
ms.assetid: e2a48939-d9fa-478c-b2f9-3bdbce07dff7
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
# CA2208: Instantiate argument exceptions correctly

|||
|-|-|
|TypeName|InstantiateArgumentExceptionsCorrectly|
|CheckId|CA2208|
|Category|Microsoft.Usage|
|Breaking change|Non-breaking|

## Cause

Possible causes include the following situations:

- A call is made to the default (parameterless) constructor of an exception type that is, or derives from, <xref:System.ArgumentException>.

- An incorrect string argument is passed to a parameterized constructor of an exception type that is, or derives from, <xref:System.ArgumentException>.

## Rule description

Instead of calling the default constructor, call one of the constructor overloads that allows a more meaningful exception message to be provided. The exception message should target the developer and clearly explain the error condition and how to correct or avoid the exception.

The signatures of the one and two string constructors of <xref:System.ArgumentException> and its derived types are not consistent with respect to the position `message` and `paramName` parameters. Make sure these constructors are called with the correct string arguments. The signatures are as follows:

- <xref:System.ArgumentException>(string `message`)
- <xref:System.ArgumentException>(string `message`, string `paramName`)
- <xref:System.ArgumentNullException>(string `paramName`)
- <xref:System.ArgumentNullException>(string `paramName`, string `message`)
- <xref:System.ArgumentOutOfRangeException>(string `paramName`)
- <xref:System.ArgumentOutOfRangeException>(string `paramName`, string `message`)
- <xref:System.DuplicateWaitObjectException>(string `parameterName`)
- <xref:System.DuplicateWaitObjectException>(string `parameterName`, string `message`)

## How to fix violations

To fix a violation of this rule, call a constructor that takes a message, a parameter name, or both, and make sure the arguments are proper for the type of <xref:System.ArgumentException> being called.

## When to suppress warnings

It's safe to suppress a warning from this rule only if a parameterized constructor is called with the correct string arguments.

## Example

The following code shows a constructor that incorrectly instantiates an instance of <xref:System.ArgumentNullException>.

[!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_1.cpp)]
[!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_1.cs?range=3-6)]
[!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_1.vb)]

The following code fixes the previous violation by switching the constructor arguments.

[!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_2.cpp)]
[!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_2.cs?range=3-6)]
[!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_2.vb)]

## Related rules

- [CA1507: Use nameof in place of string](ca1507.md)