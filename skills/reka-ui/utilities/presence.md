# Presence
How is this component different from Vue Transition?
A: The biggest difference is it accepts css animation, and control the visibility of element.
Presence component provides enhanced control over element mounting/unmounting. It ensures animations and transitions complete before removing elements from the DOM, making it perfect for animated UI components.
## API Reference
Read our Animation Guide to learn more about implementing animations with Presence component.
## Example
```vue line=2,4,5
```
### Force Mount
When you need to ensure content is always rendered regardless of the present state:
```vue

This content will always be rendered

This content is hidden

```
