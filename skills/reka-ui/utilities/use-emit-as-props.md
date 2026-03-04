# useEmitAsProps

Convert component emits into an object of handlers for forwarding via `v-bind`.

## Usage

```vue
<script setup lang="ts">
import { useEmitAsProps } from 'reka-ui'

const emits = defineEmits<CompEmitType>()
const emitsAsProps = useEmitAsProps(emits)
</script>

<template>
  <Comp v-bind="emitsAsProps">
    ...
  </Comp>
</template>
```
