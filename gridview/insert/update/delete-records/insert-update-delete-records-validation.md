---
title: Validation
page_title: Validation
description: Validation
slug: gridview-insert-update-delete-records-validation
tags: validation
published: True
position: 4
---

# Validation



## 
<table><tr><td>

RELATED VIDEOS</td></tr><tr><td>

[Validation with RadGridView for WinForms](http://tv.telerik.com/winforms/radgridview/validation-with-radgridview-winforms)
              In this video you will learn how to use the event-based Validation functionality in RadGridView for WinForms. Learn how to use the CellValidating and RowValidating events to ensure user input is valid. (Runtime: 08:47)</td></tr></table>

To prevent invalid input, wire the __ValueChanging__ and
__ValueChanged__ events of the grid to add custom
validation logic. Below is a simple example that demonstrates how to reject
symbols greater than 10 characters long:

#### __[C#] Handling the value changed event__

{{source=..\SamplesCS\GridView\InsertUpdateDeleteRecords\InsertUpdateDeleteRecords.cs region=handlingValueChangingEvent}}
	        void radGridView1_ValueChanging(object sender, Telerik.WinControls.UI.ValueChangingEventArgs e)
	        {
	            if (e.NewValue.GetType() == typeof(string))
	            {
	                if (e.NewValue.ToString().Length > 10)
	                {
	                    {
	                        e.Cancel = true;
	                    }
	                }
	            }
	        }
	{{endregion}}



#### __[VB.NET] Handling the value changed event__

{{source=..\SamplesVB\GridView\InsertUpdateDeleteRecords\InsertUpdateDeleteRecords.vb region=handlingValueChangingEvent}}
	    Private Sub RadGridView1_ValueChanging(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.ValueChangingEventArgs) Handles RadGridView1.ValueChanging
	        If e.NewValue.GetType() Is GetType(String) Then
	            If e.NewValue.ToString().Length > 10 Then
	                If True Then
	                    e.Cancel = True
	                End If
	            End If
	        End If
	    End Sub
	{{endregion}}

