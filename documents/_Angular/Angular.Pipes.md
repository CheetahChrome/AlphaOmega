---
title: Angular Pipes
layout: default
---

In Angular, a "pipe" `|` is a feature that allows you to transform the data displayed in templates. Pipes are a way to format and filter data before rendering it in the user interface. They are particularly useful for displaying data in a more human-readable or customized format.

Angular provides several built-in pipes for common data transformations, and you can also create custom pipes to meet your specific formatting and filtering needs.



Note that the blocks are in `{{}}` format.  
[Angular - Understanding Pipes](https://angular.io/guide/pipes-overview)

| Pipe Name | Description | Example |
| --- | --- | - |
| DatePipe      | Formats dates into various formats. | ` currentDate | date:'short' ` |
| UpperCasePipe | Transforms text to all upper case | `'Hello, World!' | uppercase`|
| DecimalPipe   | Transforms a number into a string with a decimal point, formatted according to locale rules | `12345.6789 | number:'1.2-2'`|
| CurrencyPipe  | Transforms a number to a currency string, formatted according to locale rules | `1234.56 | currency:'USD':'symbol':'1.2-2'` |
| SlicePipe     | Extracts a portion of an array or string. | `'Angular' | slice:0:3 ` |
| AsyncPipe     | Handles asynchronous data, such as Observables.  | `{{ asyncData$ | async }}`|
| LowerCasePipe | Transforms text to all lower case |
| PercentPipe   | Transforms a number to a percentage string, formatted according to locale rules |

## Why are Pipes Considered Pure Functions in Angular?

In Angular, pipes are considered pure functions because they produce the same output given the same input and do not have any observable side effects. 

A pure pipe is only called when Angular detects a pure change to the input value. A pure change is either a change to a primitive input value (like `String`, `Number`, `Boolean`, `Symbol`) or a changed object reference (like `Date`, `Array`, `Function`, `Object`).

This is why pipes are efficient. Angular keeps track of changes to the input values and only executes the pipe when it detects a change. This can lead to significant performance improvements for large arrays and complex objects.

## When to Use Impure Pipes in Angular

Impure pipes in Angular are used when you need to react to changes within complex objects like nested properties or arrays, or when you need to handle data that changes over time, like data coming from a WebSocket or user input.

Unlike pure pipes, impure pipes are executed on each change detection cycle, regardless of whether the input values have changed. This means they can react to changes within objects, not just changes to the object reference itself.

However, because impure pipes are executed so frequently, they can have performance implications if not used carefully. Therefore, they should be used sparingly and only when necessary.

## Example of an Impure Pipe in Angular

Here's an example of an impure pipe in Angular:

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
    name: 'randomNumber',
    pure: false
})
export class RandomNumberPipe implements PipeTransform {
    transform(value: any): number {
        return Math.random();
    }
}
```

In this example, the `RandomNumberPipe` is an impure pipe that returns a random number every time it's called, regardless of the input value. The pure: false property in the `@Pipe` decorator indicates that this is an impure pipe.