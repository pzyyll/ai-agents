# useForwardPropsEmits

Combines `useForwardProps` and `useEmitAsProps` into a single object for `v-bind`.

## Usage

```vue
<script setup lang="ts">
import { useForwardPropsEmits } from 'reka-ui'

const props = defineProps<CompEmitProps>()
const emits = defineEmits<CompEmitEmits>()
const forwarded = useForwardPropsEmits(props, emits)
</script>

<template>
  <Comp v-bind="forwarded">
    ...
  </Comp>
</template>
```
