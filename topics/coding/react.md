# React Prompts

React-specific prompts. See [`general.md`](./general.md) for framework-agnostic prompts and [`AGENTS.md`](../../AGENTS.md) for the philosophy and how to contribute.

## Hooks & State

- 🪝 Extract repeated stateful logic (data fetching, subscriptions, form handling) into a custom hook
- 🌲 Replace prop-drilling through 3+ component levels with `useContext` or component composition (children/render props)
- 🔁 Fix `useEffect` dependency arrays — add missing dependencies or restructure the effect so the linter's exhaustive-deps rule passes without suppressing it
- 🧹 Add cleanup functions to `useEffect` for subscriptions, timers, and event listeners to prevent memory leaks and stale closures
- 🧩 Replace multiple related `useState` calls with a single `useReducer` when state transitions depend on each other
- 🪄 Replace derived state stored in `useState` with a value computed directly during render (or memoized) to avoid sync bugs

## Performance

- 🧮 Wrap expensive computations in `useMemo` and stable callback props in `useCallback`, only where profiling shows it matters
- 🎯 Wrap pure presentational components in `React.memo` to avoid unnecessary re-renders from parent updates
- 📦 Code-split route-level or heavy components with `lazy()` and `Suspense`
- 🔑 Audit list rendering for stable, unique `key` props instead of array index
- 🪞 Replace context values that change on every render with split contexts or memoized value objects to avoid re-rendering all consumers
- 📈 Profile re-renders with React DevTools Profiler and fix the components with the highest wasted render counts

## Modern Patterns

- 🖥️ Clarify Server vs Client Component boundaries — add `'use client'` only where interactivity/browser APIs are actually needed, keep data-fetching components on the server
- 🏛️ Replace a class component with a function component and equivalent hooks (state, lifecycle, refs)
- ⏳ Replace manual loading/error boolean flags with `Suspense` boundaries and error boundaries where the data layer supports it
- 📝 Replace uncontrolled form logic with the `useActionState`/form Actions pattern for progressive enhancement where applicable
- 🔗 Replace `forwardRef` + manual prop threading with the `ref` as a normal prop where the React version supports it
- ✨ Adopt the `use()` hook to read promises/context directly in render where it simplifies data fetching

## Testing

- 🧪 Write component tests with React Testing Library that query by role/label text instead of test IDs or implementation details
- 🎭 Mock network requests at the boundary (MSW or fetch mocks) rather than mocking hooks or components directly
- 🎬 Add integration tests for critical user flows using Playwright or Cypress end-to-end
