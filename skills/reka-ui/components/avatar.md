# Avatar
## Features
## Installation
Install the component from your command line.
## Anatomy
Import all parts and piece them together.
```vue

```
## API Reference
### Root
Contains all the parts of an avatar
### Image
The image to render. By default it will only render when it has loaded. You can use the `@loadingStatusChange` handler if you need more control.
### Fallback
An element that renders when the image hasn't loaded. This means whilst it's loading, or if there was an error. If you notice a flash during loading, you can provide a `delayMs` prop to delay its rendering so it only renders for those with slower connections. For more control, use the `@loadingStatusChange` emit on `AvatarImage`.
## Examples
### Clickable Avatar with tooltip
You can compose the Avatar with a Tooltip to display extra information.
```vue line=6-7,9,11-15

…

Tooltip content
```
