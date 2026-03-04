# Combobox
## Features
## Installation
Install the component from your command line.
## Anatomy
Import all parts and piece them together.
```vue

```
## API Reference
### Root
Contains all the parts of a Combobox
### Anchor
Used as an anchor if you set `ComboboxContent`'s position to `popper`.
### Input
The input component to search through the combobox items.
### Trigger
The button that toggles the Combobox Content.
### Cancel
The button that clears the search term.
### Empty
Shown when none of the items match the query.
### Portal
When used, portals the content part into the `body`.
You need to set `position="popper"` for `ComboboxContent` to make sure the position was automatically computed similar to `Popover` or `DropdownMenu`.
### Content
The component that pops out when the combobox is open.
### Viewport
The scrolling viewport that contains all of the items.
### Item
The component that contains the combobox items.
### ItemIndicator
Renders when the item is selected. You can style this element directly, or you can use it as a wrapper to put an icon into, or both.
### Group
Used to group multiple items. use in conjunction with `ComboboxLabel` to ensure good accessibility via automatic labelling.
### Label
Used to render the label of a group. It won't be focusable using arrow keys.
### Separator
Used to visually separate items in the Combobox
### Arrow
An optional arrow element to render alongside the content. This can be used to help visually link the trigger with the `ComboboxContent`. Must be rendered inside `ComboboxContent`. Only available when `position` is set to `popper`.
### Virtualizer
Virtual container to achieve list virtualization.
Combobox items \\must\\ be filtered manually before passing them over to the virtualizer. See example below.
See the virtualization guide for more general info on virtualization.
## Examples
### Binding objects as values
Unlike native HTML form controls which only allow you to provide strings as values, `reka-ui` supports binding complex objects as well.
Make sure to set the `displayValue` prop to set the input value on item selection.
```vue line=12,17,23

{{ person.name }}
```
### Selecting multiple values
The `Combobox` component allows you to select multiple values. You can enable this by providing an array of values instead of a single value.
```vue line=12,17-18
…
```
### Custom filtering
Internally, `ComboboxRoot` will filter the item based on the rendered text.
However, you may also provide your own custom filtering logic together with setting `ignoreFilter="true"`.
```vue line=15,16,22,28

{{ person.name }}
```
### Custom label
By default the `Combobox` will use the input contents as the label for screenreaders. If you'd like more control over what is announced to assistive technologies, use the Label component.
```vue line=8,10

…
```
### With disabled items
You can add special styles to disabled items via the `data-disabled` attribute.
```vue line=19

…
```
```css line=2
/\ styles.css \/
.ComboboxItem[data-disabled] {
color: "gainsboro";
}
```
### With separators
Use the `Separator` part to add a separator between items.
```vue line=21

…
…
…

…
…
…
```
### With grouped items
Use the `Group` and `Label` parts to group items in a section.
```vue line=19,20,24

Label
…
…
…
```
### With complex items
You can use custom content in your items.
```vue line=21

Adolfo Hess
…
```
### Prevent select behavior
By default, selecting `ComboboxItem` would close the content, and update the `modelValue` with the provided value.
You can prevent this behavior by preventing default `@select.prevent`.
```vue line=11

Item A
…
```
### Virtualized combobox with working filtering
Combobox items \\must\\ be filtered manually before passing them over to the virtualizer.
See the virtualization guide for more general info on virtualization.
```vue line=9-10,17,19-28

{{ option.name }}
```
## Accessibility
Adheres to the Combobox WAI-ARIA design pattern.
See the W3C Combobox Autocomplete List example for more information.
### Keyboard Interactions
## Custom APIs
Create your own API by abstracting the primitive parts into your own component.
### Command Menu
Combobox can be use to build your own Command Menu.
#### Usage
```vue

Item 1

Item 2

Item 3
```
#### Implementation
```ts
// your-command.ts
export { default as Command } from 'Command.vue'
export { default as CommandItem } from 'CommandItem.vue'
```
```vue

```
```vue

```
