---
title: VisualStudio.Extensibility overview
description: Learn about the Visual Studio Extensibility model for adding custom functionality to Visual Studio.
ms.topic: overview
ms.date: 3/31/2023
ms.author: maiak
monikerRange: ">=vs-2022"
author: maiak
manager: jmartens
ms.subservice: extensibility-integration
---

# About VisualStudio.Extensibility (Preview)

VisualStudio.Extensibility is a new framework for developing Visual Studio extensions that focuses primarily on extensions that run out-of-process from the IDE for improved performance and reliability. It features a modern, asynchronous API that has been streamlined and carefully engineered to maximize developer productivity. VisualStudio.Extensibility is in active development and is available as a preview.

With the current preview, you can develop a wide range of extensions to Visual Studio, including creating commands, working with code or text in the editor, displaying prompts or dialogs to the user, creating debugger visualizers, and more!

VisualStudio.Extensibility aims to address many of the problems developers experience when using and writing extensions in Visual Studio. Writing extensions using VisualStudio.Extensibility provides the following benefits:

* **Increased reliability**: Visual Studio remains responsive and won't crash if an extension crashes or hangs.
* **Reduced API complexity**: VisualStudio.Extensibility has simplified architecture, consistent APIs, and clear documentation.
* **Hot-loading functionality**: Visual Studio doesn't need to be restarted when installing extensions.

Eventually, you will be able to use the VisualStudio.Extensibility SDK to write any extension you could write using the VS SDK. However, until that time, you might encounter situations where the functionality you need in your extension isn't yet available in VisualStudio.Extensibility. In that case, you can use VisualStudio.Extensibility SDK together with VS SDK running in-process to cover any feature gap. To learn more, see [In-proc extensions](./get-started/in-proc-extensions.md).

