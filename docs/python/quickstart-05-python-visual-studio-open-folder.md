---
title: Quickstart - Open a Python code folder
description: In this quickstart, you open and run Python code from a folder without using a Visual Studio project (Visual Studio 2019 only).
ms.date: 09/01/2023
ms.topic: quickstart
author: cwebster-99
ms.author: cowebster
manager: jmartens
ms.subservice: python
monikerRange: ">= vs-2019"
---

# Quickstart: Open and run Python code in a folder

::: moniker range="vs-2019"
Once you've [installed Python support in Visual Studio 2019](installing-python-support-in-visual-studio.md), it's easy to run existing Python code in Visual Studio 2019 without creating a Visual Studio project.
::: moniker-end

::: moniker range=">=vs-2022"
Once you've [installed Python support in Visual Studio 2022](installing-python-support-in-visual-studio.md), it's easy to run existing Python code in Visual Studio 2022 without creating a Visual Studio project.

> [!Note]
> Visual Studio 2017 and earlier require you to create a Visual Studio project to run Python code, which you can easily do using a built-in project template. See [Quickstart: Create a Python project from existing code](quickstart-01-python-in-visual-studio-project-from-existing-code.md).

::: moniker-end

::: moniker range="vs-2019"

1. For this walkthrough, you can use any folder with Python code that you like. To follow along with the example shown here, clone the gregmalcolm/python_koans GitHub repository to your computer using the command `git clone https://github.com/gregmalcolm/python_koans` in an appropriate folder.

1. Launch Visual Studio 2019 and in the start window, select **Open** at the bottom of the **Get started** column. Alternately, if you already have Visual Studio running, select the **File** > **Open** > **Folder** command instead.

   :::image type="content" source="media/quickstart-open-folder/01-open-local-folder.png" alt-text="Screenshot of the Visual Studio startup screen.":::

1. Navigate to the folder containing your Python code, then choose **Select Folder**. If you're using the python_koans code, make sure to select the `python3` folder within the clone folder.

   :::image type="content" source="media/quickstart-open-folder/02-select-folder.png" alt-text="Screenshot of the Select Folder dialog from the Open Folder command.":::

1. Visual Studio displays the folder in **Solution Explorer** in what's called **Folder View**. You can expand and collapse folders using the arrows on the left edges of the folder names:

   :::image type="content" source="media/quickstart-open-folder/03-expand-collapse-folders.png" alt-text="Screenshot of the controls to expand and collapse folders in Solution Explorer.":::

1. When opening a Python folder, Visual Studio creates several hidden folders to manage settings related to the project. To see these folders (and any other hidden files and folders, such as the `.git` folder), select the **Show All Files** toolbar button:

   :::image type="content" source="media/quickstart-open-folder/05-view-hidden-folders.png" alt-text="Screenshot of a view of hidden folders in Solution Explorer.":::

