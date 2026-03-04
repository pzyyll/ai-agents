# Year Picker

Presents a calendar view tailored for selecting years.

[year-picker docs](https://reka-ui.com/docs/components/year-picker)

## Prerequisites
Requires `@internationalized/date` package.

## Anatomy

```vue
<script setup>
import { YearPickerCell, YearPickerCellTrigger, YearPickerGrid, YearPickerGridBody, YearPickerGridHead, YearPickerGridRow, YearPickerHeadCell, YearPickerHeader, YearPickerHeading, YearPickerNext, YearPickerPrev, YearPickerRoot } from 'reka-ui'
</script>
```

## API Reference

### Root
Contains all year picker parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| modelValue | - | `DateValue` | Selected value (v-model) |
| defaultValue | - | `DateValue` | Default value |
| defaultPlaceholder | - | `DateValue` | Default placeholder |
| disabled | `false` | `boolean` | Prevents interaction |
| readonly | `false` | `boolean` | Prevents editing |
| calendarLabel | - | `string` | Accessible label |
| locale | `'en'` | `string` | Locale |
| dir | - | `'ltr' \| 'rtl'` | Reading direction |
| minValue | - | `DateValue` | Minimum selectable date |
| maxValue | - | `DateValue` | Maximum selectable date |
| multiple | `false` | `boolean` | Allow multiple selection |
| isYearDisabled | - | `Matcher` | Custom disabled check |
| isYearUnavailable | - | `Matcher` | Custom unavailable check |

| Emit | Payload |
|------|---------|
| update:modelValue | `[date: DateValue]` |
| update:placeholder | `[date: DateValue]` |

| Slot Payload | Type |
|--------------|------|
| date | `DateValue` |
| grid | `Grid` |
| locale | `string` |
| modelValue | `DateValue \| DateValue[] \| undefined` |

### CellTrigger
Interactive year cell.

| Data Attribute | Value |
|----------------|-------|
| [data-selected] | Present when selected |
| [data-disabled] | Present when disabled |
| [data-value] | ISO string date value |
