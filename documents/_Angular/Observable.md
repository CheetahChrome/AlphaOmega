---
title: Angular Observable
layout: default
---
# Angular Observable


In Angular, an RxJS Observable is a powerful tool for managing asynchronous data streams. An Observable is essentially a sequence of data items that are emitted over time. These data items can be of any type, and they can be emitted at any time.

Here are some key points to keep in mind when working with Observables in Angular:

- Observables are lazy - they don't do anything until they are subscribed to.
- Observables can emit multiple values over time, unlike Promises which emit a single value.
- Observables can be cancelled by unsubscribing from them.
- Observables can be combined and transformed using a variety of operators provided by the RxJS library.

In an Angular application, Observables are commonly used to manage data streams from HTTP requests, user input events, and other sources of asynchronous data. They are often used in combination with other Angular features such as the async pipe, which allows you to bind an Observable directly to a template without subscribing to it manually.

Here's an example of creating an Observable in Angular:

```typescript
import { Observable } from 'rxjs';

const myObservable = new Observable(observer => {
  observer.next('Hello');
  observer.next('World');
  observer.complete();
});
```


In this example, we import the `Observable` class from the `rxjs` package, and create a new Observable by passing a function to its constructor. The function receives an observer object that can be used to emit values using the `next()` method, and signal that the Observable has completed using the `complete()` method.

We can then subscribe to this Observable to receive its emitted values:

```typescript
myObservable.subscribe(value => {
  console.log(value);
});
```


Output will be   
```
Hello 
World
```

Overall, RxJS Observables are a powerful and flexible tool for managing asynchronous data streams in Angular applications.