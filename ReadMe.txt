
SimpleTextInput
===============

Description
-----------

SimpleTextInput is a simple text-editing application for iOS that enables the layout and editing of text using Core Text. It also communicates with the text input system by implementing the the UITextInput and UIKeyInput protocols and related APIs. By communicating with the text input system, it acquires such features as autocorrection and multistage text input.

SimpleTextInput demonstrates:
* Creation of objects representing positions and ranges in the text
* Insertion and deletion of text
* Management of selected and marked text ranges
* Computation of rectangles for selections and the "cursor"
and other important requirements for implementing the text-input protocols.

Please see "Communicating with the Text Input System" in Text and Web Programming Guide for iOS for an overview of UITextInput and related programming interfaces and a close examination of the SimpleTextInput code:

http://developer.apple.com/iphone/library/documentation/StringsTextFonts/Conceptual/TextAndWebiPhoneOS/CustomTextProcessing/CustomTextProcessing.html#//apple_ref/doc/uid/TP40009542-CH4-SW4

Important: 
This sample code should not be considered a template for a text editor, but rather as an example of how to bind the text input system to a pre-existing text editor. The project's use of CoreText is naive and inefficient; it deals only with left-to-right text layout, and it is by no means a good template for any text editor. It is a implementation meant only to illustrate how to bind the system keyboard (that is, the text input system) to some pre-existing text editor.


Classes in the Project
----------------------

The project implements the following classes (header and implementation files take the name of the class):

APLSimpleCoreTextView
A view that draws text, makes layout decisions, and manages a selection over its text range. It represents a pre-existing text editor.
 
APLEditableCoreTextView:
A view that adopts the UIKeyInput protocol to enable text entry and deletion. It also adopts the UITextInput protocol (and implements related protocols and classes) to communicate with the text input system (i.e., system keyboard). APLEditableCoreTextView embeds an APLSimpleCoreTextView as an instance variable, instantiates it, and calls through to it in most UITextInput and UIKeyInput method implementations. It serves as the "glue" between the system keyboard and a CoreText-based editor.

APLSimpleTextInputViewController
UIViewController subclass that manages the primary view for the application.

SimpleTextInputAppDelegate 
The application delegate, adds the main view to the window and displays the window.

------------------------------

Copyright (C) 2010-13 Apple Inc. All rights reserved.
