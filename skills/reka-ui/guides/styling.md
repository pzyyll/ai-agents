# Styling

Reka UI are unstyled and compatible with any styling solution giving you complete control over styling.

[styling docs](https://reka-ui.com/docs/guides/styling)

## Styling Overview

### Functional Styles
You are in control of all aspects of styling, including functional styles. For example, a Dialog Overlay won't cover the viewport by default - you must add those styles.

### Classes
All components accept `class` attributes, passed through to the DOM element.

### Teleported Elements
Some components (Dialog, Popover, etc.) use Vue's `<Teleport>` to render in `document.body`. Style teleported content with global CSS or target data attributes.

### Data Attributes
Stateful components include a `data-state` attribute for CSS targeting:

```css
.AccordionContent[data-state="open"] {
  animation: slideDown 300ms ease-out;
}
.AccordionContent[data-state="closed"] {
  animation: slideUp 300ms ease-out;
}
```

### CSS Variables
Some components expose CSS variables for sizing animations:
- `--reka-accordion-content-width`
- `--reka-accordion-content-height`
- `--reka-collapsible-content-width`
- `--reka-collapsible-content-height`

## Styling with Tailwind CSS
Use class-based styling directly on Reka UI components:

```vue
<TooltipContent class="bg-white rounded-md shadow-lg p-4">
  Tooltip content
</TooltipContent>
```

## Extending a Primitive
Wrap primitives with your own styling by forwarding props:

```vue
<script setup lang="ts">
import { AccordionItem, type AccordionItemProps } from "reka-ui";
interface Props extends AccordionItemProps {
  foo: string;
}
defineProps<Props>();
</script>

<template>
  <AccordionItem v-bind="$props"><slot /></AccordionItem>
</template>
```

## Summary
Reka UI encapsulates accessibility and complex functionality while ensuring you retain complete control over styling. Stateful components include `data-state` attributes for CSS targeting.
