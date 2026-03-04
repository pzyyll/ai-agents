# Time Field

An input field for entering time values with segmented input.

[time-field docs](https://reka-ui.com/docs/components/time-field)

## Prerequisites
Requires `@internationalized/date` package.
```sh
npm add @internationalized/date
```

## Anatomy

```vue
<script setup>
import { TimeFieldInput, TimeFieldRoot } from 'reka-ui'
</script>

<template>
  <TimeFieldRoot>
    <TimeFieldInput />
  </TimeFieldRoot>
</template>
```

## API Reference

### Root
Contains all time field parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| modelValue | - | `TimeValue` | Controlled value (v-model) |
| defaultValue | - | `TimeValue` | Default value |
| defaultPlaceholder | - | `TimeValue` | Default placeholder time |
| disabled | `false` | `boolean` | Prevents interaction |
| readonly | `false` | `boolean` | Prevents editing |
| granularity | - | `'hour' \| 'minute' \| 'second'` | Time precision |
| hourCycle | - | `12 \| 24` | 12 or 24 hour format |
| locale | `'en'` | `string` | Locale for formatting |
| hideTimeZone | `false` | `boolean` | Hide timezone segment |

| Emit | Payload |
|------|---------|
| update:modelValue | `[date: TimeValue]` |
| update:placeholder | `[date: TimeValue]` |

| Slot Payload | Type |
|--------------|------|
| modelValue | `TimeValue \| undefined` |
| segments | `{ part: SegmentPart; value: string; }[]` |
| isInvalid | `boolean` |

| Data Attribute | Value |
|----------------|-------|
| [data-readonly] | Present when readonly |
| [data-disabled] | Present when disabled |
| [data-invalid] | Present when invalid |

### Input
Contains the time field segments.

| Prop | Default | Type |
|------|---------|------|
| part | - | `SegmentPart` |
