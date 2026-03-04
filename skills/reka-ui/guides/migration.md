This guide provides step-by-step instructions for developers transitioning
their projects from Radix Vue to Reka UI.

# Migration - Radix Vue to Reka UI
## Installation
First and foremost, you need to install the latest `reka-ui`.
Congratulation! 🎉 Now that you've installed the above package, let's perform the migration! The first 2 steps are relatively simple. Just do a global search and replace for the following changes.
## Import Statement Changes
The primary change in imports is replacing `radix-vue` with `reka-ui`.
```vue
```
## Naming Convention Changes
CSS variable and data attributes names have been updated to use the `reka` prefix instead of `radix`.
```css
--radix-accordion-content-width: 300px; /\ [!code --] \/
--reka-accordion-content-width: 300px; /\ [!code ++] \/
[data-radix-collection-item] {} /\ [!code --] \/
[data-reka-collection-item] {} /\ [!code ++] \/
```
## Component Breaking Changes
### Combobox
\ Remove `filter-function` props - `Combobox` has been refactored and improved to support better custom filtering. Read more.
```vue
 
```
\ Replace `searchTerm` props of Root to Input's `v-model`
\ Move `displayValue` props from Root to Input
```vue
 

 
```
### Arrow
\ Improve arrow polygon - Change the svg polygon to allow better styling.
### Form component
\ Rename controlled state to `v-model` - Replace `v-model:checked`, `v-model:pressed` with more familiar API for form component.
```vue
 
 
```
\ Reposition `VisuallyHidden` - Previously, `VisuallyHidden` were positioned at the root node, causing style scoped to not be applied.
### Menu CheckboxItem
\ Similar to the changes in form component, the API for binding `CheckboxItem` has been changed from `v-model:checked` to `v-model`.
```vue
 
 
 
 
```
### Pagination
\ Required `itemsPerPage` prop - Instead of default `itemsPerPage` value, now it is required as to provide a more explicit hint about the page size.
```vue
 
```
### Calendar
\ Remove deprecated step prop - Use `prevPage/nextPage` props for greater control.
```vue
 
 
 
 
```
### Select
\ `SelectValue` no longer render teleported element - Previous implementation of `SelectValue` will render the selected `SelectItem` via teleporting fragment. This causes SSR flickering, and it is unnecessarily computation.
```vue
 
```
### Presence
To have better supports for SSR content, we also modify the logic around the usage of `forceMount` for component that utilize Presence:
\ `Accordion`
\ `Collapsible`
\ `Tabs`
\ `NavigationMenu`
`forceMount` will now render the component eventhough the state is inactive. You are now required to handle the visibility logic of the component manually.
```vue

…

…
```
## For Nuxt module users
If you are using Nuxt, you need to update your module import.
```ts
// nuxt.config.ts
export default defineNuxtConfig({
modules: [
'radix-vue/nuxt', // [!code --]
'reka-ui/nuxt', // [!code ++]
],
})
```