1. To run the code, you first need to identify the startup or primary program file. In the example shown here, select the startup file _contemplate-koans.py_, right-click that file and select **Set as Startup Item**.

   :::image type="content" source="media/quickstart-open-folder/06-set-as-startup-item-command.png" alt-text="Screenshot of the setting a startup item in Solution Explorer.":::

   > [!Important]
   > If your startup item is not located in the root of the folder you opened, you must also add a line to the launch configuration JSON file as described in the section, [Set a working directory](#set-a-working-directory).

1. Run the code by pressing **Ctrl**+**F5** or selecting **Debug** > **Start without Debugging**. You can also select the toolbar button that shows the startup item with a play button, which runs code in the Visual Studio debugger. In all cases, Visual Studio detects that your startup item is a Python file, so it automatically runs the code in the default Python environment. (That environment is shown to the right of the startup item on the toolbar.)

   :::image type="content" source="media/quickstart-open-folder/07-start-debug-toolbar.png" alt-text="Screenshot of the start debugger toolbar button.":::

1. The program's output appears in a separate command window:

   :::image type="content" source="media/quickstart-open-folder/08-result-window.png" alt-text="Screenshot of the output window for running Python code.":::

1. To run the code in a different environment, select that environment from the drop-down control on the toolbar, then launch the startup item again.

1. To close the folder in Visual Studio, select the **File** > **Close folder** menu command.

::: moniker-end

::: moniker range=">=vs-2022"

1. For this walkthrough, you can use any folder with Python code that you like. To follow along with the example shown here, clone the gregmalcolm/python_koans GitHub repository to your computer using the command `git clone https://github.com/gregmalcolm/python_koans` in an appropriate folder.

1. Launch Visual Studio 2022 and in the start window, select **Open** at the bottom of the **Get started** column. Alternately, if you already have Visual Studio running, select the **File** > **Open** > **Folder** command instead.

   :::image type="content" source="media/quickstart-open-folder/vs-2022/01-open-local-folder.png" alt-text="Screenshot of the Visual Studio startup screen.":::

1. Navigate to the folder containing your Python code, then choose **Select Folder**.

   :::image type="content" source="media/quickstart-open-folder/vs-2022/02-select-folder.png" alt-text="Screenshot of the Select Folder dialog from the Open Folder command.":::

1. Visual Studio displays the folder in **Solution Explorer** in what's called **Folder View**. You can expand and collapse folders using the arrows on the left edges of the folder names:

   :::image type="content" source="media/quickstart-open-folder/vs-2022/03-expand-collapse-folders.png" alt-text="Screenshot of the controls to expand and collapse folders in Solution Explorer.":::

1. When opening a Python folder, Visual Studio creates several hidden folders to manage settings related to the project. To see these folders (and any other hidden files and folders, such as the `.git` folder), select the **Show All Files** toolbar button:

   :::image type="content" source="media/quickstart-open-folder/vs-2022/05-view-hidden-folders.png" alt-text="Screenshot of a view of hidden folders in Solution Explorer.":::

1. To run the code, you first need to identify the startup or primary program file. In the example shown here, the startup file _contemplate-koans.py_. Right-click that file and select **Set as Startup Item**.

   :::image type="content" source="media/quickstart-open-folder/vs-2022/06-set-as-startup-item-command.png" alt-text="Screenshot of setting a startup item in Solution Explorer.":::

   > [!Important]
   > If your startup item is not located in the root of the folder you opened, you must also add a line to the launch configuration JSON file as described in the section, [Set a working directory](#set-a-working-directory).

1. Run the code by pressing **Ctrl**+**F5** or selecting **Debug** > **Start without Debugging**. You can also select the toolbar button that shows the startup item with a play button, which runs code in the Visual Studio debugger. In all cases, Visual Studio detects that your startup item is a Python file, so it automatically runs the code in the default Python environment. (That environment is shown to the right of the startup item on the toolbar.)

   :::image type="content" source="media/quickstart-open-folder/vs-2022/07-start-debug-toolbar.png" alt-text="Screenshot of the start debugger toolbar button.":::

1. The program's output appears in a separate command window:

   :::image type="content" source="media/quickstart-open-folder/vs-2022/08-result-window.png" alt-text="Screenshot of the output window for running Python code.":::

1. To run the code in a different environment, select that environment from the drop-down control on the toolbar, then launch the startup item again.

1. To close the folder in Visual Studio, select the **File** > **Close folder** menu command.

::: moniker-end

## Set a working directory

::: moniker range="vs-2019"
By default, Visual Studio runs a Python project opened as a folder in the root of that same folder. The code in your project, however, might assume that Python is being run in a subfolder. For example, now suppose you open the root folder of the python*koans repository and there is a subfolder called python3 where \_contemplate-koans.py* exists. You set the _python3/contemplate-koans.py_ file as startup item. If you then run the code, you would see an error that the _koans.txt_ file can't be found. This error happens because _contemplate-koans.py_ assumes that Python is being run in the _python3_ folder rather than the repository root.

In such cases, you must also add a line to the launch configuration JSON file to specify the working directory:

1. Right-click the Python (_.py_) startup file in **Solution Explorer** and select **Debug and Launch Settings**.

   :::image type="content" source="media/quickstart-open-folder/09-debug-launch-settings-menu-command.png" alt-text="Screenshot of the Solution Explorer Folder view with the contemplate-koans.py file selected, and Debug and Launch Settings selected on the context menu.":::

1. In the **Select debugger** dialog box that appears, select **Default** and then choose **Select**.

   :::image type="content" source="media/quickstart-open-folder/10-select-debugger.png" alt-text="Screenshot of the Select a Debugger dialog with the Default debugger selected and the Select button chosen.":::

   > [!Note]
   > If you don't see **Default** as a choice, be sure that you chose a Python _.py_ file when selecting the **Debug and Launch Settings** command. Visual Studio uses the file type to determine which debugger options to display.

1. Visual Studio opens a file named _launch.vs.json_, which is located in the hidden `.vs` folder. This file describes the debugging context for the project. To specify a working directory, add a value for `"workingDirectory"`, as in `"workingDirectory": "python3"` for python-koans example:

   ```json
   {
     "version": "0.2.1",
     "defaults": {},
     "configurations": [
       {
         "type": "python",
         "interpreter": "(default)",
         "interpreterArguments": "",
         "scriptArguments": "",
         "env": {},
         "nativeDebug": false,
         "webBrowserUrl": "",
         "project": "contemplate_koans.py",
         "projectTarget": "",
         "name": "contemplate_koans.py",
         "workingDirectory": "python3"
       }
     ]
   }
   ```

1. Save the file and launch the program again, which now runs in the specified folder.
   ::: moniker-end

::: moniker range=">=vs-2022"

By default, Visual Studio runs a Python project opened as a folder in the root of that same folder. The code in your project, however, might assume that Python is being run in a subfolder. For example, now suppose you open the root folder of the python*koans repository and there is a subfolder called python3 where \_contemplate-koans.py* exists. You set the _python3/contemplate-koans.py_ file as startup item. If you then run the code, you would see an error that the _koans.txt_ file can't be found. This error happens because _contemplate-koans.py_ assumes that Python is being run in the _python3_ folder rather than the repository root.

In such cases, you must also add a line to the launch configuration JSON file to specify the working directory:

1. Right-click the Python (_.py_) startup file in **Solution Explorer** and select **Add Debug Configuration**.

   :::image type="content" source="media/quickstart-open-folder/vs-2022/09-debug-launch-settings-menu-command.png" alt-text="Screenshot of the Solution Explorer Folder View with the contemplate-koans.py file selected, and Add Debug Configuration selected on the context menu.":::

1. In the **Select debugger** dialog box that appears, select **Default** and then choose **Select**.

   :::image type="content" source="media/quickstart-open-folder/vs-2022/10-select-debugger.png" alt-text="Screenshot of the Select a Debugger dialog with the Default debugger selected and the Select button chosen.":::

   > [!Note]
   > If you don't see **Default** as a choice, be sure that you chose a Python _.py_ file when selecting the **Add Debug Configuration** command. Visual Studio uses the file type to determine which debugger options to display.

1. Visual Studio opens a file named _launch.vs.json_, which is located in the hidden `.vs` folder. This file describes the debugging context for the project. To specify a working directory, add a value for `"workingDirectory"`, as in `"workingDirectory": "python3"` for python-koans example:

   ```json
   {
     "version": "0.2.1",
     "defaults": {},
     "configurations": [
       {
         "type": "python",
         "interpreter": "(default)",
         "interpreterArguments": "",
         "scriptArguments": "",
         "env": {},
         "nativeDebug": false,
         "webBrowserUrl": "",
         "project": "contemplate_koans.py",
         "projectTarget": "",
         "name": "contemplate_koans.py",
         "workingDirectory": "python3"
       }
     ]
   }
   ```

1. Save the file and launch the program again, which now runs in the specified folder.

::: moniker-end

## Next steps

> [!div class="nextstepaction"]
> [Tutorial: Work with Python in Visual Studio](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## See also

- [Quickstart: Create a Python project from existing code](quickstart-01-python-in-visual-studio-project-from-existing-code.md)
- [Quickstart: Create a Python project from a repository](quickstart-03-python-in-visual-studio-project-from-repository.md)
- [Manually identify an existing Python interpreter](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment)
