# Listbox
## Features
## Installation
Install the component from your command line.
## Anatomy
Import all parts and piece them together.
```vue

```
## API Reference
### Root
Contains all the parts of a listbox. An `input` will also render when used within a `form` to ensure events propagate correctly.
### Filter
Input element to perform filtering.
### Content
Contains all the listbox group and items.
### Item
The item component.
### ItemIndicator
Renders when the item is selected. You can style this element directly, or you can use it as a wrapper to put an icon into, or both.
### Group
Used to group multiple items. use in conjunction with `ListboxGroupLabel` to ensure good accessibility via automatic labelling.
### GroupLabel
Used to render the label of a group. It won't be focusable using arrow keys.
### Virtualizer
Virtual container to achieve list virtualization.
## Examples
### Binding objects as values
Unlike native HTML form controls which only allow you to provide strings as values, `reka-ui` supports binding complex objects as well.
```vue line=12,16,21

{{ person.name }}
```
### Selecting multiple values
The `Listbox` component allows you to select multiple values. You can enable this by providing an array of values instead of a single value.
```vue line=12,18
...
```
### Custom filtering
```vue line=13,15-16,21,24

{{ person.name }}
```
### Virtual List
Rendering a long list of item can slow down the app, thus using virtualization would significantly improve the performance.
See the virtualization guide for more general info on virtualization.
```vue line=18-23

{{ person.name }}
```
## Accessibility
Adheres to the Listbox WAI-ARIA design pattern.
### Keyboard Interactions
