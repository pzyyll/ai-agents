# Color Slider
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
### ColorSliderRoot
The root component that provides the slider functionality and context.
### ColorSliderTrack
The track component that displays the color gradient background.
### ColorSliderThumb
The draggable thumb component for selecting values.
## Examples
### Hue Slider
A horizontal hue slider in HSL color space.
```vue

```
### Alpha Channel
Slider for adjusting the alpha (opacity) channel.
```vue

```
### Vertical Orientation
A vertical slider for space-constrained layouts.
```vue

```
### RGB Channel Sliders
Sliders for individual RGB channels.
```vue```
### Custom Step Value
Use a custom step increment for finer or coarser control.
```vue

```
## Accessibility
### Keyboard Interactions
| Key | Description |
 --- |
| `ArrowLeft` | Decreases the value in horizontal orientation. |
| `ArrowRight` | Increases the value in horizontal orientation. |
| `ArrowUp` | Increases the value in vertical orientation. |
| `ArrowDown` | Decreases the value in vertical orientation. |
| `PageUp` | Increases the value by a larger step. |
| `PageDown` | Decreases the value by a larger step. |
| `Home` | Sets the value to minimum. |
| `End` | Sets the value to maximum. |
