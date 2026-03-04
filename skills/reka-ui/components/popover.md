# Popover
## Features
## Installation
Install the component from your command line.
## Anatomy
Import all parts and piece them together.
```vue

```
## API Reference
### Root
Contains all the parts of a popover.
### Trigger
The button that toggles the popover. By default, the `PopoverContent` will position itself against the trigger.
### Anchor
An optional element to position the `PopoverContent` against. If this part is not used, the content will position alongside the PopoverTrigger.
### Portal
When used, portals the content part into the `body`.
### Content
The component that pops out when the popover is open.
### Arrow
An optional arrow element to render alongside the popover. This can be used to help visually link the anchor with the `PopoverContent`. Must be rendered inside `PopoverContent`.
### Close
The button that closes an open popover.
## Examples
### Constrain the content size
You may want to constrain the width of the content so that it matches the trigger width. You may also want to constrain its height to not exceed the viewport.
We expose several CSS custom properties such as `--reka-popover-trigger-width` and `--reka-popover-content-available-height` to support this. Use them to constrain the content dimensions.
```vue line=10,11
…

…
```
```css line=3,4
/\ styles.css \/
.PopoverContent {
width: var(--reka-popover-trigger-width);
max-height: var(--reka-popover-content-available-height);
}
```
### Origin-aware animations
We expose a CSS custom property `--reka-popover-content-transform-origin`. Use it to animate the content from its computed origin based on `side`, `sideOffset`, `align`, `alignOffset` and any collisions.
```vue line=9
…

…
```
```css line=3
/\ styles.css \/
.PopoverContent {
transform-origin: var(--reka-popover-content-transform-origin);
animation: scaleIn 0.5s ease-out;
}
@keyframes scaleIn {
from {
opacity: 0;
transform: scale(0);
}
to {
opacity: 1;
transform: scale(1);
}
}
```
### Collision-aware animations
We expose `data-side` and `data-align` attributes. Their values will change at runtime to reflect collisions. Use them to create collision and direction-aware animations.
```vue line=9
…

…
```
```css line=6-11
/\ styles.css \/
.PopoverContent {
animation-duration: 0.6s;
animation-timing-function: cubic-bezier(0.16, 1, 0.3, 1);
}
.PopoverContent[data-side="top"] {
animation-name: slideUp;
}
.PopoverContent[data-side="bottom"] {
animation-name: slideDown;
}
@keyframes slideDown {
from {
opacity: 0;
transform: translateY(-10px);
}
to {
opacity: 1;
transform: translateY(0);
}
}
@keyframes slideUp {
from {
opacity: 0;
transform: translateY(10px);
}
to {
opacity: 1;
transform: translateY(0);
}
}
```
### With custom anchor
You can anchor the content to another element if you do not want to use the trigger as the anchor.
```vue line=7-11

Row as anchor Trigger

…
```
```css
/\ styles.css \/
.Row {
background-color: gainsboro;
padding: 20px;
}
```
### Close using slot props
Alternatively, you can use the `close` method provided by the `PopoverRoot` slot props to programmatically close the popover.
```vue line=4,8,16-20
Open

```
## Accessibility
Adheres to the Dialog WAI-ARIA design pattern.
### Keyboard Interactions
## Custom APIs
Create your own API by abstracting the primitive parts into your own component.
#### Abstract the arrow and set default configuration
This example abstracts the `PopoverArrow` part and sets a default `sideOffset` configuration.
#### Usage
```vue
Popover trigger
Popover content
```
#### Implementation
```ts
// your-popover.ts
export { default as PopoverContent } from 'PopoverContent.vue'
export { PopoverRoot as Popover, PopoverTrigger } from 'reka-ui'
```
```vue

```
