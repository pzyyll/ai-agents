# Color Area
Alpha
## Features
## Installation
Install the component from your command line.
Looking for a complete color picker? Check out the Color Picker example that combines Color Area, Color Slider, Color Field, and Color Swatch components.
## Anatomy
Import all parts and piece them together.
```vue

```
## API Reference
### ColorAreaRoot
The root component that provides the color area context and state management.
### ColorAreaArea
The interactive area component where users can select color values by clicking or dragging.
### ColorAreaThumb
The draggable thumb component that indicates the current position in the color area.
## Examples
### HSL Saturation/Lightness
A common use case for color area is selecting saturation and lightness in HSL color space.
```vue

```
### RGB Red/Green Selector
Using RGB color space with red and green channels.
```vue

```
### Disabled State
Disable interaction with the color area.
```vue

```
## Accessibility
### Keyboard Interactions
| Key | Description |
 --- |
| `ArrowLeft` | Decreases the x-axis channel value by one step. |
| `ArrowRight` | Increases the x-axis channel value by one step. |
| `ArrowUp` | Increases the y-axis channel value by one step. |
| `ArrowDown` | Decreases the y-axis channel value by one step. |
| `Shift + ArrowKey` | Changes values by 10 steps at a time. |
| `PageUp` | Increases the y-axis channel value by a larger step. |
| `PageDown` | Decreases the y-axis channel value by a larger step. |
| `Home` | Jumps left (decreases x-axis value). |
| `End` | Jumps right (increases x-axis value). |
