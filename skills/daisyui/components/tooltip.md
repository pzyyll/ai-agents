# tooltip

Tooltip can be used to show a message when hovering over an element

[tooltip docs](https://daisyui.com/components/tooltip/)

## Class Names

- Component: `tooltip`
- Placement: `tooltip-top`, `tooltip-bottom`, `tooltip-left`, `tooltip-right`
- Color: `tooltip-primary`, `tooltip-secondary`, `tooltip-accent`, `tooltip-info`, `tooltip-success`, `tooltip-warning`, `tooltip-error`
- Modifier: `tooltip-open`

## Syntax

```html
<div class="tooltip {MODIFIER}" data-tip="tooltip text">
  <button class="btn">Hover me</button>
</div>
```

## Rules

- {MODIFIER} is optional and can have one of the placement/color class names
- Use `data-tip` attribute to set the tooltip text
- Use `tooltip-open` to force the tooltip to be visible
