# useForwardExpose

Forward template ref `$el` for non-single-root components, and extend missing exposed props.

## Usage

```vue
<script setup lang="ts">
import { useForwardExpose } from 'reka-ui'

const { forwardRef } = useForwardExpose()
</script>

<template>
  <span>
    <div :ref="forwardRef">
      ...
    </div>
  </span>
</template>
```
