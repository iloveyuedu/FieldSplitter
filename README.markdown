
# Field Splitter plugin

With a single method call, turn a single input field, into a multi-field input. This new field has the following features:

* __Default value__: Allowing for inline labels
* __Auto blur/focus__: When the users enters maxlength characters into one of the fields, the focus is automatically changed into the next field.
* __Glue string__: Used when joining the values of partial fields
* __Gracefull degradation__: If no JS is enabled, then the original input field is used.

# How do I get the value from all those new fields?

You don't! The plugin updates the original field while keeping it hidden, that way you can include the plugin into an already created form without having to change 
the way you send the information.

# How to use it?

Installation is simple, just include the JS file just like you would with any other.
After including it, just use the method **fieldSplit** with any combination of the options listed below.

# Configuration options

There are several options that can be passed as an options hash, allowing for some customization:

* __defaultValue__: The text used on the input when there is no text entered by the user (default: XXX)
* __maxLength__:    The max length allowed for that input (default: 3)
* __numberOfFields__: Number of fields to split the original one into. (default: 3)
* __glue__: 				 String to be used to join the fields and their value (default: "-")
* __glueOriginal__: When updating the original input field, do we use the glue string or not? (default: true)


# Examples of use

Here are some basic code examples:

Using some of the configuration options:

```js
$("#test2").fieldSplit({
	glue:"/", 
	maxLength:2, 
	numberOfFields:2, 
	defaultValue:"__"
});
```


Now using some anonymous functions instead of static values as configuration options:

```js
$("#test3").fieldSplit({
	glue:"/", 
	maxLength:function(i) { return (i < 3)?2:4; }, 
	numberOfFields:3, 
	defaultValue:function(i) { return (i < 3)?"__":"____"; } //The default value changes, to show how many characters the usre can enter
});
```
 
# Contact me

If you have questions, or just want to send your love/hate, drop me an e-mail at: deleteman@gmail.com
