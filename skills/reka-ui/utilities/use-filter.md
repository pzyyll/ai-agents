# useFilter

Locale-aware string filtering using `Intl.Collator`.

## Usage

```vue
<script setup>
import { ref, computed } from 'vue'
import { useFilter } from 'reka-ui'

const { contains } = useFilter()
const searchQuery = ref('')
const items = ref(['Apple', 'Banana', 'Cherry', 'Date'])

const filteredItems = computed(() =>
  items.value.filter(item => contains(item, searchQuery.value))
)
</script>
```

## Methods
- `contains(string, substring)` - Check if string contains substring
- `startsWith(string, substring)` - Check if string starts with substring
- `endsWith(string, substring)` - Check if string ends with substring

## Options
Accepts `Intl.CollatorOptions` for customization. See [MDN Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator).
