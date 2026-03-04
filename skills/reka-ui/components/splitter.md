# Splitter

A component that divides a layout into resizable panels.

[splitter docs](https://reka-ui.com/docs/components/splitter)

## Features
- Supports horizontal and vertical orientations
- Collapsible panels
- Keyboard-accessible resize handles
- Auto-save layout via localStorage

## Anatomy

```vue
<script setup>
import { SplitterGroup, SplitterPanel, SplitterResizeHandle } from 'reka-ui'
</script>

<template>
  <SplitterGroup direction="horizontal">
    <SplitterPanel :default-size="50" />
    <SplitterResizeHandle />
    <SplitterPanel :default-size="50" />
  </SplitterGroup>
</template>
```

## API Reference

### Group (Root)
Contains all splitter panels and resize handles.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| direction | - | `'horizontal' \| 'vertical'` | Orientation of the splitter |
| autoSaveId | `null` | `string \| null` | Unique id for auto-saving layout via localStorage |
| keyboardResizeBy | `10` | `number \| null` | Step size for arrow key resize |
| storage | defaultStorage | `PanelGroupStorage` | Custom storage API |

| Emit | Payload | Description |
|------|---------|-------------|
| layout | `[val: number[]]` | Called when group layout changes |

### Panel
A resizable panel within the group.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| defaultSize | - | `number` | Initial panel size (1-100) |
| minSize | `10` | `number` | Minimum size (1-100) |
| maxSize | `100` | `number` | Maximum size (1-100) |
| collapsible | `false` | `boolean` | Whether panel can collapse |
| collapsedSize | - | `number` | Size when collapsed |
| order | - | `number` | Order within group (for conditional panels) |

| Emit | Payload |
|------|---------|
| collapse | `[]` |
| expand | `[]` |
| resize | `[size: number, prevSize: number]` |

### ResizeHandle
Handle between panels for resizing.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| tabindex | `0` | `number` | Tabindex for the handle |

| Emit | Payload |
|------|---------|
| dragging | `[isDragging: boolean]` |

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"drag" \| "hover" \| "inactive"` |
| [data-orientation] | `"vertical" \| "horizontal"` |

## Examples

### Collapsible
Use the `collapsible` prop to allow panel collapse when `minSize` is reached.
(`collapsedSize` and `minSize` props are required.)
