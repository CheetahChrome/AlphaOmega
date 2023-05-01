---
# Angular Interpolation
title: Angular Data Sharing
layout: default
---
# Angular Data Share

In Angular, there are several ways to share data between components. Here are some common approaches:

| Approach | Type | Description   |
|-|-| -|
| Parent-Child Component Interaction   | `Input`      | You can pass data from a parent component to a child component using Input binding. Input binding allows the parent component to pass data to the child component as a property binding. In the child component, you can access the data using the @Input decorator. |
| Child-Parent Component Interaction  |`Output`       | You can pass data from a child component to a parent component using Output binding. Output binding allows the child component to emit events to the parent component. In the parent component, you can listen to the emitted events using event binding. |
| Service                              | Injectable      | You can create a service to store data and then inject the service into the components that need to access the data. The service acts as a centralized store for data, which can be accessed by any component that injects the service. |
| State Management Libraries         | Libraries         | You can use state management libraries such as Redux, NgRx, or Akita to manage application state. These libraries provide a centralized store for application state and allow components to access and update the state. |
| Local Storage or Session Storage  | Session Storage | You can also use local storage or session storage to store data, which can be accessed by different components in the application. |
