---
title: "VSTextView Object | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords:
  - "VSTextView"
helpviewer_keywords:
  - "VSTextView object, reference"
  - "views [Visual Studio SDK], reference"
ms.assetid: 78272ddc-9718-4c65-a94e-a44a2e8d54f4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
  - "vssdk"
---
# VSTextView object
The text view is a window that lets users view and edit the Unicode text of the text buffer. Essentially, the view is what most users refer to as the editor. Because the view is separated from the buffer by various text layers (word wrap, outlining text, and so on), the view is not guaranteed to be an exact representation of the text in the buffer. For more information about the text view, see [Accessing theText view by using the legacy API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md).

 The following table shows the interfaces in the <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> object.

|Interface|Description|
|---------------|-----------------|
|[IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource)|Standard OLE interface.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>|Standard OLE interface.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite>|Standard OLE interface.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Standard OLE interface.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Enables the creation of compound actions (that is, actions that are grouped in a single undo/redo unit).|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|Provides the basic methods for managing and accessing the view. `IVsTextView` is not threaded safe.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Creates and manages a window pane.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|Interacts with text layers.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsThreadSafeTextView>|Performs operations on the view from a different thread.|

## See also
- [Figures edit](https://www.microsoft.com/download/details.aspx?id=55984)
- [VSTextBuffer object](../extensibility/vstextbuffer-object.md)
- [Accessing theText view by using the legacy API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)