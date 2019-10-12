---
title: "Tutorial 2: Create a timed math quiz"
ms.date: 11/04/2016
ms.assetid: d7165d08-ace3-457d-b57d-fb8f80760a6f
ms.topic: tutorial
ms.technology: vs-ide-general
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
  - "multiple"
---
# Tutorial 2: Create a timed math quiz

In this tutorial, you build a quiz in which the quiz taker must answer four random arithmetic problems within a specified time. You learn how to:

- Generate random numbers by using the <xref:System.Random> class.

- Trigger events to occur at a specific time by using a <xref:System.Windows.Forms.Timer> control.

- Control program flow by using `if else` statements.

- Perform basic arithmetic operations in code.

When you finish, your quiz will look similar to the following screenshot, except with different numbers:

![Math quiz with four problems](../ide/media/express_finishedquiz.png)

## Tutorial links

To download a completed version of the quiz, see [Complete math quiz tutorial sample](https://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).

> [!NOTE]
> This tutorial covers both C# and Visual Basic, so focus on the information that's specific to the programming language that you're using.

## Related topics

|Title|Description|
|-----------|-----------------|
|[Step 1: Create a project and add labels to your form](../ide/step-1-create-a-project-and-add-labels-to-your-form.md)|Start by creating the project, changing properties, and adding `Label` controls.|
|[Step 2: Create a random addition problem](../ide/step-2-create-a-random-addition-problem.md)|Create an addition problem, and use the `Random` class to generate random numbers.|
|[Step 3: Add a countdown timer](../ide/step-3-add-a-countdown-timer.md)|Add a countdown timer so that the quiz can be timed.|
|[Step 4: Add the CheckTheAnswer() method](../ide/step-4-add-the-checktheanswer-parens-method.md)|Add a method to check whether the quiz taker entered a correct answer for the problem.|
|[Step 5: Add Enter event handlers for the NumericUpDown controls](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md)|Add event handlers that make your quiz easier to take.|
|[Step 6: Add a subtraction problem](../ide/step-6-add-a-subtraction-problem.md)|Add a subtraction problem that generates random numbers, uses the timer, and checks for correct answers.|
|[Step 7: Add multiplication and division problems](../ide/step-7-add-multiplication-and-division-problems.md)|Add multiplication and division problems that generate random numbers, use the timer, and check for correct answers.|
|[Step 8: Customize the quiz](../ide/step-8-customize-the-quiz.md)|Try other features, such as changing colors and adding a hint.|
