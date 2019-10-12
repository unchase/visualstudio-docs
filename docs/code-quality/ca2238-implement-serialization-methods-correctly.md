---
title: "CA2238: Implement serialization methods correctly"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
  - "ImplementSerializationMethodsCorrectly"
  - "CA2238"
helpviewer_keywords:
  - "ImplementSerializationMethodsCorrectly"
  - "CA2238"
ms.assetid: 00882cf9-e10d-4d40-9126-3e6753e3c934
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
 - CSharp
 - VB
ms.workload:
  - "multiple"
---
# CA2238: Implement serialization methods correctly

|||
|-|-|
|TypeName|ImplementSerializationMethodsCorrectly|
|CheckId|CA2238|
|Category|Microsoft.Usage|
|Breaking change|Breaking - If the method is visible outside the assembly.<br /><br /> Non-breaking - If the method is not visible outside the assembly.|

## Cause
A method that handles a serialization event does not have the correct signature, return type, or visibility.

## Rule description
A method is designated a serialization event handler by applying one of the following serialization event attributes:

- <xref:System.Runtime.Serialization.OnSerializingAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnSerializedAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnDeserializingAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnDeserializedAttribute?displayProperty=fullName>

  Serialization event handlers take a single parameter of type <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>, return `void`, and have `private` visibility.

## How to fix violations
To fix a violation of this rule, correct the signature, return type, or visibility of the serialization event handler.

## When to suppress warnings
Do not suppress a warning from this rule.

## Example
The following example shows correctly declared serialization event handlers.

[!code-vb[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/VisualBasic/ca2238-implement-serialization-methods-correctly_1.vb)]
[!code-csharp[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/CSharp/ca2238-implement-serialization-methods-correctly_1.cs)]

## Related rules
[CA2236: Call base class methods on ISerializable types](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

[CA2240: Implement ISerializable correctly](../code-quality/ca2240-implement-iserializable-correctly.md)

[CA2229: Implement serialization constructors](../code-quality/ca2229-implement-serialization-constructors.md)

[CA2235: Mark all non-serializable fields](../code-quality/ca2235-mark-all-non-serializable-fields.md)

[CA2237: Mark ISerializable types with SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

[CA2239: Provide deserialization methods for optional fields](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: Secure serialization constructors](../code-quality/ca2120-secure-serialization-constructors.md)