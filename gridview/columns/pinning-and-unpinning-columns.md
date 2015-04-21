---
title: Pinning and Unpinning Columns
page_title: Pinning and Unpinning Columns
description: Pinning and Unpinning Columns
slug: gridview-columns-pinning-and-unpinning-columns
tags: pinning,and,unpinning,columns
published: True
position: 5
---

# Pinning and Unpinning Columns



## Pinning single column

Columns in RadGridView can be pinned which will result in the pinned columns being anchored to the left or right side of the grid.
    		To pin a particular column, set its __IsPinned__ property of the __Columns collection item__ to
      		*True*. This will pin the column to the left size of RadGridView. In order to change the position where the 
    		column should be pinned you have to use the __PinPosition__ property of the particular column and choose a value
    		from the provided enumeration. The code block below shows pinning the third column (called “FirstName) in the RadGridView:
      	

#### __[C#] Pinning a single columns__

{{source=..\SamplesCS\GridView\Columns\PinningAndUnpinningColumns.cs region=pinningColumns}}
	            radGridView1.Columns[2].IsPinned = true;
	            radGridView1.Columns["FirstName"].IsPinned = true;
	{{endregion}}



#### __[VB.NET] Pinning a single columns__

{{source=..\SamplesVB\GridView\Columns\PinningAndUnpinningColumns.vb region=pinningColumns}}
	        Me.RadGridView1.Columns(2).IsPinned = True
	        'or you can use
	        Me.RadGridView1.Columns("FirstName").IsPinned = True
	{{endregion}}



In order to pin the column to the right side of RadGridView consider the following code snippet:
      	![gridview-columns-pinning-and-unpinning-columns 001](images/gridview-columns-pinning-and-unpinning-columns001.png)

## Pinning multiple columns 

Multiple column pinning is also possible. Simply set either the __IsPinned__ property or the
	  		__PinPosition__ property for all columns that you want to pin:
	  	

#### __[C#] Pinning multiple columns__

{{source=..\SamplesCS\GridView\Columns\PinningAndUnpinningColumns.cs region=pinMultipleColumns}}
	            radGridView1.Columns["Photo"].PinPosition = Telerik.WinControls.UI.PinnedColumnPosition.Left;
	            radGridView1.Columns["FirstName"].PinPosition = Telerik.WinControls.UI.PinnedColumnPosition.Left;
	            radGridView1.Columns["LastName"].PinPosition = Telerik.WinControls.UI.PinnedColumnPosition.Left;
	{{endregion}}



#### __[VB.NET] Pinning multiple columns__

{{source=..\SamplesVB\GridView\Columns\PinningAndUnpinningColumns.vb region=pinMultipleColumns}}
	        Me.RadGridView1.Columns("Photo").PinPosition = Telerik.WinControls.UI.PinnedColumnPosition.Left
	        Me.RadGridView1.Columns("FirstName").PinPosition = Telerik.WinControls.UI.PinnedColumnPosition.Left
	        Me.RadGridView1.Columns("LastName").PinPosition = Telerik.WinControls.UI.PinnedColumnPosition.Left
	{{endregion}}

![gridview-columns-pinning-and-unpinning-columns 002](images/gridview-columns-pinning-and-unpinning-columns002.png)

>All pinned columns appear in the selected pinned section ordered by their original column index in the Columns collection.
				After pinning multiple columns you can drag each of them to the desired position in the pin section.
		  ![gridview-columns-pinning-and-unpinning-columns 003](images/gridview-columns-pinning-and-unpinning-columns003.png)![gridview-columns-pinning-and-unpinning-columns 004](images/gridview-columns-pinning-and-unpinning-columns004.png)