---
title: Site Snippet Bug Example
slug: site-snippet-bug-example
publish: True
ordinal: 2
---

If you want to format the content of __RadRichTextBox__ at run time, you have to use the API exposed by
        __RadRichTextBox__. This is essential, as the main purpose of __RadRichTextBox__ is to allow the users to format
        their input via UI. The UI should call the respective API methods of the control.
      

>To learn more about the methods exposed by the API take a look at
{{site_name:WPF}}

[this topic](http://www.telerik.com/help/wpf/allmembers_t_telerik_windows_controls_radrichtextbox.html)

{{/site_name}}
{{site_name:Silverlight}}

[this topic](http://www.telerik.com/help/silverlight/allmembers_t_telerik_windows_controls_radrichtextbox.html)

{{/site_name}}
          .
        

## Changing the text formatting

The __RadRichTextBox__ exposes methods that change the style of the selected text or the paragraph. When a method is called, the
          respective style is applied to the selected text. If there is no selection available, the style is applied to the word in which the caret is located.
        

>RadRichTextBox provides a fully functional formatting UI out of the box. To learn more about it read the topic.
          

Here is an example of a toggle button that upon checking should make the selection or the current word bold. In the handler of the
          __Click__ event of the __RadToggleButton__, the __ToggleBold()__ method of
          __RadRichTextBox__ is called.
        ##XAML
        
