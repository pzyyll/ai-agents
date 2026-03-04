# Visually Hidden

Hides content visually while keeping it accessible to screen readers.

[visually-hidden docs](https://reka-ui.com/docs/utilities/visually-hidden)

## Anatomy

```vue
<script setup lang="ts">
import { VisuallyHidden } from 'reka-ui'
</script>

<template>
  <button>
    <GearIcon />
    <VisuallyHidden>Settings</VisuallyHidden>
  </button>
</template>
```

## API Reference

### Root
Anything inside will be hidden visually but announced by screen readers.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| as | `'span'` | `string \| Component` | Render element |
| asChild | `false` | `boolean` | Merge onto child element |

## Accessibility
Useful as an alternative to `aria-label` or `aria-labelledby`.
