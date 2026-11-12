---
title: Angular Interview Questions
layout: default
---
# Angular Interview Questions

These notes focus on modern Angular practices from v19 through the current v22 release (November 2026). The **Angular Versions** section summarizes earlier migration milestones and legacy patterns.

## Fundamentals

| Topic | Summary |
|-------|---------|
| Framework | Angular is a TypeScript-based web application framework. |
| Components and templates | `@Component` classes and HTML templates define UI views. |
| Directives | `@Directive` types add behavior to elements or control rendering. |
| Services | `@Injectable` classes provide reusable logic, state, or data access. |
| Dependency injection | `inject()` and configured providers supply dependencies to classes. |
| Routing | `provideRouter()` configures routes that map URLs to views. |
| Forms | `ReactiveFormsModule` or `FormsModule` capture and validate user input. |
| HTTP client | `HttpClient` sends HTTP requests and returns Observables. |
| Angular CLI | The `ng` CLI creates, serves, tests, and builds Angular applications. |

### What are components, directives, services, and pipes?

| Building block | Role and modern usage |
|----------------|-----------------------|
| Components | Own a view and its UI state. Standalone components import the dependencies their templates use. |
| Directives | Attach reusable behavior to elements. Use Angular's built-in `@if` and `@for` blocks for conditional and repeated rendering. |
| Services | Encapsulate reusable logic, state, or data access outside views. Provider scope controls sharing: `providedIn: 'root'` is app-wide, while component providers create local instances. |
| Pipes | - Provide reusable template transformations, such as formatting.<br/> - Pure by default: rerun only when an input value changes; for objects or arrays, when the reference changes. |

### What is the Angular CLI?

The Angular CLI creates and maintains projects, generates code, runs development builds and tests, and produces production builds. Common commands include `ng new`, `ng serve`, `ng generate`, `ng test`, and `ng build`.

The Angular CLI creates and maintains projects, generates code, runs development builds and tests, and produces production builds. Common commands include `ng new`, `ng serve`, `ng generate`, `ng test`, and `ng build`.


## Components and Templates

### What is a standalone component?

| Topic | Summary |
|-------|---------|
| Standalone component | Can be used and bootstrapped without being declared in an `NgModule`. |
| Template dependencies | Lists the components, directives, and pipes used by its template in the component's `imports`. |
| Default behavior | Components are standalone by default starting in Angular 19; existing `NgModule` declarations can be migrated incrementally. |
### What are Angular's binding types?
| Binding | Code | Summary |
|---------|------|---------|
| Interpolation | <code>&#123;&#123; value &#125;&#125;</code> | Displays a value as text. |
| Property binding | `[value]="value"` | Binds an expression to a DOM or component property. |
| Event binding | `(click)="save()"` | Calls a handler in response to an event. |
| Two-way binding | `[(ngModel)]="name"` | Combines property and event binding to keep a value synchronized; `ngModel` is a directive, not a structural `*` directive. |

### What is Angular's built-in template control flow?

| Block | Summary |
|-------|---------|
| `@if` / `@else` | Conditionally displays template content. |
| `@for` | Repeats content for a collection; use a stable key such as `track item.id` to associate items with DOM nodes. |
| `@switch` | Displays content for matching cases. |

### What are the key component lifecycle hooks?

| Hook | Summary |
|------|---------|
| `ngOnChanges` | Runs when inputs change; the initial call occurs before `ngOnInit`. |
| `ngOnInit` | Runs once after the initial inputs are set. |
| `ngAfterViewInit` | Runs once after the component's view is initialized. |
| `ngOnDestroy` | Runs once before the component is destroyed. |
| `afterNextRender` / `afterEveryRender` | Register callbacks after rendering, useful for browser DOM work; these callbacks do not run during server-side rendering. |

## Signals and RxJS

### What are Signals?

Signals are reactive wrappers around values. Angular tracks where a signal is read and updates affected consumers when it changes, enabling targeted rendering work.

### How do `signal()`, `computed()`, and `effect()` differ?

`signal(initialValue)` creates writable state; update it with `.set(value)` or `.update(current => next)`. `computed(() => ...)` creates a lazy, memoized, read-only value derived from other signals. `effect(() => ...)` runs in response to signal reads changing and is intended mainly to connect reactive state to imperative, non-signal APIs, not to propagate state between signals.

### What is the difference between writable and readonly signals?

A writable signal exposes `.set()` and `.update()`. A computed signal is read-only, and a writable signal can expose a read-only view with `.asReadonly()`. Readonly signals prevent writes through that API, but do not prevent mutation of nested objects.

### How do Signals compare with RxJS Observables?

Signals hold a synchronous current value and are useful for component state and derived values. RxJS `Observable`s represent streams over time and provide operators for asynchronous work, cancellation, and event composition; Angular HTTP calls return `Observable`s. Use the abstraction that fits the data flow rather than treating one as a replacement for the other.

