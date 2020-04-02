# Form Data Json - Form input values to/from JSON
A zero dependency, cross browser library to easily get form input values as a json object. Or set form input values from a json object. It can handle almost all existing input types, including multidimensional array names.

## Installation
Download [latest release](https://github.com/brainfoolong/form-data-json/releases/latest) and include `dist/form-data-json.min.js` into your project.

    <script src="dist/form-data-json.min.js"></script>

## Features
* No dependency - Vanilla javascript
* Cross Browser including IE11
* Multidimensional input name support. For example: `name="entry[123][person]"`

## Supported Browser
* Chrome
* Firefox
* Edge (Chromium based and Old)
* Safari
* IE11
* And probably every other that we don't test

## What's not supported
* `<input type="file">` It's impossible in javascript to set values for file inputs, for security reasons.

## How to contribute
* Please write an issue before you start programming.
* Always test the official supported browsers.
* Write all tests in `tests/test.html`. Each new option must have an own test.

## How to use
###### Read form input values

    FormDataJson.formToJson(document.querySelector("form"))
    
###### Read form input values including all inputs, even disabled inputs or unchecked checkboxes

    FormDataJson.formToJson(document.querySelector("form"), new FormDataJsonOptions({ includeDisabled: true }))
    
###### Set form input values

    FormDataJson.fillFormFromJsonValues(document.querySelector("form"), {'name': 'BrainFooLong'})
    
###### Set form input values and unset all other existing input values

    FormDataJson.fillFormFromJsonValues(document.querySelector("form"), {'name': 'BrainFooLong'}, new FormDataJsonOptions({ unsetAllInputsOnFill: true }))
    
###### All options

	/**
	* Include all disabled inputs in result data
	* @type {boolean}
	*/
	includeDisabled = false

	/**
	* Include checkboxes that are unchecked with a null, otherwise the key will not exist in result data
	* @type {boolean}
	*/
	includeUncheckedAsNull = false

	/**
	* Include all input buttons/submits values, otherwise the key they will not exist in result data
	* @type {boolean}
	*/
	includeButtonValues = false