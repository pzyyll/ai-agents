# useId

Generate unique IDs for components.

**Deprecated**: Vue 3.5 released an official `useId`. Use Vue's built-in version instead.

## Usage

```ts
import { useId } from 'reka-ui'

const buttonId = useId() // "reka-1"
const customId = useId('test-id') // "test-id"
```