### How do Signals and RxJS work together?

Angular's `@angular/core/rxjs-interop` provides `toSignal()` to read an `Observable` as a signal and `toObservable()` to expose a signal as an `Observable`. `toSignal()` subscribes immediately and cleans up with its owning context by default, so create it once and reuse it.

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

Functional guards such as `CanActivateFn` control navigation and can return a boolean, redirect, `Promise`, or `Observable`. Resolvers load essential data before route activation. Guards improve navigation and user experience; authorization must also be enforced on the server because client-side checks can be bypassed.

## Forms and HTTP

### When should you use Reactive Forms?

Reactive Forms define an explicit form model with `FormControl`, `FormGroup`, or `FormArray`; they support synchronous validation, typed forms, and observable `valueChanges`. They remain a strong fit for complex forms that need predictable state and testing. Signal Forms provide a signal-based alternative and are stable in Angular 22.

### How does Angular handle HTTP and interceptors?

Inject `HttpClient` to make typed HTTP requests; its methods return `Observable`s, so requests execute when subscribed. Configure shared behavior with `provideHttpClient()` and functional interceptors via `withInterceptors()`. Interceptors can handle cross-cutting concerns such as authentication headers, logging, caching, and retry policy. Handle request failures in the `Observable` pipeline (for example, with `catchError`) and present useful error state to users.

## Performance

### What is change detection?

Change detection is Angular's process for checking component bindings and updating the DOM when application state changes. Angular walks the component tree and can skip subtrees that do not need checking; signals read in templates notify Angular when their values change.

### What is `OnPush` change detection?

`OnPush` lets Angular skip a component subtree until it receives a changed input, handles an event in that subtree, is explicitly marked for checking, or a signal read by its template changes. `OnPush` is the default strategy starting in Angular 22.

### What are SSR and hydration?

Server-side rendering (SSR) sends rendered HTML from the server; prerendering generates HTML at build time. Hydration reuses server-rendered DOM in the browser and attaches Angular behavior instead of recreating the whole view. Server and client output must have matching DOM structure, and code that uses browser-only APIs must account for running on the server.

## Testing

### What is a modern Angular testing strategy?

Test behavior at the right level: unit-test pure logic and services, use `TestBed` for component and DOM interactions, and test routing and HTTP with Angular's testing utilities. New Angular CLI projects use `Vitest` by default; browser-based end-to-end testing can use tools such as `Playwright`.

## Angular Versions

| Version | Migration context |
|---------|-------------------|
| AngularJS 1.5.2 | This is AngularJS, a separate 1.x framework. Its `.component()` API, one-way `<` inputs, and `&` callback outputs encouraged component-based structure. AngularJS and modern Angular can coexist during an incremental migration using `@angular/upgrade`; their APIs are not interchangeable. |
| Angular 15 | Standalone APIs became stable, making it practical to move feature by feature from `NgModule` declarations toward standalone components and provider-based application setup. |
| Angular 16 | Introduced Signals in developer preview. This was the transition point for evaluating signal-based state alongside established RxJS streams. |
| Angular 19 | Components, directives, and pipes became standalone by default. When migrating, declarations that remain in an `NgModule` need `standalone: false`; the Angular update schematic handles this transition. Signals are a core state primitive, while RxJS remains useful for asynchronous streams. |
| Angular 20–22 | Continue updating with Angular's update guide and `ng update`. In v22, `OnPush` is the default change-detection strategy, Signal Forms are stable, and new CLI projects use `Vitest`. Move older templates using `*ngIf` / `*ngFor` toward built-in control flow; replace legacy Karma/Jasmine and Protractor setups as part of a planned testing migration. |

## Further Reading

- [Angular versioning and updates](https://angular.dev/reference/releases) and the [Angular update guide](https://angular.dev/update-guide)
- [AngularJS components](https://docs.angularjs.org/guide/component) and [Angular upgrade APIs](https://angular.dev/api/upgrade/static/UpgradeModule)
- [Angular Signals](https://angular.dev/guide/signals) and [RxJS interop](https://angular.dev/ecosystem/rxjs-interop)
- [Components and lifecycle](https://angular.dev/guide/components) and [template control flow](https://angular.dev/guide/templates/control-flow)
- [Dependency injection](https://angular.dev/guide/di) and [routing](https://angular.dev/guide/routing)
- [Forms](https://angular.dev/guide/forms) and [HTTP](https://angular.dev/guide/http)
- [Change detection](https://angular.dev/best-practices/skipping-subtrees), [SSR](https://angular.dev/guide/ssr), [hydration](https://angular.dev/guide/hydration), and [testing](https://angular.dev/guide/testing)
