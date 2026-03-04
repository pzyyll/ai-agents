# useForwardProps

Forward component props without Vue's boolean casting.

Useful when wrapping components where you need to preserve `undefined` vs `false` distinction.

## Usage

```vue
<script setup lang="ts">
import { useForwardProps } from 'reka-ui'

const props = defineProps<CompEmitProps>()
const forwarded = useForwardProps(props)
</script>

<template>
  <Comp v-bind="forwarded">
    ...
  </Comp>
</template>
```
