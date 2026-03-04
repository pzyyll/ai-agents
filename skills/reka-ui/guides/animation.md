Animate Reka UI with CSS keyframes, native Vue Transition or JavaScript
animation library of your choice.

# Animation
Adding animation to Reka UI should feel similar to any other component, but there are some caveats noted here in regards to exiting animations with JS animation libraries.
## Animating with CSS animation
The simplest way to animate Primitives is with CSS.
You can use CSS animation to animate both mount and unmount phases. The latter is possible because the Reka UI will suspend unmount while your animation plays out.
```css
@keyframes fadeIn {
from {
opacity: 0;
}
to {
opacity: 1;
}
}
@keyframes fadeOut {
from {
opacity: 1;
}
to {
opacity: 0;
}
}
.DialogOverlay[data-state="open"],
.DialogContent[data-state="open"] {
animation: fadeIn 300ms ease-out;
}
.DialogOverlay[data-state="closed"],
.DialogContent[data-state="closed"] {
animation: fadeOut 300ms ease-in;
}
```
## Animating with Vue Transition
Other than using CSS animation, you might prefer to use the native Vue ``. Great news! It should be as easy as wrapping component (that has `forceMount` prop), and you are done!
```vue line=11,13,14,19,25-33

Edit profile

# Hello from inside the Dialog!

Close
```
## ⭐️ Animating with Motion Vue
Motion Vue is the recommended animation library for Reka UI. This lightweight, powerful library integrates seamlessly with components and offers extensive flexibility for creating smooth, performant animations.
```vue line=3,12,14-18,22-26,29,31

Edit profile

# Hello from inside the Dialog!

Close
```
Check out this Stackblitz Demo 🤩
## Delegating unmounting for JavaScript Animation
When many stateful Primitives are hidden from view, they are actually removed from the DOM. JavaScript animation libraries need control of the unmounting phase, so we provide the `forceMount` prop on many components to allow consumers to delegate the mounting and unmounting of children based on the animation state determined by those libraries.
For example, if you want to use @vueuse/motion to animate a `Dialog`, you would do so by conditionally rendering the dialog `Overlay` and `Content` parts based on the animation state from one of its composable like `useSpring`:
```vue line=32,34,41

Edit profile

# Hello from inside the Dialog!

Close
```
Check out this Stackblitz Demo
