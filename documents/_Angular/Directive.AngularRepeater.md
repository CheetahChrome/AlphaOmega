---
title: Directive - Repeater 
layout: default
---

# Angular Repeater Directives

In Angular, repeater directives are a set of directives that allow you to repeat a portion of a template over a collection of items. 

<p class="warning">Remember each of these commands must have a `*` in front of them</p>

The most commonly used repeater directives are:

| Directive | Description |
|-----------|-------------|
| `ngFor` | This directive is used to loop over a collection of items and create a template instance for each item in the collection. |
| `ngIf` | This directive is used to conditionally include or exclude a portion of the template based on a boolean expression. |
| `ngSwitch` | This directive is used to conditionally render a template based on the value of an expression. |
| `ngTemplateOutlet` | This directive is used to render a template that has been defined elsewhere in the application. |

By using these directives, you can create dynamic and reusable templates that can display data in a variety of ways.

### ngTemplateOutlet

Here's an example of how to use the `ngTemplateOutlet` directive in Angular:

Let's say we have a component that needs to display a list of items, and we want to allow the user to customize the appearance of each item. We can use the `ngTemplateOutlet` directive to render a custom template for each item in the list.

First, let's define our custom template in the component's template:

```html
<ng-template #itemTemplate let-item>
  <div class="item">
    {{ item.name }} - {{ item.description }}
  </div>
</ng-template>

```

Here, we've defined a template with the `ng-template` element, and given it a local variable `item` using the `let` keyword. Inside the template, we're displaying the `name` and `description` properties of the `item` object.

Next, we can use the `ngTemplateOutlet` directive to render this template for each item in the list:

```html
<div class="item-list">
  <div *ngFor="let item of items">
    <ng-container *ngTemplateOutlet="itemTemplate; context: { $implicit: item }"></ng-container>
  </div>
</div>
```

Here, we're using the `ngFor` directive to loop over the `items` array and create a `<div>` element for each item. Inside each `<div>`, we're using the `ngTemplateOutlet` directive to render the `itemTemplate` template that we defined earlier. We're also passing in the current `item` as the implicit context, which will be available inside the template as the `item` variable.

With this setup, we can easily customize the appearance of each item by modifying the `itemTemplate` template in the component's template. This can be useful for creating reusable components that allow for a high degree of customization.
