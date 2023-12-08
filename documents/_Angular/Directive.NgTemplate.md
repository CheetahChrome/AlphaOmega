---
layout: default
title: Directive - NGTemplate
---

The Angular directive `ng-template` is used for defining templates within Angular templates. It serves as a placeholder for content that can be **rendered conditionally** or repeatedly based on application logic. `ng-template` allows you to encapsulate a block of HTML or other Angular elements and then reference and render it dynamically using various Angular structural directives like `ngIf`, `ngFor`, or custom directives.

```html
<ul *ngIf="players$ | async as players; else loading" class="my-4">
  <li *ngFor="let player of players" [appOnlineStatus]="player.online">
    <a [routerLink]="['/profile', player.id]">{{ player.name }}</a>
  </li>
</ul>

<ng-template #loading>
  <p class="my-4">Loading&hellip;</p>
</ng-template>
```

## ng-template and *ngIf in Angular

The highlighted code is an Angular template that uses the `*ngIf` directive along with the `ng-template` tag. 

Here's a breakdown of the code:

| Code Segment | Description |
| --- | --- |
| `<ul *ngIf="players$ | async as players; else loading" class="my-4">` | This line uses the `*ngIf` directive to subscribe to the `players$` Observable. If players are present, it assigns them to a local variable `players` and renders the `ul` element. If players are not present, it renders an alternative template `loading`. |
| `<ng-template #loading>` | This is an `ng-template` tag. The `#loading` is a template reference variable that can be used to reference this template elsewhere in the component. |

## Difference between ng-template and ng-container in Angular

`ng-template` and `ng-container` are both structural directives in Angular, but they are used in different scenarios:

- `ng-template`: This is a template element that Angular uses to render the HTML. It is never displayed directly. Instead, it's used as a blueprint for creating views. You can apply structural directives like `*ngIf`, `*ngFor`, etc., to `ng-template`.

- `ng-container`: This is a grouping element that doesn't interfere with styles or layout because Angular doesn't put it in the DOM. This is useful when you want to apply a structural directive but don't want to create an extra element (like a `div`), which might mess up your layout or styles.

## Example of ng-container in Angular

Here's an example of how you might use `ng-container` in Angular:

```html
<ng-container *ngFor="let item of items">
    <div *ngIf="item.isVisible">{{ item.name }}</div>
</ng-container>
```

In this example, the `ng-container` directive is used to apply the `*ngFor` directive without creating an extra DOM element. Then, within the `ng-container`, the `*ngIf` directive is used to conditionally render a div element for each visible item.