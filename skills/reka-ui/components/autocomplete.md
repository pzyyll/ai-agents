An input with suggestions that allows free-form text entry. Unlike Combobox,
the value is the input text itself rather than a selected item.

# Autocomplete
Alpha
## Features
## Installation
Install the component from your command line.
## Anatomy
Import all parts and piece them together.
```vue

```
## Autocomplete vs. Combobox
The Autocomplete component is similar to the Combobox but with a key difference:
| | Autocomplete | Combobox |
 --- 
| \\`modelValue`\\ | The input text (`string`) | The selected item (`AcceptableValue`) |
| \\Free-form text\\ | Yes — any text is valid | No — must select from the list |
| \\`multiple`\\ | Not supported | Supported |
| \\Input on blur\\ | Retains typed text by default | Resets to selected value by default |
| \\Item selection\\ | Fills the input with the item's text value | Sets `modelValue` to the item's value |
Use \\Autocomplete\\ when the user should be able to type anything with optional suggestions. Use \\Combobox\\ when the user must pick from a predefined set of options.
## API Reference
### Root
Contains all the parts of an Autocomplete.
### Anchor
Used as an anchor if you set `AutocompleteContent`'s position to `popper`.
### Input
The input component to search through the autocomplete items. Typing updates the `modelValue` directly.
### Trigger
The button that toggles the Autocomplete Content.
### Cancel
The button that clears the input text and resets the value.
### Empty
Shown when none of the items match the query.
### Portal
When used, portals the content part into the `body`.
You need to set `position="popper"` for `AutocompleteContent` to make sure the position was automatically computed similar to `Popover` or `DropdownMenu`.
### Content
The component that pops out when the autocomplete is open.
### Viewport
The scrolling viewport that contains all of the items.
### Item
The component that contains the autocomplete items. When selected, the item's string value fills the input.
### Group
Used to group multiple items. Use in conjunction with `AutocompleteLabel` to ensure good accessibility via automatic labelling.
### Label
Used to render the label of a group. It won't be focusable using arrow keys.
### Separator
Used to visually separate items in the Autocomplete.
### Arrow
An optional arrow element to render alongside the content. This can be used to help visually link the trigger with the `AutocompleteContent`. Must be rendered inside `AutocompleteContent`. Only available when `position` is set to `popper`.
### Virtualizer
Virtual container to achieve list virtualization.
See the virtualization guide for more general info on virtualization.
## Examples
### Basic usage
The `modelValue` is a string that reflects whatever the user types. Selecting an item fills the input with that item's text.
```vue

{{ fruit }}
```
### Hide menu when empty
Use the `hideWhenEmpty` prop on `AutocompleteContent` to hide the menu when no items match the filter.
```vue

{{ fruit }}
```
### With form submission
The Autocomplete value is submitted as a regular text field in forms.
```vue
```
## Accessibility
Adheres to the Combobox WAI-ARIA design pattern.
### Keyboard Interactions
