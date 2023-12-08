---
title: Directive - NGModel
layout: default
---
## Angular ngModel directive

In Angular, `ngModel` is a directive used to create a **two-way data binding** between a form control element and a property on a component class. 

By using `ngModel`, any changes made to the form control element are automatically reflected in the component property, and vice versa. This allows for easy synchronization of data between the user interface and the component class.

For example, if you have an input element for a user's name, you can use `ngModel` to bind its value to a property on the component class, like this:


For example, if you have an input element for a user's name, you can use `ngModel` to bind its value to a property on the component class, like this:

    <input type="text" [(ngModel)]="userName">

Note that in order to use `ngModel`, you need to import the `FormsModule` into your Angular module, like this:

```typescript
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';

@NgModule({
  imports: [
    FormsModule
  ],
  // ...
})
export class AppModule { }
```
---    

The `ngModel` directive can also be used with other directives, such as `ngIf` or `ngFor`, to create more complex forms. For example:

```html
<form>
  <div *ngFor="let item of items">
    <input type="text" [(ngModel)]="item.name" *ngIf="item.visible">
    <button (click)="deleteItem(item)">Delete</button>
  </div>
</form>
```

In this example, the `ngFor` directive is used to loop through an array of items and create a form input and delete button for each one. The `ngIf` directive is used to conditionally show the input element only if the visible property of the item is true. The ngModel directive is used to bind the value of the input element to the name property of the item.


## Bootstrap Property in Angular

The `bootstrap` property in Angular is part of the `@NgModule` decorator's metadata. It tells Angular which component(s) should be loaded when the application starts. 

Typically, this is the root component of your application, and it should contain the application's main view, also known as the host view. The selected component will be inserted into the `index.html` host web page inside the `app-root` selector (or whatever selector you've defined for the root component).

Here's an example:

```typescript
@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }