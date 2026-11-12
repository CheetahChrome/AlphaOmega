---
title: Angular Interview Questions
layout: default
---
# Angular Interview Questions

These notes reflect the current Angular documentation (v22, November 2026). NgModules and older testing setups still exist in legacy applications, but are not the default starting point for new Angular apps.

## Fundamentals

### What is Angular?

Angular is a TypeScript-based web application framework. It includes components and templates, dependency injection, routing, forms, HTTP services, and the Angular CLI.

### What are components, directives, services, and pipes?

Components define UI views using a TypeScript class and a template. Directives add behavior to elements or control rendering. Services hold reusable application logic or data access. Pipes transform values for display in templates.

### What is the Angular CLI?

The Angular CLI creates and maintains projects, generates code, runs development builds and tests, and produces production builds. Common commands include `ng new`, `ng serve`, `ng generate`, `ng test`, and `ng build`.

## Components and Templates

### What is a standalone component?

Standalone components directly import the components, directives, and pipes their templates use, and can be bootstrapped without an NgModule. Components are standalone by default starting in Angular 19; NgModules remain supported for existing applications and library integration.

### What are Angular's binding types?

Interpolation (`{{ value }}`) displays text; property binding (`[value]="value"`) sets a DOM or component property; event binding (`(click)="save()"`) responds to events; and two-way binding (`[(ngModel)]="name"`) combines input and output binding. `ngModel` is a directive, not a structural `*` directive.

### What is Angular's built-in template control flow?

Templates can use `@if` / `@else`, `@for`, and `@switch` blocks. Use a stable key such as `track item.id` with `@for` so Angular can efficiently associate data with rendered DOM nodes. The older `*ngIf` and `*ngFor` syntax remains common in existing code.

### What are the key component lifecycle hooks?

`ngOnChanges` runs when inputs change (and runs before the initial `ngOnInit`); `ngOnInit` runs once after initial inputs are set; `ngAfterViewInit` runs after the view is initialized; and `ngOnDestroy` runs before destruction. Use `afterNextRender` or `afterEveryRender` for work that must happen after rendering, such as browser DOM interaction.

## Signals and RxJS

### What are Signals?

Signals are reactive wrappers around values. Angular tracks where a signal is read and updates affected consumers when it changes, enabling targeted rendering work.

### How do `signal()`, `computed()`, and `effect()` differ?

`signal(initialValue)` creates writable state; update it with `.set(value)` or `.update(current => next)`. `computed(() => ...)` creates a lazy, memoized, read-only value derived from other signals. `effect(() => ...)` runs in response to signal reads changing and is intended mainly to connect reactive state to imperative, non-signal APIs, not to propagate state between signals.

### What is the difference between writable and readonly signals?

A writable signal exposes `.set()` and `.update()`. A computed signal is read-only, and a writable signal can expose a read-only view with `.asReadonly()`. Readonly signals prevent writes through that API, but do not prevent mutation of nested objects.

### How do Signals compare with RxJS Observables?

Signals hold a synchronous current value and are useful for component state and derived values. Observables represent streams over time and provide operators for asynchronous work, cancellation, and event composition; Angular HTTP calls return Observables. Use the abstraction that fits the data flow rather than treating one as a replacement for the other.

### How do Signals and RxJS work together?

Angular's `@angular/core/rxjs-interop` provides `toSignal()` to read an Observable as a signal and `toObservable()` to expose a signal as an Observable. `toSignal()` subscribes immediately and cleans up with its owning context by default, so create it once and reuse it.

## Dependency Injection

### How does modern Angular dependency injection work?

Angular provides dependencies through hierarchical injectors. `@Injectable({ providedIn: 'root' })` is a common application-wide service scope; component- or route-level providers can create narrower instances. Injecting dependencies keeps construction and implementation choices outside the consuming class.

### What is `inject()` and when can it be used?

`inject(Service)` retrieves a dependency in an Angular injection context, commonly a component, directive, or service field initializer, or a functional guard or interceptor. Constructor injection is still supported; `inject()` is a flexible alternative, not a different DI system.

## Routing

### How is the Angular Router configured and used?

Define a `Routes` array and register it with `provideRouter(routes)`. `RouterOutlet` displays the active route, `RouterLink` provides in-app navigation, and the router also exposes route parameters, query parameters, navigation events, and programmatic navigation.

### How does modern route lazy loading work?

Use `loadComponent` to load a standalone component on demand, or `loadChildren` to load a route configuration. Dynamic imports create separate chunks that are downloaded when the route is needed. Lazy loading can reduce the initial bundle, but adds a request on first navigation.

### What are route guards and resolvers?

Functional guards such as `CanActivateFn` control navigation and can return a boolean, redirect, Promise, or Observable. Resolvers load essential data before route activation. Guards improve navigation and user experience; authorization must also be enforced on the server because client-side checks can be bypassed.

## Forms and HTTP

### When should you use Reactive Forms?

Reactive Forms define an explicit form model with `FormControl`, `FormGroup`, or `FormArray`; they support synchronous validation, typed forms, and observable `valueChanges`. They are a strong fit for complex forms that need predictable state and testing. Angular also documents Signal Forms as a newer signal-based option.

### How does Angular handle HTTP and interceptors?

Inject `HttpClient` to make typed HTTP requests; its methods return Observables, so requests execute when subscribed. Configure shared behavior with `provideHttpClient()` and functional interceptors via `withInterceptors()`. Interceptors can handle cross-cutting concerns such as authentication headers, logging, caching, and retry policy. Handle request failures in the Observable pipeline (for example, with `catchError`) and present useful error state to users.

## Performance

### What is change detection?

Change detection is Angular's process for checking component bindings and updating the DOM when application state changes. Angular walks the component tree and can skip subtrees that do not need checking; signals read in templates notify Angular when their values change.

### What is `OnPush` change detection?

`OnPush` lets Angular skip a component subtree until it receives a changed input, handles an event in that subtree, is explicitly marked for checking, or a signal read by its template changes. `OnPush` is the default strategy starting in Angular 22; older versions may require opting in with `ChangeDetectionStrategy.OnPush`.

### What are SSR and hydration?

Server-side rendering (SSR) sends rendered HTML from the server; prerendering generates HTML at build time. Hydration reuses server-rendered DOM in the browser and attaches Angular behavior instead of recreating the whole view. Server and client output must have matching DOM structure, and code that uses browser-only APIs must account for running on the server.

## Testing

### What is a modern Angular testing strategy?

Test behavior at the right level: unit-test pure logic and services, use `TestBed` for component and DOM interactions, and test routing and HTTP with Angular's testing utilities. New Angular CLI projects use Vitest by default; browser-based end-to-end testing can use tools such as Playwright. Jasmine/Karma projects are still found in existing applications, while Protractor is obsolete.

## Further Reading

- [Angular Signals](https://angular.dev/guide/signals) and [RxJS interop](https://angular.dev/ecosystem/rxjs-interop)
- [Components and lifecycle](https://angular.dev/guide/components) and [template control flow](https://angular.dev/guide/templates/control-flow)
- [Dependency injection](https://angular.dev/guide/di) and [routing](https://angular.dev/guide/routing)
- [Forms](https://angular.dev/guide/forms) and [HTTP](https://angular.dev/guide/http)
- [Change detection](https://angular.dev/best-practices/skipping-subtrees), [SSR](https://angular.dev/guide/ssr), [hydration](https://angular.dev/guide/hydration), and [testing](https://angular.dev/guide/testing)
