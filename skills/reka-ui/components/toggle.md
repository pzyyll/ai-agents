# Toggle

A two-state button that can be either on or off.

[toggle docs](https://reka-ui.com/docs/components/toggle)

## Anatomy

```vue
<script setup>
import { Toggle } from 'reka-ui'
</script>

<template>
  <Toggle />
</template>
```

## API Reference

### Root
The toggle button.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| as | `'button'` | `AsTag \| Component` | Render element |
| modelValue | - | `boolean \| null` | Controlled pressed state (v-model) |
| defaultValue | - | `boolean` | Default pressed state |
| disabled | `false` | `boolean` | Prevents interaction |
| name | - | `string` | Form field name |
| required | - | `boolean` | Form required |

| Emit | Payload |
|------|---------|
| update:modelValue | `[value: boolean]` |

| Slot Payload | Type |
|--------------|------|
| modelValue | `boolean` |
| state | `'on' \| 'off'` |
| pressed | `boolean` |
| disabled | `boolean` |

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"on" \| "off"` |
| [data-disabled] | Present when disabled |

## Accessibility

| Key | Description |
|-----|-------------|
| Space | Toggles state |
| Enter | Toggles state |
