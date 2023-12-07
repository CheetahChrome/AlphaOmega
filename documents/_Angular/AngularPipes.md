---
title: Angular Pipes
layout: default
---

In Angular, a "pipe" `|` is a feature that allows you to transform the data displayed in templates. Pipes are a way to format and filter data before rendering it in the user interface. They are particularly useful for displaying data in a more human-readable or customized format.

Angular provides several built-in pipes for common data transformations, and you can also create custom pipes to meet your specific formatting and filtering needs.


[Angular - Understanding Pipes](https://angular.io/guide/pipes-overview)

| Pipe Name | Description | Example |
| --- | --- | - |
| DatePipe  | Formats dates into various formats. | `<p>{{ currentDate | date:'short' }}</p>` |
| UpperCasePipe | Transforms text to all upper case | `<p>{{ 'Hello, World!' | uppercase }}</p>`|
| DecimalPipe | Transforms a number into a string with a decimal point, formatted according to locale rules | `{{ 12345.6789 | number\:'1.2-2' }}`|
| CurrencyPipe | Transforms a number to a currency string, formatted according to locale rules | `{{ 1234.56 | currency:'USD'\:'symbol'\:'1.2-2' }}` |
| **SlicePipe:**    | Extracts a portion of an array or string. | `<p>{{ 'Angular' | slice\:0\:3 }}</p>` |
| **AsyncPipe:**    | Handles asynchronous data, such as Observables.  | `<p>{{ asyncData$ | async }}</p>`|
| LowerCasePipe | Transforms text to all lower case |
| PercentPipe | Transforms a number to a percentage string, formatted according to locale rules |