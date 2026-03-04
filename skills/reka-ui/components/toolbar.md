# Toolbar

A container for grouping a set of controls, such as buttons and toggle groups.

[toolbar docs](https://reka-ui.com/docs/components/toolbar)

## Anatomy

```vue
<script setup>
import { ToolbarButton, ToolbarLink, ToolbarRoot, ToolbarSeparator, ToolbarToggleGroup, ToolbarToggleItem } from 'reka-ui'
</script>

<template>
  <ToolbarRoot>
    <ToolbarButton />
    <ToolbarSeparator />
    <ToolbarLink />
    <ToolbarToggleGroup>
      <ToolbarToggleItem />
    </ToolbarToggleGroup>
  </ToolbarRoot>
</template>
```

## API Reference

### Root
Contains all toolbar parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| orientation | `'horizontal'` | `'horizontal' \| 'vertical'` | Toolbar orientation |
| dir | - | `'ltr' \| 'rtl'` | Reading direction |
| loop | `true` | `boolean` | Loop focus navigation |

| Data Attribute | Value |
|----------------|-------|
| [data-orientation] | `"vertical" \| "horizontal"` |

### Button
A toolbar button.

### Separator
Visual separator between toolbar items.

### Link
A toolbar link.

### ToggleGroup
A toggle group within the toolbar. Same API as ToggleGroup.Root.

### ToggleItem
A toggle item within a toolbar toggle group. Same API as ToggleGroup.Item.

## Accessibility

| Key | Description |
|-----|-------------|
| Tab | Moves focus to the toolbar, then through items |
| Arrow keys | Navigate between items |
| Home | First item |
| End | Last item |
