---
title: Angular Interpolation
layout: default
---
# Angular Interpolation


Interpolation binding is used to display dynamic data in an Angular template by wrapping the expression in double curly braces. Here's an example:

`<h1>Welcome {{username}}!</h1>`

In this example, `{{username}}` is an expression that will be evaluated by Angular and replaced with the value of the `username` property in the component. If the value of `username` is "John", for example, the template will be rendered as:

`<h1>Welcome John!</h1>`

Interpolation can also be used to display the results of method calls:

The current date and time is 

`{ { getCurrentDateTime() } }`

Here, `{ { getCurrentDateTime() } }` will be replaced with the result of the `getCurrentDateTime()` method defined in the component.
