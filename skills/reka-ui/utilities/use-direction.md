# useDirection

Access the current text direction from ConfigProvider.

## Usage

```ts
import { useDirection } from 'reka-ui'

// With <ConfigProvider dir="rtl">
const dir = useDirection() // "rtl"

// With explicit override
const dir = useDirection('ltr') // "ltr"
```
