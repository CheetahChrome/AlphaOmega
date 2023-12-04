---
title: ZNotes 
layout: default
---
# RxJS vs NgRx

## Angular Component Files

When you generate a new Angular component using the Angular CLI command `ng generate component ComponentName` or `ng g c ComponentName`, the following files are created:

- `component-name.component.ts`: This is the main file for the component. It contains the component class and metadata.

- `component-name.component.html`: This is the template file for the component. It contains the HTML that Angular will render.

- `component-name.component.css`: This is the stylesheet for the component. It contains the CSS that will be applied to the template.

- `component-name.component.spec.ts`: This is the testing file for the component. It contains unit tests for the component.

For example, if you generate a component named `example`, you'll get these files:

- `example.component.ts`
- `example.component.html`
- `example.component.css`
- `example.component.spec.ts`


## Template Reference Variables in Angular

In Angular, a Template Reference Variable is a way of capturing a reference to a specific element, directive, or component instance within a template. This can be useful when you want to use the properties or methods of a specific element or component within your template.

Template Reference Variables are declared using the hash (`#`) symbol followed by the variable name. Once declared, they can be used elsewhere in the template.

Here's an example:

```html
<input #myInput type="text">
<button (click)="myInput.focus()">Focus the input</button>
```
In this example, `#myInput` is a Template Reference Variable. It captures a reference to the input element. Then, in the button's click event, we use myInput.focus() to set focus to the input element.

