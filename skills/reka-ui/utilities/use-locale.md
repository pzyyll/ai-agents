# useLocale

Access the current locale from ConfigProvider.

## Usage

```ts
import { useLocale } from 'reka-ui'

// With <ConfigProvider locale="fr-FR">
const locale = useLocale() // "fr-FR"

// With explicit override
const locale = useLocale('en-US') // "en-US"
```
