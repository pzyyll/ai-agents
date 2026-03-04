# Toggle Group

A set of two-state buttons that can be toggled on or off.

[toggle-group docs](https://reka-ui.com/docs/components/toggle-group)

## Anatomy

```vue
<script setup>
import { ToggleGroupItem, ToggleGroupRoot } from 'reka-ui'
</script>

<template>
  <ToggleGroupRoot>
    <ToggleGroupItem />
  </ToggleGroupRoot>
</template>
```

## API Reference

### Root
Contains all toggle group parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| type | - | `'single' \| 'multiple'` | Single or multi-select mode |
| modelValue | - | `AcceptableValue \| AcceptableValue[]` | Controlled value (v-model) |
| defaultValue | - | `AcceptableValue \| AcceptableValue[]` | Default value |
| disabled | `false` | `boolean` | Prevents interaction |
| orientation | `'horizontal'` | `'horizontal' \| 'vertical'` | Layout orientation |
| rovingFocus | `true` | `boolean` | Use roving tab focus |
| loop | `true` | `boolean` | Loop focus navigation |

| Emit | Payload |
|------|---------|
| update:modelValue | `[payload: AcceptableValue \| AcceptableValue[]]` |

| Data Attribute | Value |
|----------------|-------|
| [data-orientation] | `"vertical" \| "horizontal"` |

### Item
A toggle button within the group.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| value | - | `AcceptableValue` | Unique value for the item |
| disabled | - | `boolean` | Prevents interaction |

| Slot Payload | Type |
|--------------|------|
| modelValue | `boolean` |
| state | `'on' \| 'off'` |
| pressed | `boolean` |

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"on" \| "off"` |
| [data-disabled] | Present when disabled |
