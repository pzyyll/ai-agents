# Tooltip

A popup that displays information related to an element when it receives keyboard focus or the mouse hovers over it.

[tooltip docs](https://reka-ui.com/docs/components/tooltip)

## Anatomy

```vue
<script setup lang="ts">
import { TooltipArrow, TooltipContent, TooltipPortal, TooltipProvider, TooltipRoot, TooltipTrigger } from 'reka-ui'
</script>

<template>
  <TooltipProvider>
    <TooltipRoot>
      <TooltipTrigger />
      <TooltipPortal>
        <TooltipContent>
          <TooltipArrow />
        </TooltipContent>
      </TooltipPortal>
    </TooltipRoot>
  </TooltipProvider>
</template>
```

## API Reference

### Provider
Wraps your app to provide global tooltip settings.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| delayDuration | `700` | `number` | Delay before tooltip opens (ms) |
| skipDelayDuration | `300` | `number` | Skip delay when moving between tooltips (ms) |
| disableHoverableContent | `false` | `boolean` | Close when pointer leaves trigger |
| disableClosingTrigger | - | `boolean` | Don't close on trigger click |
| disabled | - | `boolean` | Disable all tooltips |

### Root
Contains all tooltip parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| open | - | `boolean` | Controlled open state (v-model:open) |
| defaultOpen | `false` | `boolean` | Default open state |
| delayDuration | - | `number` | Override provider delay |

| Emit | Payload |
|------|---------|
| update:open | `[value: boolean]` |

### Trigger
Button that opens the tooltip. Content positions against this.

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"closed" \| "delayed-open" \| "instant-open"` |

### Portal
Portals content into the body.

### Content
The tooltip popup content.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| side | `'top'` | `'top' \| 'right' \| 'bottom' \| 'left'` | Preferred side |
| sideOffset | `0` | `number` | Distance from trigger |
| align | `'center'` | `'start' \| 'center' \| 'end'` | Alignment relative to trigger |
| alignOffset | `0` | `number` | Alignment offset |
| avoidCollisions | `true` | `boolean` | Flip to avoid viewport overflow |
| forceMount | - | `boolean` | Force mount for animations |

### Arrow
Optional arrow pointing to the trigger.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| width | `10` | `number` | Arrow width in px |
| height | `5` | `number` | Arrow height in px |
