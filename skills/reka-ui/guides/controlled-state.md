# Controlled State
Reka UI provides flexible state management for components, allowing developers to use either \\controlled\\ or \\uncontrolled\\ state. Understanding when to use each approach ensures better integration with Vue's reactivity system.
\\\
## Controlled vs. Uncontrolled State
### Controlled State
A \\controlled\\ component receives its state as a prop and requires explicit updates via event listeners. The parent component manages and synchronizes the state.
#### Example: Controlled `SwitchRoot`
```vue

```
\\How it works:\\
\ The `SwitchRoot` component’s state is managed by the `isActive` ref.
\ The `@update:modelValue` event ensures updates propagate correctly.
- You need to sync state with Vuex, Pinia, or an API.
- Multiple components rely on the same state.
- You want fine-grained control over updates.
#### Using v-model with Controlled Components
Vue’s `v-model` syntax provides a convenient way to bind values to controlled components in Reka UI. It automatically handles passing the value and listening for updates.
Example: Using `v-model` with `SwitchRoot`
```vue

```
### Uncontrolled State
An \\uncontrolled\\ component manages its own state internally, without requiring a parent-controlled prop. Instead of `modelValue`, Reka UI components use `defaultValue` to initialize state.
#### Example: Uncontrolled `SwitchRoot`
```vue

```
\\How it works:\\
\ The `SwitchRoot` initializes its state with `defaultValue`.
\ State changes occur internally without external control.
- The component does not need to sync with external logic.
- You want a simpler setup without explicit state management.
- The state is local and does not impact other components.
## Common Mistakes & Fixes
### 1. Forgetting `@update:modelValue`
```vue

 isActive = val" />
```
### 2. Using `modelValue` Instead of `defaultValue`
```vue

```
### 3. Not Providing a Setter for Computed Props
```ts
// ❌ Incorrect:
const isActive = computed(() => store.state.toggleState)
// ✅ Correct:
const isActive = computed({
get: () => store.state.toggleState,
set: val => store.commit('setToggleState', val)
})
```
