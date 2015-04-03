---
title: OnColumnHeaderClick
page_title: OnColumnHeaderClick | UI for ASP.NET AJAX Documentation
description: OnColumnHeaderClick
slug: calendar/client-side-programming/events/oncolumnheaderclick
tags: oncolumnheaderclick
published: True
position: 9
---

# OnColumnHeaderClick



## 

The __OnColumnHeaderClick__ client-side event handler is called when the user is about to select a column of dates by clicking on a column header. The event occurs only if the __ShowColumnHeaders__ and __UseColumnHeadersAsSelectors__ properties are set to __true__.

>note The __OnColumnHeaderClick__ event is supported by: __RadCalendar__ .
>


The event handler receives two arguments:

1. the [RadCalendar object]({%slug calendar/client-side-programming/radcalendar-object%}) that fired the event.

1. an event arguments object that exposes the following methods:OnColumnHeaderClick event arguments object


| Name | Return Type | Arguments | Description |
| ------ | ------ | ------ | ------ |
| __get_index()__ |int||Returns the 1-based index of the column that was clicked.|
| __get_domElement()__ |HTML element||Returns the DOM element for the column header that was clicked.|
| __set_cancel(value)__ ||bool|Lets you prevent the click from selecting the column of dates.|

The following example uses the __OnColumnHeaderClick__ event to confirm the selection:

````ASPNET
	<script type="text/javascript">
	    function ConfirmColumnSelection(sender, eventArgs) {
	        var msg = "Do you want to change the selection for column " + eventArgs.get_index();
	        var title = eventArgs.get_domElement().title;
	        if (title != "")
	            msg = msg + " (" + title + ")";
	        msg = msg + "?";
	        eventArgs.set_cancel(!confirm(msg));
	    }
	</script>
	<telerik:RadCalendar ID="RadCalendar1" runat="server">
	 <ClientEvents OnColumnHeaderClick="ConfirmColumnSelection" />
	</telerik:RadCalendar>
````



# See Also

 * [OnRowHeaderClick]({%slug calendar/client-side-programming/events/onrowheaderclick%})

 * [OnViewSelectorClick]({%slug calendar/client-side-programming/events/onviewselectorclick%})

 * [OnDateClick]({%slug calendar/client-side-programming/events/ondateclick%})