The latest information on VisualStudio.Extensibility may be found in the VSExtensibility GitHub repo at [announcements](https://github.com/microsoft/VSExtensibility/blob/main/docs/announcements.md).

## Navigate the documentation

| Article | Description|
|-|-|
| [Install VisualStudio.Extensibility](#install-visualstudioextensibility) | Download and install the latest preview of VisualStudio.Extensibility. |
| [Get started](#get-started) | Start with beginner quickstarts and introductory tutorials if you've never developed an extension before. |
| [Concepts](#concepts) | Build your mental model of how the SDK and extensions work. |
| [Overviews](#overviews) | Learn more by reading overviews of each major area of functionality. |
| [Samples](#samples-and-tutorials) | Explore sample code demonstrating major features. |
| [API reference](#api-docs) | Browse the VisualStudio.Extensibility API documentation. |
| [Experimental APIs and Breaking Changes](#experimental-apis-and-breaking-changes) | Learn about our approach to stable-vs-experimental APIs and about breaking changes from the previous version. |
| [Known Issues](#known-issues) | View known issues with the VisualStudio.Extensibility SDK. |
| [Advanced topics](#advanced-topics) | Learn implementation details of the VisualStudio.Extensibility SDK. |

## Install VisualStudio.Extensibility

The current VisualStudio.Extensibility preview works with Visual Studio 2022 version 17.9 Preview 1 or higher with the `Visual Studio extension development` workload to be installed.

## Get started

The following articles help you get oriented and started"

* [Create your first Visual Studio extension](./get-started/create-your-first-extension.md) shows how to create the equivalent of "Hello, world" as an extension.
*  [Create a simple extension](./get-started/tutorial-create-simple-extension.md) shows you how to create a more interesting extension that adds a GUID to the editor window.

To understand how to work with VisualStudio.Extensibility, we recommend a thorough understanding of [asynchronous programming with async and await](/dotnet/csharp/programming-guide/concepts/async/) and [dependency injection](/dotnet/core/extensions/dependency-injection). In addition, UI in VisualStudio.Extensibility is based on Windows Presentation Foundation (WPF), so you might want to review the [WPF documentation](/dotnet/desktop/wpf/).

## Concepts

If you're familiar with the Visual Studio SDK, refer to [Introduction to VisualStudio.Extensibility for VSSDK users](./get-started/oop-extensibility-model-overview.md).

To build your mental model of how Visual Studio extensions work, see [Parts of a new Visual Studio extension](./inside-the-sdk/extension-anatomy.md).

To find out what is included in the SDK, see [Functional areas of the SDK](./inside-the-sdk/inside-the-sdk.md).

When and where should your extension appear in the IDE? Visual Studio extensions appear in the IDE when certain conditions are met. To have control over how and when your extension appears in the IDE, see [Rule-based activation constraints](./inside-the-sdk/activation-constraints.md).

Visual Studio extensions make their features available to Visual Studio through contributions. For more information, see [Contributions](./inside-the-sdk/contributions-and-configurations.md)

Learn about the [Remote UI](./inside-the-sdk/remote-ui.md) model used in the VisualStudio.Extensibility.

## Overviews
Read an overview of the areas of the SDK that you might need for your extension development projects.

* Create commands and expose them to users in the IDE, see [Commands](./command/command.md).
* Work with the contents of files and documents, see [Editor extensions](./editor/editor.md).
* Work with the in-memory representation of those documents themselves, see [Documents](./document/documents.md).
* Use the output window in an extension, see [Output window](./output-window/output-window.md).
* Work with tool windows, dockable windows within the Visual Studio IDE, see [Tool windows](./tool-window/tool-window.md).
* Use prompts with customizable buttons to interact with the user, see [User prompts](./user-prompt/user-prompts.md).
* Use dialogs with custom UI to interact with the user, see [Dialogs](./dialog/dialog.md)
* Create custom data visualizations when debugging, see [Debugger Visualizers](./debugger-visualizer/debugger-visualizers.md)
* Query or modify information about project sand solutions, see [Project Query](./project/project.md)
* Work with language servers/LSP for additional language support, see [Language Server Provider](./language-server-provider/language-server-provider.md)

## Samples and tutorials

You can find a Visual Studio solution that contains all samples at [Samples.sln](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/Samples.sln).

| Sample | Description|
|-|-|
| [Simple command handler](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/SimpleRemoteCommandSample) | Demonstrates the basics of working with commands. See also the [Create your first Visual Studio extension](./get-started/create-your-first-extension.md) tutorial. |
| [Insert guid extension](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/InsertGuid) | Shows how to insert text or code in the code editor, how to configure a command with a specific activation condition, and how to use a resource file for localization. See also the [Create your simple extension](./get-started/tutorial-create-simple-extension.md) tutorial. |
| [Command parenting](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/CommandParentingSample) | Shows how to author a command that can be parented to different aspects of the IDE. |
| [Document selector](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/DocumentSelectorSample) | Shows how to create an editor extension that is only applicable to files matching a file path pattern. |
| [Output window](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/OutputWindowSample) | Shows the most basic use of the [Output Window API](./output-window/output-window.md)|
| [Tool window](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/ToolWindowSample) | Shows how to create a tool window and populate it with content. |
| [User prompt](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/UserPromptSample) | Shows how to display a prompt to the user. |
| [Dialog](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/DialogSample) | Shows how to display a dialog with custom UI to the user. |
| [Word count margin](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/WordCountMargin) | Shows how to create an editor margin extension that displays the word count in a document. |
| [Markdown linter](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/MarkdownLinter) | Shows how multiple components can interact together inside an extension and how different areas of Visual Studio can be extended. |
| [Project Query](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/VSProjectQueryAPISample) | Shows several different kinds of project system queries you can make. |
| [Comment remover](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/CommentRemover) | Shows how to consume [Visual Studio SDK](https://www.nuget.org/packages/Microsoft.VisualStudio.SDK) services through .NET dependency injection and use VisualStudio.Extensibility APIs for commands, prompts and progress report. |
| RegexMatchDebugVisualizer | Shows how to use [Remote UI](./inside-the-sdk/remote-ui.md) to create a [Debugger Visualizer](./debugger-visualizer/debugger-visualizers.md) to visualize regular expression matches that will launch in a modal dialog window. |
| MemoryStreamDebugVisualizer | Shows how to create a [Debugger Visualizer](./debugger-visualizer/debugger-visualizers.md) to visualize MemoryStream objects that launches in a non-modal tool window. |
| [RustLanguageServiceProvider](https://github.com/microsoft/VSExtensibility/tree/main/New_Extensibility_Model/Samples/RustLanguageServerProvider) | Shows how to create a Rust language server provider extension that adds Intellisense and tooltips when a rust file is opened. |

## Experimental APIs and Breaking Changes
Starting with our 17.9 release, we're ready to label the vast majority of our APIs as stable. That is, we don't plan to make any breaking changes to these APIs. Any breaking changes that might need to be made, for example in response to user feedback about usability, will be communicated formally and with plenty of notice on our [breaking changes](https://github.com/microsoft/VSExtensibility/blob/main/docs/breaking_changes.md) page.

There are a few of our APIs that don't yet meet this bar for stability, for one of several reasons:
* The feature area is new and additional features and changes are expected in future versions.
* The API is new and we want to incorporate user feedback into the deisgn before marking it stable.
* We've received feedback that a particular API is difficult to use, so we're planning on updating it in future versions.

For these APIs, we've explicitly labeled them using the `[Experimental]` attribute to help extension authors create their extensions with confidence in the the SDK.

For more information, including how to use experimental APIs, please see our [Experimental APIs](https://github.com/microsoft/VSExtensibility/blob/main/docs/experimental_apis.md) page.

## Known Issues

We appreciate your feedback and bug reports in our [Issues Tracker](https://github.com/microsoft/VSExtensibility/issues), and we work to address any issues found in the SDK.

Please visit our [Known Issues](https://github.com/microsoft/VSExtensibility/blob/main/docs/known_issues.md) page for information about any current known issues.

## Advanced topics

| Article | Description|
|-|-|
| [Advanced Remote UI](./inside-the-sdk/advanced-remote-ui.md) | In-depth information on the remote UI model |
| [In-proc extensions](./get-started/in-proc-extensions.md) | A quick walkthrough on different options to use VisualStudio.Extensibility SDK in-proc |

## API Docs

* [Microsoft.VisualStudio.Extensibility](/dotnet/api/microsoft.visualstudio.extensibility)
* [Microsoft.VisualStudio.Extensibility.Editor](/dotnet/api/microsoft.visualstudio.extensibility.editor)
* [Microsoft.VisualStudio.ProjectSystem.Query](/dotnet/api/microsoft.visualstudio.projectsystem.query)

## Send feedback

We're actively seeking feedback and engagement. The preview phase is a great time to get community input to help us identify issues and opportunities. You can provide feedback and report bugs in our [issues tracker](https://github.com/microsoft/VSExtensibility/issues).
