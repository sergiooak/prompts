# Vue Prompts

Vue-specific prompts. See [`general.md`](./general.md) for framework-agnostic prompts and [`AGENTS.md`](../../AGENTS.md) for the philosophy and how to contribute.

## Composition API & Reactivity

- 🧱 Migrate an Options API component to `<script setup>` with the Composition API, keeping props/emits/exposed API identical
- 📎 Replace primitive `ref()` overuse for objects with `reactive()` (or vice versa) based on whether the value is reassigned wholesale or mutated in place
- 🧮 Replace values recomputed in methods or watchers with `computed()` properties
- 👀 Replace `watch` callbacks that just re-derive state with `watchEffect`, and use `watch` only when you need the old/new values or explicit dependency control
- 🧵 Add explicit TypeScript generics to `defineProps`/`defineEmits` instead of relying on runtime prop declarations
- 🪄 Extract repeated computed/watch logic duplicated across sibling components into a shared composable

## Performance

- 🦥 Add `v-memo` to expensive list items that rarely change to skip re-render diffing
- 🧊 Wrap large read-only data structures in `shallowRef`/`shallowReactive` to avoid deep reactivity overhead
- 📦 Lazy-load routes and heavy components with dynamic `import()` and `defineAsyncComponent`
- 🔑 Audit `v-for` loops for stable, unique `:key` bindings instead of array index
- 🧹 Ensure `watch`/`watchEffect` sources and event listeners are cleaned up in `onUnmounted` when not auto-stopped by the component scope
- ❄️ Use `v-once` for static content that never changes after initial render

## Modern Patterns

- 🧰 Extract shared stateful logic across components into a composable (`useXxx` function) instead of a mixin
- 🗃️ Replace ad-hoc global state (event bus, provide/inject soup) with a Pinia store
- 🔌 Replace `provide`/`inject` without typing with typed injection keys (`InjectionKey<T>`)
- 🧩 Replace slot-based prop drilling with scoped slots that expose only the data the child needs
- ⏳ Add `<Suspense>` around components with top-level `await` in `<script setup>` for async setup
- 🪝 Replace manual template refs juggling with the `useTemplateRef` helper (Vue 3.5+)

## Testing

- 🧪 Write component tests with Vue Testing Library / `@vue/test-utils` that query by role/label text instead of implementation details
- 🎭 Mock network requests at the boundary rather than mocking composables or components directly
- 🎬 Add Cypress or Playwright end-to-end tests for critical multi-page user flows
