# Checkbox
## Features
## Installation
Install the component from your command line.
## Anatomy
Import all parts and piece them together.
```vue

```
## API Reference
### Root
Contains all the parts of a checkbox. An `input` will also render when used within a `form` to ensure events propagate correctly.
### Indicator
Renders when the checkbox is in a checked or indeterminate state. You can style this element directly, or you can use it as a wrapper to put an icon into, or both.
### Group Root
Wrapper around `CheckboxRoot` to support array of `modelValue`
## Examples
### Custom Values
Use the `trueValue` and `falseValue` props to specify custom values for the checked and unchecked states instead of the default `true`/`false`.
```vue line=5-6,11-12

Value: {{ acceptTerms }} 

Value: {{ permission }} 
```
### Indeterminate
You can set the checkbox to `indeterminate` by taking control of its state.
```vue line=5,9-14,16-18

```
## Accessibility
Adheres to the tri-state Checkbox WAI-ARIA design pattern.
### Keyboard Interactions
