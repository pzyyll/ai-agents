# Tags Input

A component for entering multiple tags/values.

[tags-input docs](https://reka-ui.com/docs/components/tags-input)

## Anatomy

```vue
<script setup>
import { TagsInputClear, TagsInputInput, TagsInputItem, TagsInputItemDelete, TagsInputItemText, TagsInputRoot } from 'reka-ui'
</script>

<template>
  <TagsInputRoot>
    <TagsInputItem>
      <TagsInputItemText />
      <TagsInputItemDelete />
    </TagsInputItem>
    <TagsInputInput />
    <TagsInputClear />
  </TagsInputRoot>
</template>
```

## API Reference

### Root
Contains all tags input parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| modelValue | - | `AcceptableInputValue[]` | Tags array (v-model) |
| addOnPaste | `false` | `boolean` | Add tags when pasting |
| addOnTab | `false` | `boolean` | Add tag on Tab key |
| addOnBlur | `false` | `boolean` | Add tag on blur |
| delimiter | `','` | `string` | Character to split tags |
| duplicate | `false` | `boolean` | Allow duplicate tags |
| max | `0` | `number` | Maximum tags (0=unlimited) |
| disabled | `false` | `boolean` | Prevents interaction |
| name | - | `string` | Form field name |

| Emit | Payload |
|------|---------|
| update:modelValue | `[payload: AcceptableInputValue[]]` |

| Data Attribute | Value |
|----------------|-------|
| [data-disabled] | Present when disabled |
| [data-focused] | Present when focused |
| [data-invalid] | Present when invalid |

### Item
Tag container.

| Prop | Default | Type |
|------|---------|------|
| value | - | `string \| number \| bigint \| Record` |

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"active" \| "inactive"` |
| [data-disabled] | Present when disabled |

### ItemText
Textual part of the tag (important for accessibility).

### ItemDelete
Button to delete the associated tag.

### Input
Text input for entering new tags.

### Clear
Button to clear all tags.
