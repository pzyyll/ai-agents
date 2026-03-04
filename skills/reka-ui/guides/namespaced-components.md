url: /docs/guides/namespaced-components.md

# Namespaced components
Reka UI design pattern is to create primitives for each component, and allow user to construct or compose components however they want.
However, importing all the necessary components 1-by-1 can be quite an effort, and the user might sometimes accidentally leave out an important component.
## How to use?
First, you need to import the namespaced components via `reka-ui/namespaced` in your Vue component.
```vue line=2
```
Then, you can use all the relevant components within the namespace.
```vue line=6-17

Trigger

…
```
