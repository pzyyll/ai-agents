# useDateFormatter

Creates a wrapper around DateFormatter for consistent date formatting.

## Usage

```vue
<script setup lang="ts">
import type { DateValue } from '@internationalized/date'
import { CalendarDate, getLocalTimeZone } from '@internationalized/date'
import { toDate, useDateFormatter } from 'reka-ui'
import { ref } from 'vue'

const value = ref(new CalendarDate(1995, 8, 18))
const formatter = useDateFormatter('en')
</script>

<template>
  <span>
    {{ formatter.custom(value.toDate(getLocalTimeZone()), { month: 'short' }) }}
  </span>
</template>
```
