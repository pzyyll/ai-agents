# Slot
How is this component different from Vue native slot?
A: The biggest different is how it handles the `attributes` assigned to it.
Native slot treat any binded value as Scoped Slots, where the values will be exposed to the parent template and be consumed.
But Reka UI's slot behave differently, it would merge all the assigned attributes onto it's immediate child.
## Example
Say we want to assign an `id` attribute to whatever component/element that was rendered, but Native slot will convert it into a scoped slot, and you will need to assign that id manually.
```vue

...
