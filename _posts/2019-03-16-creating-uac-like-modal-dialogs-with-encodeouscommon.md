---
layout: post
title: Creating UAC-like modal dialogs with EncodeousCommon
subtitle: Using windows' desktop api to create modal dialogs
published: true
---
## Creating UAC-like modal dialogs with EncodeousCommon
Before starting:
- Download the latest Builds of [EncodeousCommon.Miscellaneous.ModalDialog and EncodeousCommon.Demo.ModalDialog](https://ci.appveyor.com/project/Encodeous/encodeouscommon/build/artifacts).

### What is a Modal dialog?
A modal dialog is a dialog that requires the user to interact with it. In this case, the modal dialog also prevents other windows from covering it!

### When can Modal dialogs be used?
When making big and irriversable changes, you want that user to be fully aware of the actions. Modal dialogs will help grab the user's attention.



## Creating Modal Dialogs

In this tutorial, we will be creating cool modal dialogs like this:

![](https://i.imgur.com/TSC0YFR.png)



First create a simple window and button that will launch the dialog (this step is optional)

![](https://i.imgur.com/Cf2zUF5.png)

Then double click on the button to create a event handler.

Now type in this code:
~~~csharp
int backgroundBrightness = -50;
DialogForm modalDialogForm = new DialogForm();
DialogCreator modalDialogCreator = new DialogCreator("DesktopName",modalDialogForm, backgroundBrightness);
modalDialogCreator.CreateDialog();
~~~

`DialogCreator` is the class we will be referencing.

The `DialogCreator` constructor has a few parameters

`DesktopName` is the name of the desktop the modal dialog will be created in

`DialogForm` is the form that we will be showing.

`backgroundBrightness` is how dark the background should be.


![](https://i.imgur.com/atYa9Bc.png)


Lets quickly create the actual dialog form:

![](https://i.imgur.com/wjNccVS.png)

Add a close button and insert the event handler.

In our close method, we will run Close();

{: .box-note}
Note: Close(); is a built-in function in winforms

![](https://i.imgur.com/RnXVxUH.png)


{: .box-warning} 
Warning: On the form, DO NOT run any code that can terminate the currently running process! doing so will cause the user to be stuck in an empty void (desktop)

### The program should be ready to go! Give it a try or download the demo program!
