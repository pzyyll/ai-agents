---
name: reka-ui
description: Reka UI component library reference for Vue 3. Use this when building accessible, unstyled UI components with Reka UI primitives.
---

# Reka UI

Reka UI is an open-source Vue 3 component library providing unstyled, accessible primitive components. Built on WAI-ARIA standards with full keyboard navigation and focus management.

- [Reka UI docs](https://reka-ui.com)
- [GitHub](https://github.com/unovue/reka-ui)

## When to use this skill

Use this skill when:

- Building Vue 3 UI components with Reka UI primitives
- Need reference for Reka UI component APIs (props, events, slots)
- Implementing accessible UI patterns (dialogs, menus, selects, etc.)
- Working with date/time components using `@internationalized/date`
- Composing custom components with `asChild` prop
- Styling Reka UI components with Tailwind CSS or custom CSS
- Wrapping Reka UI primitives with forwarded props/emits
- Migrating from Radix Vue to Reka UI

## Installation

[install guide](https://reka-ui.com/docs/overview/installation)

```sh
npm add reka-ui
```

### Nuxt Module

```ts
export default defineNuxtConfig({
  modules: ['reka-ui/nuxt'],
})
```

### unplugin-vue-components

```ts
import Components from 'unplugin-vue-components/vite'
import RekaResolver from 'reka-ui/resolver'

export default defineConfig({
  plugins: [
    vue(),
    Components({
      dts: true,
      resolvers: [RekaResolver()],
    }),
  ],
})
```

### Date Components Prerequisite

Date and time components require `@internationalized/date`:

```sh
npm add @internationalized/date
```

## Usage Rules

1. Reka UI components are **unstyled** - you control all styling (CSS, Tailwind, etc.)
2. Import components individually: `import { DialogRoot, DialogContent } from 'reka-ui'`
3. Components follow a **compound pattern**: Root > Trigger > Content (with sub-parts)
4. Use `v-model` for controlled state, `defaultValue` for uncontrolled
5. Use the `asChild` prop to compose primitives onto your own elements
6. Stateful components expose `data-state` attributes for CSS targeting
7. Use `forceMount` prop when animating with JS animation libraries
8. Wrap app in `ConfigProvider` for global RTL/locale/scroll settings
9. Use `TooltipProvider` and `ToastProvider` at app root level
10. Date components use `DateValue` objects from `@internationalized/date`, not native Date

## Key Concepts

### Composition with asChild

Merge primitive behavior onto your own elements:

```vue
<DialogTrigger asChild>
  <MyButton>Open</MyButton>
</DialogTrigger>
```

### Data Attributes for Styling

```css
.AccordionContent[data-state="open"] {
  animation: slideDown 300ms ease-out;
}
.AccordionContent[data-state="closed"] {
  animation: slideUp 300ms ease-out;
}
```

### CSS Variables for Animation

Some components expose sizing CSS variables:
- `--reka-accordion-content-width` / `--reka-accordion-content-height`
- `--reka-collapsible-content-width` / `--reka-collapsible-content-height`

### Controlled vs Uncontrolled

```vue
<!-- Uncontrolled -->
<AccordionRoot defaultValue="item-1">

<!-- Controlled -->
<AccordionRoot v-model="activeItem">
```

### Animation with Vue Transition

```vue
<DialogContent forceMount>
  <Transition name="fade">
    <div v-if="open">Content</div>
  </Transition>
</DialogContent>
```

---

## Component Index

**Load component docs on-demand from `components/` folder.**

### Form Components

| Component | File | Description |
|-----------|------|-------------|
| Autocomplete | `autocomplete.md` | Input with suggestions, value is text itself |
| Checkbox | `checkbox.md` | Toggle between checked and unchecked |
| Combobox | `combobox.md` | Searchable select with keyboard support |
| Editable | `editable.md` | Inline editable text |
| Label | `label.md` | Accessible label for controls |
| Listbox | `listbox.md` | Selectable list of items |
| Number Field | `number-field.md` | Numeric input with increment/decrement |
| Pin Input | `pin-input.md` | Sequence of one-character inputs |
| Radio Group | `radio-group.md` | Single selection from a group |
| Select | `select.md` | Dropdown selection list |
| Slider | `slider.md` | Range input with draggable thumb |
| Switch | `switch.md` | Toggle between on and off |
| Tags Input | `tags-input.md` | Input for multiple tag values |
| Toggle | `toggle.md` | Two-state on/off button |
| Toggle Group | `toggle-group.md` | Set of toggle buttons |

### Color Components

| Component | File | Description |
|-----------|------|-------------|
| Color Area | `color-area.md` | 2D area for color selection |
| Color Field | `color-field.md` | Input for color values |
| Color Slider | `color-slider.md` | Slider for color channels |
| Color Swatch | `color-swatch.md` | Color preview display |
| Color Swatch Picker | `color-swatch-picker.md` | Picker with color swatches |

### Date & Time Components

| Component | File | Description |
|-----------|------|-------------|
| Calendar | `calendar.md` | Date calendar view |
| Date Field | `date-field.md` | Segmented date input |
| Date Picker | `date-picker.md` | Date input with calendar popup |
| Date Range Field | `date-range-field.md` | Segmented date range input |
| Date Range Picker | `date-range-picker.md` | Date range with calendar popup |
| Range Calendar | `range-calendar.md` | Calendar for date ranges |
| Time Field | `time-field.md` | Segmented time input |
| Time Range Field | `time-range-field.md` | Segmented time range input |
| Month Picker | `month-picker.md` | Calendar for month selection |
| Month Range Picker | `month-range-picker.md` | Calendar for month ranges |
| Year Picker | `year-picker.md` | Calendar for year selection |
| Year Range Picker | `year-range-picker.md` | Calendar for year ranges |

### General Components

| Component | File | Description |
|-----------|------|-------------|
| Accordion | `accordion.md` | Expandable/collapsible content sections |
| Alert Dialog | `alert-dialog.md` | Modal dialog requiring a response |
| Aspect Ratio | `aspect-ratio.md` | Content within a desired ratio |
| Avatar | `avatar.md` | Image with fallback for user display |
| Collapsible | `collapsible.md` | Expandable/collapsible panel |
| Context Menu | `context-menu.md` | Right-click menu |
| Dialog | `dialog.md` | Modal window overlay |
| Dropdown Menu | `dropdown-menu.md` | Menu triggered by a button |
| Hover Card | `hover-card.md` | Content preview on hover |
| Menubar | `menubar.md` | Horizontal menu bar |
| Navigation Menu | `navigation-menu.md` | Site navigation links |
| Pagination | `pagination.md` | Page navigation controls |
| Popover | `popover.md` | Content popup triggered by button |
| Progress | `progress.md` | Progress indicator bar |
| Scroll Area | `scroll-area.md` | Custom cross-browser scroll |
| Separator | `separator.md` | Visual/semantic content divider |
| Splitter | `splitter.md` | Resizable panel layout |
| Stepper | `stepper.md` | Multi-step process indicator |
| Tabs | `tabs.md` | Tabbed content panels |
| Toast | `toast.md` | Temporary notification messages |
| Toolbar | `toolbar.md` | Grouped controls container |
| Tooltip | `tooltip.md` | Hover/focus information popup |
| Tree | `tree.md` | Hierarchical expandable list |

---

## Guides Index

**Load guide docs on-demand from `guides/` folder.**

| Guide | File | Description |
|-------|------|-------------|
| Introduction | `introduction.md` | Overview of Reka UI |
| Getting Started | `getting-started.md` | Quick start tutorial |
| Installation | `installation.md` | Installation methods |
| Accessibility | `accessibility.md` | WAI-ARIA compliance details |
| Styling | `styling.md` | CSS, Tailwind, and data attributes |
| Animation | `animation.md` | CSS, Vue Transition, and Motion Vue |
| Composition | `composition.md` | asChild prop and component composition |
| Controlled State | `controlled-state.md` | v-model vs defaultValue patterns |
| Dates | `dates.md` | Working with @internationalized/date |
| I18n | `i18n.md` | RTL and internationalization |
| SSR | `server-side-rendering.md` | Server-side rendering |
| Virtualization | `virtualization.md` | Large dataset rendering |
| Namespaced | `namespaced-components.md` | Namespaced component imports |
| Inject Context | `inject-context.md` | Context injection patterns |
| Migration | `migration.md` | Migrating from Radix Vue |
| Releases | `releases.md` | Release information |

---

## Utilities Index

**Load utility docs on-demand from `utilities/` folder.**

### Components

| Utility | File | Description |
|---------|------|-------------|
| ConfigProvider | `config-provider.md` | Global config (locale, dir, scroll) |
| FocusScope | `focus-scope.md` | Focus trapping |
| Presence | `presence.md` | Mount/unmount with transitions |
| Primitive | `primitive.md` | Base primitive component |
| RovingFocus | `roving-focus.md` | Roving tabindex focus management |
| Slot | `slot.md` | Prop merging onto child |
| VisuallyHidden | `visually-hidden.md` | Screen-reader-only content |

### Composables

| Composable | File | Description |
|------------|------|-------------|
| useId | `use-id.md` | Generate unique IDs (deprecated: use Vue 3.5+) |
| useDateFormatter | `use-date-formatter.md` | Locale-aware date formatting |
| useDirection | `use-direction.md` | Access current text direction |
| useLocale | `use-locale.md` | Access current locale |
| useEmitAsProps | `use-emit-as-props.md` | Convert emits to prop handlers |
| useFilter | `use-filter.md` | Locale-aware string filtering |
| useForwardExpose | `use-forward-expose.md` | Forward template ref $el |
| useForwardProps | `use-forward-props.md` | Forward props without boolean casting |
| useForwardPropsEmits | `use-forward-props-emits.md` | Combined props + emits forwarding |
