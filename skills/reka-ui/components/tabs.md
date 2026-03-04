# Tabs

A set of layered sections of content (tab panels) displayed one at a time.

[tabs docs](https://reka-ui.com/docs/components/tabs)

## Anatomy

```vue
<script setup>
import { TabsContent, TabsIndicator, TabsList, TabsRoot, TabsTrigger } from 'reka-ui'
</script>

<template>
  <TabsRoot>
    <TabsList>
      <TabsIndicator />
      <TabsTrigger />
    </TabsList>
    <TabsContent />
  </TabsRoot>
</template>
```

## API Reference

### Root
Contains all tab parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| modelValue | - | `StringOrNumber` | Active tab (v-model) |
| defaultValue | - | `StringOrNumber` | Default active tab |
| orientation | `'horizontal'` | `'horizontal' \| 'vertical'` | Tab layout orientation |
| activationMode | `'automatic'` | `'automatic' \| 'manual'` | Auto-activate on focus or manual click |
| unmountOnHide | `true` | `boolean` | Unmount inactive content from DOM |

| Emit | Payload |
|------|---------|
| update:modelValue | `[payload: StringOrNumber]` |

### List
Contains the tab triggers.

| Data Attribute | Value |
|----------------|-------|
| [data-orientation] | `"vertical" \| "horizontal"` |

### Trigger
Button that activates a tab panel.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| value | - | `StringOrNumber` | Associates trigger with content |
| disabled | `false` | `boolean` | Prevents interaction |

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"active" \| "inactive"` |
| [data-orientation] | `"vertical" \| "horizontal"` |

### Content
Panel content for a tab.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| value | - | `StringOrNumber` | Associates content with trigger |
| forceMount | - | `boolean` | Force mount for animation control |

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"active" \| "inactive"` |
| [data-orientation] | `"vertical" \| "horizontal"` |

### Indicator
Visual indicator for the active tab.
