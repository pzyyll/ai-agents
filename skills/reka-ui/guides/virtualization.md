# Virtualization

Efficiently render large datasets with Reka UI, powered by @tanstack/vue-virtual.

[virtualization docs](https://reka-ui.com/docs/guides/virtualization)

## What is Virtualization?
Only renders items currently visible in the viewport, improving performance and reducing memory for large lists.

## Benefits
- Improved Performance: Render thousands of items without lag
- Reduced Memory Usage: Only mount DOM nodes for visible items
- Better User Experience: Fast initial load times

## Supported Components
- Combobox (ComboboxVirtualizer)
- Listbox (ListboxVirtualizer)
- Tree (TreeVirtualizer)

## Customization Options

| Prop | Description |
|------|-------------|
| estimateSize | Set estimated item height for static or dynamic items |
| overscan | Number of items rendered outside visible area |
| textContent | Text content for type-ahead accessibility |

## Usage Requirements
1. A fixed `height`/`max-height` wrapping container
2. Consistent item height with appropriate `estimateSize`
3. Set `textContent` for type-ahead accessibility

## Example

```vue
<script setup>
import { ComboboxContent, ComboboxItem, ComboboxRoot, ComboboxViewport, ComboboxVirtualizer } from 'reka-ui'

const items = [/* large array */]
</script>

<template>
  <ComboboxRoot>
    ...
    <ComboboxContent>
      <ComboboxViewport class="max-h-80 overflow-y-auto">
        <ComboboxVirtualizer
          v-slot="{ option }"
          :options="items"
          :estimate-size="25"
          :text-content="(opt) => opt.label"
        >
          <ComboboxItem :value="option">
            {{ option.label }}
          </ComboboxItem>
        </ComboboxVirtualizer>
      </ComboboxViewport>
    </ComboboxContent>
  </ComboboxRoot>
</template>
```
