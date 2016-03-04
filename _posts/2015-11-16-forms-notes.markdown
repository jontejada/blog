---
layout: post
title: "Notes on HTML forms"
date: 2015-11-15 11:10:00 -800
categories: galvanize notes
---
## the `<form>` element
* `method=` attribute sets the HTTP submit method
	* `'post'` form data sent to server
	* `'get'` form data appended to action URI with `?` and sent to server
* `action=` attr is URI of processing program
	* `'demo_form.asp'`
	* `''` stays on same page
	* can be overridden by `formaction` attr on `<button>` or `<input>`
* `id=` attr should be used over `name=`

##the `<input>` element
* no end tag `</input>`
* set by `type=` attr
	* `'text'` default is a single line text box 
	* `'checkbox'`
		* must use `value='something'` to include in submit
		* `checked` boolean attr will set it as checked to start
	* `color` color button with color picker UI
		* PARTIAL SUPPORT
	* `date` calendar UI with year, month, day (without time)
	* `datetime` & `datetime-local` date + hr, min, sec, fraction of a sec
		* PARTIAL SUPPORT
	* `email` validates on submit for empty string or single email
		* `:valid` & `:invalid` CSS pseudo-classes applied
	* `file` Choose File button with file browser UI
		* set file types allowed with `accept` attr
	* `month` calendar UI with year, month
	* `number` accepts floating point number
		* up down toggle UI
		* `min='4'` & `max='8'` set range
		* `step='2'` sets allowed intervals
		* `.stepDown()` & `.stepUp()` JS methods
	* `password`
	* `radio` pick one from multiple with shared `name='radiogroup'` 
		* must use `value='something'` to include in submit
		* `checked` boolean attr
	* `range` slider UI for inexact number input
		* invisible defaults:
			* `min='0'`
			* `max='100'`
			* `value=` min + (max - min) / 2
			* `step='1`
		* `reset` button that resets
		* `tel`
		* `time`
		* `url`
		* `week`
		* `search`
	* lots more
* clicking the `<label for='an_input_id'>` element will give focus to the corresponding input
	* the label element can contain the input it labels (don't need `for` attr for this)

##other form input elements
* `<select name='a_name'>` offers menu of options
	* has `<option>OPT 1</option>` children
		* `value='option1'` attr is optional. Without this, default is element contents, e.g. `OPT 1` above
		* `selected` boolean attr to give initial selection
		* `<optgroup label='group 1'>` is optional parent to grouped options
	* `multiple` boolean attr allows selection of multiple options
	* `size='4'` attr sets number of displayed rows
* `<textarea>` multi-line text input
	* `cols='30'` attr sets visible width in average character widths, 20 default
	* `rows='4'` sets height, 2 default

##other input attributes
* give a `name='a_name'` to be submitted with form data
* `value='something'` depends on `type=` attr
	* required for `checkbox`, `radio` and `image`, gives value sent on submit
	* sets initial value for `text`, `password` and `hidden` types
	* sets button text for `button`, `reset` and `submit` types
* `form='a_form_id'` allows element to be anywhere in the document
* `placeholder='some text'` shown when field is empty, not focused
*  `autofocus` boolean attr grabs focus on page load
*  `required` boolean attr
*  `pattern="[0-9][A-Z]{3}"` attr takes a JS regexp to be checked
	* [pattern examples](http://html5pattern.com/Names)
* `list='a_datalist_id'` associates a `<datalist>` of `<options>` with possible `value`s
	* (breaks easily?)


##[submitting](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms/Sending_and_retrieving_form_data)
* `<button>` element
	* default `type='submit'` attr submits form data to server
		* can override form submit method with `formmethod='get|put'` 
		* can override form action url with `formaction='url'`
	* `type='reset'` resets all controls to initial values
	* `type='button'` has no default behavior
		* can use scripts to set behavior
* `<input type='button'>` has no default behavior
* `<input type='image' src=''>` for a graphical submit button

##links
[MDN input guide](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Input)

[my first form](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms/My_first_HTML_form)

[diveintohtml5](http://diveintohtml5.info/forms.html)

[html5doctor](http://html5doctor.com/html5-forms-introduction-and-new-attributes/)

##future work
more on submission
