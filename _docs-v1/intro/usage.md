---
title: Basic Usage
description: How to get started. Learn FullCalendar's basic principles.
---

The first step in embedding a calendar on a web page is to have the right JavaScript and CSS files.
Make sure you are including the FullCalendar stylesheet, as well as the FullCalendar and
[jQuery](http://jquery.com/) JS files, in the `<head>` of your page:

```js
<link rel='stylesheet' type='text/css' href='fullcalendar.css' />
<script type='text/javascript' src='jquery.js'></script>
<script type='text/javascript' src='fullcalendar.js'></script>
```

If you plan on doing dragging or resizing, you need some additional [jQuery UI](http://jqueryui.com/download) files (more information [here](jquery-ui-dnd)).

Once you have your dependencies, you need to write the JavaScript code that initializes the calendar.
This code must be executed *after* the page has initialized. The best way to do this is with jQuery's
`$(document).ready` like so:

```js
$(function() {

  // page is now ready, initialize the calendar...

  $('#calendar').fullCalendar({
    // put your options and callbacks here
  })

});
```

The above code should be in a `<script>` tag in the head of your page. The code
relies on there being an element with an id of "calendar" in the body of your page.
The calendar will be placed *inside* this div:

```js
<div id='calendar'></div>
```

An that's it, you should see a month-based calendar that has no events on it. If you want to learn how to display events, visit the [Google Calendar](google-calendar) or [Event Data](event-data) sections.


## Options

Most of FullCalendar's documentation describes options that affect the look or behavior of the calendar. Options are usually set when the calendar is initialized, like so:

```js
$('#calendar').fullCalendar({
  weekends: false // will hide Saturdays and Sundays
});
```

## Callbacks

Callbacks are sort of like options, but they are *functions* that get *called* whenever something special happens. In the following example, an alert box will appear whenever the user clicks on a day:

```js
$('#calendar').fullCalendar({
  dayClick: function() {
    alert('a day has been clicked!');
  }
});
```

## Methods

Methods provide ways to manipulate the calendar from JavaScript code. A method operates on the jQuery object of a calendar that has already been initialized, using the familiar `fullCalendar` command, but in a completely different way:

```js
$('#calendar').fullCalendar('next');
```

This will call the [next](next) method and will force to the calendar to move to the next month/week/day.
