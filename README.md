# easyTimer
A simple jQuery plugin which provides jQuery methods to hide and show elements based on what time and date it is. It does require jQuery 1.x or 2.x.

## Basic Usage
There are two main functions available in the plugin. The HTML attributes function and the futureDate() function. These allow you to quickly show, hide, or remove elements until or after a specified date.

### Date Format
All dates must be in the YYYY-MM-DD format throughout the plugin. Also, the change happens **on** the date you enter. For example, if you enter your date to begin showing something as after="2016-01-01", it will begin showing at exactly midnight on January 1st, 2016.

## Timing HTML Attributes Function
The main feature of the plugin is it listens for data attributes which you can quickly put on to any HTML element you want to time. It will only change these elements on the specified date.

### Trigger the Timing methods
To trigger the plugin to search for the elements, call the jQuery Method.

  $(document).timeMachine();

### Hide Until
This means leave the element as display:none; from CSS until this date.

  <div data-hide-until="2016-01-01">
    <p>
      Hidden content until January 1st, 2016
    </p>
  </div>

### Remove Until
For more sensitive elements that can't be just hidden, you can also trigger a .remove(); (method which completely removes it from the DOM) on the element until a certain date.

  <div data-remove-until="2016-01-01">
    <p>
      This content will completely self destruct on page load until January 1st, 2016, which it will then show.
    </p>
  </div>

### Show Until
You could do the opposite method and specify for the element to show until a certain date too.

  <div data-show-until="2016-01-01">
    <p>
      This content will display any time before January 1st, 2016. When that date comes it will hide.
    </p>
  </div>

### Hide After
In the opposite way of the above methods you can trigger in action after the date entered. (This is truly **on** and after). This one will hide on and after a certain date.

  <div data-hide-after="2016-01-01">
    <p>
      This content will appear any time before January 1st, 2016. It will hide on and after January 1st, 2016.
    </p>
  </div>

### Remove After
This method will remove on and after a certain date.

  <div data-remove-after="2016-01-01">
    <p>
      This content will appear any time before January 1st, 2016. It will remove from DOM on and after January 1st, 2016.
    </p>
  </div>

### Show After
This method will only show content on and after a certain date.

  <div data-show-after="2016-01-01">
    <p>
      This content will be hidden any time before January 1st, 2016. It will show on and after January 1st, 2016.
    </p>
  </div>

## futureDate() Boolean Test Function
This is a boolean test you can run against the plugin. Simply will return true or false of whether a date has arrived (**true**) , or has not arrived yet (**false**)

  if (futureDate("2016-01-01")) {
    alert ("Happy New year!");
  }
