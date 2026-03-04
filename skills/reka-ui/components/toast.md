# Toast

A succinct message displayed temporarily as a notification.

[toast docs](https://reka-ui.com/docs/components/toast)

## Anatomy

```vue
<script setup lang="ts">
import { ToastAction, ToastClose, ToastDescription, ToastProvider, ToastRoot, ToastTitle, ToastViewport } from 'reka-ui'
</script>

<template>
  <ToastProvider>
    <ToastRoot>
      <ToastTitle />
      <ToastDescription />
      <ToastAction />
      <ToastClose />
    </ToastRoot>
    <ToastViewport />
  </ToastProvider>
</template>
```

## API Reference

### Provider
Wraps your app to provide toast functionality.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| duration | `5000` | `number` | Default toast duration in ms |
| label | `'Notification'` | `string` | Accessible label for the region |
| swipeDirection | `'right'` | `'right' \| 'left' \| 'up' \| 'down'` | Swipe dismiss direction |
| swipeThreshold | `50` | `number` | Swipe distance to trigger dismiss |

### Root
The toast itself.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| open | - | `boolean` | Controlled open state (v-model:open) |
| defaultOpen | `true` | `boolean` | Default open state |
| duration | - | `number` | Override provider duration |
| type | `'foreground'` | `'foreground' \| 'background'` | Screen reader priority |
| forceMount | - | `boolean` | Force mount for animations |

| Emit | Payload |
|------|---------|
| update:open | `[value: boolean]` |
| escapeKeyDown | `[event: KeyboardEvent]` |
| swipeStart | `[event: SwipeEvent]` |
| swipeMove | `[event: SwipeEvent]` |
| swipeCancel | `[event: SwipeEvent]` |
| swipeEnd | `[event: SwipeEvent]` |

| Slot Payload | Type |
|--------------|------|
| open | `boolean` |
| remaining | `number` |
| duration | `number` |

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"open" \| "closed"` |
| [data-swipe] | `"start" \| "move" \| "cancel" \| "end"` |
| [data-swipe-direction] | `"up" \| "down" \| "left" \| "right"` |

### Title
Toast title text.

### Description
Toast description text.

### Action
A button for the toast action. Should include `altText` for accessibility.

### Close
Button to dismiss the toast.

### Viewport
The container where toasts are rendered.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| hotkey | `['F8']` | `string[]` | Keyboard shortcut to focus viewport |
