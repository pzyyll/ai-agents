Utility component that implements the roving tabindex method to manage focus
between items.

# Roving Focus
Learn more about roving tabindex in Keyboard Navigation Inside Composite Components
## Anatomy
Import all parts and piece them together.
```vue

```
## API Reference
### Group
Contains all the parts of a Roving Focus
### Item
The item that would inherit the roving tabindex
## Examples
### Vertical orientation
```vue{2}
…
```
### Loop
Use `loop` property to enable roving from last item to the first item, and vice versa.
```vue{2}
…
```
### Initial focus item
Set `active` prop to item to initially focused item.
```vue{4}
1
2
3
```
### Unfocusable item
Set `focusable="false"` prop to item will prevent them from being focused.
```vue{4}
1
2
3
```
## Accessibility
Adheres to the Keyboard Navigation Inside Composite Components.
### Keyboard Interactions
