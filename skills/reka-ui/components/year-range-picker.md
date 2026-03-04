# Year Range Picker

Presents a calendar view for selecting a range of years.

[year-range-picker docs](https://reka-ui.com/docs/components/year-range-picker)

## Prerequisites
Requires `@internationalized/date` package.

## API Reference

### Root
Contains all year range picker parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| modelValue | - | `DateRange` | Selected range (v-model) |
| defaultValue | `{ start: undefined, end: undefined }` | `DateRange` | Default range |
| defaultPlaceholder | - | `DateValue` | Default placeholder |
| disabled | `false` | `boolean` | Prevents interaction |
| readonly | `false` | `boolean` | Prevents editing |
| allowNonContiguousRanges | `false` | `boolean` | Allow non-contiguous ranges |
| calendarLabel | - | `string` | Accessible label |
| locale | `'en'` | `string` | Locale |
| minValue | - | `DateValue` | Minimum date |
| maxValue | - | `DateValue` | Maximum date |

| Emit | Payload |
|------|---------|
| update:modelValue | `[date: DateRange]` |
| update:placeholder | `[date: DateValue]` |
| update:startValue | `[date: DateValue]` |

| Slot Payload | Type |
|--------------|------|
| date | `DateValue` |
| grid | `Grid` |
| locale | `string` |
| modelValue | `DateRange` |
