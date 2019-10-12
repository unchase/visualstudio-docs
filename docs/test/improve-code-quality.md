---
title: "Testing tools"
ms.date: 03/16/2018
ms.topic: conceptual
helpviewer_keywords:
  - "testing tools [Visual Studio]"
  - "unit tests [Visual Studio]"
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
author: gewarren
---
# Testing tools in Visual Studio

Visual Studio testing tools can help you and your team develop and sustain high standards of code excellence.

> [!NOTE]
> Unit testing is available in all editions of Visual Studio. Other testing tools, such as Live Unit Testing, IntelliTest, and Coded UI Test, are only available in Visual Studio Enterprise edition. For more information about editions see [Compare Visual Studio IDEs](https://visualstudio.microsoft.com/vs/compare/).

## Test Explorer

The **Test Explorer** window helps developers create, manage, and run unit tests. You can use the Microsoft unit test framework or one of several third-party and open source frameworks.

::: moniker range="vs-2017"
![Visual Studio Test Explorer](media/devtest-testexplorer.png)
::: moniker-end

::: moniker range="vs-2019"
![Visual Studio Test Explorer 16.2](media/vs-2019/test-explorer-16-2.PNG)
::: moniker-end

* [Get started with unit testing](unit-test-your-code.md)
* [Run unit tests with Test Explorer](run-unit-tests-with-test-explorer.md)
* [Test Explorer FAQ](test-explorer-faq.md)
* [Install third-party unit test frameworks](install-third-party-unit-test-frameworks.md)

Visual Studio is also extensible and opens the door for third-party unit testing adapters such as NUnit and xUnit.net. In addition, the code clone capability goes hand-in-hand with delivering high-quality software by helping you identify blocks of semantically similar code that may be candidates for common bug fixes or refactoring.

![Third-party test integration](media/devtest-thirdparty.png)

## Live Unit Testing

[Live Unit Testing](../test/live-unit-testing.md) automatically runs unit tests in the background, and graphically displays code coverage and test results in the Visual Studio code editor.

## IntelliTest

IntelliTest automatically generates unit tests and test data for your managed code. IntelliTest improves coverage and dramatically reduces the effort to create and maintain unit tests for new or existing code.

![IntelliTest in action](media/devtest-intellitest.png)

* [Generate unit tests for your code with IntelliTest](generate-unit-tests-for-your-code-with-intellitest.md)
* [IntelliTest – One test to rule them all](https://devblogs.microsoft.com/devops/intellitest-one-test-to-rule-them-all/)
* [IntelliTest reference manual](intellitest-manual/index.md)

## Code coverage

[Code coverage](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md) determines what proportion of your project's code is actually being tested by coded tests such as unit tests. To guard effectively against bugs, your tests should exercise or "cover" a large proportion of your code.

Code coverage analysis can be applied to both managed and unmanaged (native) code.

Code coverage is an option when you run test methods using Test Explorer. The results table shows the percentage of the code that was run in each assembly, class, and method. In addition, the source editor shows you which code has been tested.

* [Use code coverage to determine how much code is being tested](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [Unit testing, code coverage and code clone analysis with Visual Studio (Lab)](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Unit%20Testing,%20Code%20Coverage%20and%20Code%20Clone%20Analysis%20with%20Visual%20Studio%202015.docx)
* [Customize code coverage analysis](customizing-code-coverage-analysis.md)

## Microsoft Fakes

[Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md) help you isolate the code you're testing by replacing other parts of the application with stubs or shims.

## User interface testing with Coded UI and Selenium

Coded UI tests provide a way to create fully automated tests to validate the functionality and behavior of your application’s user interface. They can automate UI testing across a variety of technologies, including XAML-based UWP apps, browser apps, and SharePoint apps.

Whether you choose best-of-breed Coded UI Tests or generic browser-based UI testing with Selenium, Visual Studio provides all the tools you need.

![UI testing with coded UI](media/devtest-codeduitest.png)

* [Use UI automation to test your code](use-ui-automation-to-test-your-code.md)
* [Get started creating, editing, and maintaining a coded UI test](walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)
* [Test UWP apps with coded UI tests](test-uwp-app-with-coded-ui-test.md)
* [Introduction to coded UI tests with Visual Studio Enterprise (Lab)](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Introduction%20to%20Coded%20UI%20Tests%20with%20Visual%20Studio%20Enterprise%202015.docx)

## Load testing

[Load testing](../test/quickstart-create-a-load-test-project.md) simulates load on a server application by running unit tests and web performance tests.

## Related scenarios

* [Exploratory & manual testing (Azure Test Plans)](/azure/devops/test/index?view=vsts)
* [Load testing (Azure Test Plans)](/azure/devops/test/load-test/index?view=vsts)
* [Continuous testing (Azure Test Plans)](/azure/devops/pipelines/test/getting-started-with-continuous-testing?view=vsts)
* [Code analysis tools](../code-quality/code-analysis-for-managed-code-overview.md)
