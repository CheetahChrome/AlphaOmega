---
title: RxJS vs NgRx
layout: default
---
# RxJS vs NgRx



**RxJS** and ****NgRx**** are both libraries for managing reactive data streams in Angular applications, but they serve different purposes:

**RxJS**: **RxJS** is a standalone library that provides a set of powerful tools for managing asynchronous data streams in JavaScript applications, including Angular. It provides a rich set of operators for transforming and combining data streams, and can be used with any data source that emits data over time. **RxJS** is not specific to Angular and can be used in any JavaScript application.

**NgRx**: **NgRx** is a library for managing state in Angular applications using the principles of the Redux pattern. It is built on top of **RxJS** and provides a set of tools for managing application state in a predictable, testable way. **NgRx** provides a store that holds the application state, as well as actions that describe state changes and reducers that handle those changes. **NgRx** is specific to Angular and provides a way to manage complex state in large-scale Angular applications.

In summary, **RxJS** provides a powerful set of tools for managing asynchronous data streams in Angular applications, while **NgRx** provides a way to manage application state in a predictable, testable way using the Redux pattern. While **NgRx** is built on top of **RxJS**, they serve different purposes and can be used together to manage both asynchronous data streams and application state in an Angular application.