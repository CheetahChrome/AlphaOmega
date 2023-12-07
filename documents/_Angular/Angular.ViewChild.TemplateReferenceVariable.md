---
layout: post
title: "Binding ViewChild Template Reference Variable"
date: 12-07-2023
categories: [Angular, ViewChild, Template Reference Variable]
---

## Template Reference Variables in Angular

In Angular, a Template Reference Variable (TRV) is a type of object known as a "ViewChild." ViewChild is a decorator that allows you to access a reference to an element or directive in the view template and interact with it in your component code. The TRV is a way of capturing a reference to a specific element, directive, or component instance within a template. This can be useful when you want to use the properties or methods of a specific element or component within your template.

Template Reference Variables are declared using the hash (`#`) symbol followed by the variable name. Once declared, they can be used elsewhere in the template.

Here's an example:

```html
<input #myInput type="text">
<button (click)="myInput.focus()">Focus the input</button>
```
In this example, `#myInput` is a Template Reference Variable. It captures a reference to the input element. Then, in the button's click event, we use myInput.focus() to set focus to the input element.

```html
<div class="input-group my-4">
  <input type="text" class="form-control" placeholder="Find Players by Name" #filter (keyup)="update(filter.value)">
  <button class="btn btn-light" type="button" (click)="update(''); filter.value = ''">Clear</button>
</div>
```

| Element | Description |
| --- | --- |
| `<div class="input-group my-4">` | A div element with a CSS class of "input-group my-4" for styling purposes. |
| `<input type="text" class="form-control" placeholder="Find Players by Name" #filter (keyup)="update(filter.value)">` | An input field of type text with a CSS class of "form-control". The placeholder text inside the input field is "Find Players by Name".<br/>The `#filter` is a template reference variable that refers to this input element. <br/>The `(keyup)="update(filter.value)"` is an event binding that calls the `update` method whenever a keyup event occurs (i.e., when the user releases a key while the input field is focused).<br/>The `filter.value` is passed as an argument to the `update` method. |
| `<button class="btn btn-light" type="button" (click)="update(''); filter.value = ''">Clear</button>` | A button with a CSS class of "btn btn-light". The button's type is "button", and its label is "Clear". The `(click)="update(''); filter.value = ''"` is an event binding that calls the `update` method with an empty string as an argument and clears the input field when the button is clicked. |
