Manages focus within a component boundary with support for trapping and
looping focus navigation.

# Focus Scope
Focus Scope provides enhanced control over keyboard focus management within component boundaries. It can trap focus within its container and optionally loop focus navigation, making it ideal for modal interfaces and other interactive components that need to manage focus states.
## API Reference
## Example
Basic usage with focus trapping
```vue line=2
```
### With Focus Looping
Enable both trapping and looping for complete focus management:
```vue line=2
```
### Handling Focus Event
```vue line=2-5

…

```
When using trapped mode, ensure there is always at least one focusable element within the scope to prevent focus from being trapped in an inaccessible state.
