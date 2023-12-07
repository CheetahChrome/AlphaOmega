---
layout: post
title: Angular Property Binding
date: 2022-10-01
categories: [Angular, Property Binding]
---

Property binding in Angular is a technique that allows you to set properties of view elements from a component's data. Essentially, you bind a property of a DOM element to a property of your component class. This is typically done using the `[propertyName]` syntax.

Here's an example to illustrate this. Let's assume you have a component with a property `imageUrl` and you want to bind this property to the `src` attribute of an `<img>` element in your component's template.

The following markdown code block includes a two-column table. The left column describes each part of the code, while the right column provides the corresponding code snippet.

| Description | Code |
| ----------- | ---- |
| Component class in TypeScript. It has a property `imageUrl` that holds the URL of an image. | `export class AppComponent { imageUrl = 'https://example.com/image.jpg'; }` |
| Template HTML. The `src` attribute of the `<img>` tag is bound to the `imageUrl` property of the component. | `<img [src]="imageUrl">` |

This example demonstrates how Angular's property binding works. When the `imageUrl` property in your component changes, Angular automatically updates the `src` attribute of the image in the view to reflect this change.

---

```html
<ul *ngIf="players$ | async as players; else loading" class="my-4">
  <li *ngFor="let player of players" [appOnlineStatus]="player.online">
    <a [routerLink]="['/profile', player.id]">{{ player.name }}</a>
  </li>
</ul>
```

| Code Segment | Description |
| --- | --- |
| `<ul *ngIf="players$ \| async as players; else loading" class="my-4">` | The `*ngIf` directive is used to conditionally render this element based on the presence of `players`.<br/>The `players$ \| async as players` part is subscribing to the `players$` Observable and assigning the result to a local variable `players`.</br>The `else loading` part specifies an alternative template `loading` to be rendered when `players$` is falsy. |
| `<li *ngFor="let player of players" [appOnlineStatus]="player.online">` | This is a `li` element. The `*ngFor` directive is used to iterate over each `player` in the `players` array and create a new `li` element for each one. The `[appOnlineStatus]="player.online"` part is a property binding that sets the `appOnlineStatus` property to the `online` property of the current `player`. |
| `<a [routerLink]="['/profile', player.id]">{{ player.name }}</a>` | This is an `a` element. The `[routerLink]="['/profile', player.id]"` part is a property binding that sets the `routerLink` directive to an array that will construct a URL like `/profile/1`, where `1` is the `id` of the current `player`. The `{{ player.name }}` part is interpolation that will be replaced with the `name` property of the current `player`. |



