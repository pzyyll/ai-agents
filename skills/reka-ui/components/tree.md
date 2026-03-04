# Tree

A hierarchical list of items where sub-items can be expanded or collapsed.

[tree docs](https://reka-ui.com/docs/components/tree)

## Anatomy

```vue
<script setup lang="ts">
import { TreeItem, TreeRoot } from 'reka-ui'
</script>

<template>
  <TreeRoot
    v-slot="{ flattenItems }"
    :items="items"
  >
    <TreeItem
      v-for="item in flattenItems"
      :key="item._id"
      v-bind="item.bind"
      v-slot="{ handleSelect, isSelected, isIndeterminate }"
    >
      {{ item.value.title }}
    </TreeItem>
  </TreeRoot>
</template>
```

## API Reference

### Root
Contains all tree parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| items | - | `Record[]` | Tree data items |
| modelValue | - | `Record \| Record[]` | Selected item(s) (v-model) |
| expanded | - | `string[]` | Expanded item keys (v-model:expanded) |
| multiple | `false` | `boolean` | Allow multiple selection |
| selectionBehavior | `'toggle'` | `'replace' \| 'toggle'` | Selection mode |
| propagateSelect | `false` | `boolean` | Propagate select to children |
| getKey | - | `(item: Record) => string` | Key extractor |
| getChildren | - | `(item: Record) => Record[]` | Children extractor |

| Emit | Payload |
|------|---------|
| update:modelValue | `[val: Record \| Record[]]` |
| update:expanded | `[val: string[]]` |

| Slot Payload | Type |
|--------------|------|
| flattenItems | `FlattenedItem[]` |
| modelValue | `Record \| Record[]` |
| expanded | `string[]` |

### Item
Individual tree item.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| value | - | `Record` | Item data |
| level | - | `number` | Depth level |

| Emit | Payload |
|------|---------|
| select | `[event: SelectEvent]` |
| toggle | `[event: ToggleEvent]` |

| Slot Payload | Type |
|--------------|------|
| isExpanded | `boolean` |
| isSelected | `boolean` |
| isIndeterminate | `boolean \| undefined` |
| handleToggle | `() => void` |
| handleSelect | `() => void` |

| Data Attribute | Value |
|----------------|-------|
| [data-indent] | Number (depth level) |
| [data-expanded] | Present when expanded |
| [data-selected] | Present when selected |

### Virtualizer
Virtual container for large tree rendering.

| Prop | Default | Type |
|------|---------|------|
| estimateSize | - | `number` |
| textContent | - | `(item) => string` |
