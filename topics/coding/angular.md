# Angular Prompts

Angular/RxJS/Nebular-specific prompts. See [`general.md`](./general.md) for framework-agnostic prompts and [`AGENTS.md`](../../AGENTS.md) for the philosophy and how to contribute.

## Signals & Reactivity

- 🔗 Migrate component state from `@Input()`/RxJS `BehaviorSubject` to `signal()`/`computed()`, keeping the public API the same
- 🧮 Replace derived state computed in getters or `ngOnChanges` with `computed()` signals
- 🎬 Replace manual side-effect wiring (subscribe callbacks that mutate other state) with `effect()`, keeping effects free of direct DOM writes
- 🔀 Convert an existing Observable stream to a signal with `toSignal()` (and back with `toObservable()`) where it simplifies template bindings
- 🪄 Replace `@Input()` setter side-effects with a `linkedSignal()` where the derived state should reset on input change

## Standalone Components & Modern APIs

- 🧱 Convert an NgModule-based component/directive/pipe to standalone, updating its imports and any module that declared it
- 💉 Replace constructor-based dependency injection with `inject()`, especially in functional guards, resolvers, and interceptors
- 🌳 Replace `*ngIf`/`*ngFor`/`*ngSwitch` with the built-in control-flow syntax (`@if`/`@for`/`@switch`), adding `track` expressions to every `@for`
- 🚪 Convert eagerly-imported feature modules to lazy-loaded standalone routes with `loadComponent`/`loadChildren`
- 🎛️ Adopt `input()`/`output()` signal-based component APIs to replace `@Input()`/`@Output()` decorators

## Angular & RxJS

- 🔁 Replace imperative subscriptions with async pipe and reactive patterns to eliminate manual subscribe/unsubscribe boilerplate
- 🚿 Audit all component subscriptions for missing unsubscribe or takeUntil — add cleanup to prevent memory leaks
- 🧹 Replace manual `takeUntil(this.destroy$)` boilerplate with `takeUntilDestroyed()`
- 📡 Refactor service methods to use shareReplay(1) where multiple consumers request the same data to avoid duplicate HTTP calls
- 🧵 Replace nested subscribe() calls with switchMap, mergeMap, or forkJoin for cleaner async composition
- ⏸️ Use debounceTime and distinctUntilChanged on form inputs and search streams to reduce excessive HTTP calls and improve responsiveness
- 🔍 Add breakpoint-friendly logging for RxJS observables (tap operator) to trace data flow through pipelines
- 🩹 Replace manual retry loops with RxJS `retry`/`retryWhen` operators for resilient HTTP calls

## Performance

- 🦥 Implement trackBy functions in all *ngFor loops (or `track` expressions in `@for`) to prevent unnecessary DOM re-renders
- ⚡ Audit @Input() bound objects — replace full-object bindings with primitive values or signals where possible to reduce change detection cycles
- 🎯 Leverage OnPush change detection strategy in presentational components to minimize change detection runs across the component tree
- 📦 Defer heavy computations with async pipes and observables; avoid synchronous data transformations in templates
- 📈 Profile component render times with Angular DevTools and identify bottlenecks; optimize or memoize expensive getters and methods
- ⏳ Wrap non-critical below-the-fold sections in `@defer` blocks to reduce initial bundle size and time-to-interactive
- 🏎️ Enable zoneless change detection (`provideExperimentalZonelessChangeDetection`) where the component tree is fully signal-driven

## UX / UI

- 🪶 Add skeleton loading states or spinners (NbSpinnerModule) to data-heavy pages while API calls are in flight
- 📭 Add empty-state messages to tables and lists when the API returns zero results
- 🔔 Add toast notifications (NbToastrService) for user feedback on successful saves, deletions, and error scenarios
- ⚙️ Add confirmation dialogs (NbDialogService) before destructive actions (delete, cancel, clear form) to prevent accidental data loss
- 🔄 Add optimistic UI updates for common actions (like/save/delete) that roll back on request failure

## SEO & Meta

- 🏷️ Add descriptive <title> and <meta name="description"> tags to every route using Angular's Title and Meta services
- 🕸️ Prerender or server-render public marketing routes to ensure crawlers and social previews see full content

## Security

- 🔐 Sanitize user-provided HTML with Angular's `DomSanitizer` before binding it with `[innerHTML]`, and prefer `{{}}` interpolation over `innerHTML` wherever raw HTML isn't required
- 🚧 Set a strict Content-Security-Policy and disable Angular's `bypassSecurityTrust*` escape hatches except where absolutely required
