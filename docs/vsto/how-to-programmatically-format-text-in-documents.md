---
title: "Programmatically format text in documents"
description: Learn how you can use the Range object to programmatically format text in a Microsoft Word document.
ms.date: "02/02/2017"
ms.topic: "how-to"
dev_langs:
  - "VB"
  - "CSharp"
helpviewer_keywords:
  - "formatting [Office development in Visual Studio]"
  - "documents [Office development in Visual Studio], formatting text"
  - "text [Office development in Visual Studio], formatting in documents"
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.subservice: office-development
---
# Programmatically format text in documents

  You can use the <xref:Microsoft.Office.Interop.Word.Range> object to format text in a Microsoft Office Word document.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 The following example selects the first paragraph in the document and changes the font size, the font name, and the alignment. It then selects the range and displays a message box to pause before executing the next section of code. The next section calls the Undo method of the <xref:Microsoft.Office.Tools.Word.Document> host item (for a document-level customization) or the <xref:Microsoft.Office.Interop.Word.Document> class (for a VSTO Add-in) three times. It applies the Normal Indent style and displays a message box to pause the code. Then the code calls the <xref:Microsoft.Office.Tools.Word.Document.Undo%2A> method once, and displays a message box.

## Document-level customization example

### To format text using a document-level customization

1. The following example can be used in a document-level customization. To use this code, run it from the `ThisDocument` class in your project.

     ### [C#](#tab/csharp)
     :::code language="csharp" source="../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs" id="Snippet62":::

     ### [VB](#tab/vb)
     :::code language="vb" source="../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb" id="Snippet62":::
     ---

## VSTO Add-in Example

### To format text using a VSTO Add-in

1. The following example can be used in a VSTO Add-in. This example uses the active document. To use this code, run it from the `ThisAddIn` class in your project.

     ### [C#](#tab/csharp)
     :::code language="csharp" source="../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs" id="Snippet62":::

     ### [VB](#tab/vb)
     :::code language="vb" source="../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb" id="Snippet62":::
     ---

## Related content
- [How to: Programmatically define and select ranges in documents](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [How to: Programmatically insert text into Word documents](../vsto/how-to-programmatically-insert-text-into-word-documents.md)
- [How to: Programmatically search for and replace text in documents](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)
