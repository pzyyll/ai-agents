# Time Range Field

An input for selecting a range of times with segmented input.

[time-range-field docs](https://reka-ui.com/docs/components/time-range-field)

## Prerequisites
Requires `@internationalized/date` package.
```sh
npm add @internationalized/date
```

## Anatomy

```vue
<script setup>
import { TimeRangeFieldInput, TimeRangeFieldRoot } from 'reka-ui'
</script>

<template>
  <TimeRangeFieldRoot>
    <TimeRangeFieldInput part="hour" type="start" />
    <TimeRangeFieldInput part="minute" type="start" />
    <TimeRangeFieldInput part="hour" type="end" />
    <TimeRangeFieldInput part="minute" type="end" />
  </TimeRangeFieldRoot>
</template>
```

## API Reference

### Root
Contains all time range field parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| modelValue | - | `TimeRange` | Controlled value (v-model) |
| defaultValue | - | `TimeRange` | Default value |
| defaultPlaceholder | - | `TimeValue` | Default placeholder |
| disabled | `false` | `boolean` | Prevents interaction |
| readonly | `false` | `boolean` | Prevents editing |
| granularity | - | `'hour' \| 'minute' \| 'second'` | Time precision |
| hourCycle | - | `12 \| 24` | Hour format |
| locale | `'en'` | `string` | Locale |

| Emit | Payload |
|------|---------|
| update:modelValue | `[date: TimeRange]` |
| update:placeholder | `[date: TimeValue]` |

| Slot Payload | Type |
|--------------|------|
| modelValue | `TimeRange \| undefined` |
| segments | `{ start: { part: SegmentPart; value: string; }[]; end: { part: SegmentPart; value: string; }[]; }` |
| isInvalid | `boolean` |

### Input
Individual time segment input.

| Prop | Default | Type |
|------|---------|------|
| part | - | `SegmentPart` |
| type | - | `'start' \| 'end'` |
