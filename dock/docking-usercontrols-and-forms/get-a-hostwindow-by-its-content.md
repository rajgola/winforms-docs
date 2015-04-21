---
title: Get a HostWindow by its Content
page_title: Get a HostWindow by its Content
description: Get a HostWindow by its Content
slug: dock-docking-usercontrols-and-forms-get-a-hostwindow-by-its-content
tags: get,a,hostwindow,by,its,content
published: True
position: 2
---

# Get a HostWindow by its Content



In certain cases, you may need to perform specific operations depending on the currently activated HostWindow in regards to the form/user control that it contains.



In order to do this, you should first subscribe to the ActiveWindowChanged event and then execute the following code snippet in the ActiveWindowChanged event handler:

#### __[C#]__

{{source=..\SamplesCS\Dock\DockingForms.cs region=handlingActiveWindowChanged}}
	        void radDock1_ActiveWindowChanged(object sender, Telerik.WinControls.UI.Docking.DockWindowEventArgs e)
	        {
	            HostWindow hostWin = e.DockWindow as HostWindow;
	            if (hostWin != null)
	            {
	                if (hostWin.Content is VegetablesForm)
	                {
	                    // custom implementation here
	                }
	            }
	        }
	{{endregion}}



#### __[VB.NET]__

{{source=..\SamplesVB\Dock\DockingForms.vb region=handlingActiveWindowChanged}}
	    Private Sub radDock1_ActiveWindowChanged(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.Docking.DockWindowEventArgs)
	        Dim hostWin As HostWindow = TryCast(e.DockWindow, HostWindow)
	        If Not hostWin Is Nothing Then
	            If TypeOf hostWin.Content Is VegetablesForm Then
	                ' custom implementation here
	            End If
	        End If
	    End Sub
	{{endregion}}







## Getting a HostWindow by its content

In order to get a HostWindow that hosts a particular form/user control instance, you should call the GetHostWindows method passing the contained control as a parameter. Supposing that vegetablesForm is an instance of type VegetablesForm, we can use the following code snippet:

#### __[C#]__

{{source=..\SamplesCS\Dock\DockingForms.cs region=gettingWindow}}
	            HostWindow vegetablesWindow = this.radDock1.GetHostWindow(vegetablesForm);
	{{endregion}}



#### __[VB.NET]__

{{source=..\SamplesVB\Dock\DockingForms.vb region=gettingWindow}}
	        Dim vegetablesWindow As HostWindow = Me.RadDock1.GetHostWindow(VegetablesForm)
	{{endregion}}



