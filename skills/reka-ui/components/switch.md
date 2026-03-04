# Switch

A control that allows the user to toggle between on and off.

[switch docs](https://reka-ui.com/docs/components/switch)

## Anatomy

```vue
<script setup>
import { SwitchRoot, SwitchThumb } from 'reka-ui'
</script>

<template>
  <SwitchRoot>
    <SwitchThumb />
  </SwitchRoot>
</template>
```

## API Reference

### Root
Contains all switch parts. Renders an input for form usage.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| as | `'button'` | `AsTag \| Component` | Render element |
| modelValue | - | `boolean \| null` | Controlled state (v-model) |
| defaultValue | - | `boolean` | Default state |
| disabled | - | `boolean` | Prevents interaction |
| name | - | `string` | Form field name |
| required | - | `boolean` | Form required |
| value | `'on'` | `string` | Form submit value |

| Emit | Payload |
|------|---------|
| update:modelValue | `[payload: boolean]` |

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"checked" \| "unchecked"` |
| [data-disabled] | Present when disabled |

### Thumb
Visual indicator for the switch state.

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"checked" \| "unchecked"` |
| [data-disabled] | Present when disabled |

## Accessibility
Adheres to the switch role requirements.

| Key | Description |
|-----|-------------|
| Space | Toggles state |
| Enter | Toggles state |
