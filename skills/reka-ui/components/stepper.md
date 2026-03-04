# Stepper

A set of steps that guide users through a multi-step process.

[stepper docs](https://reka-ui.com/docs/components/stepper)

## Anatomy

```vue
<script setup>
import { StepperDescription, StepperIndicator, StepperItem, StepperRoot, StepperSeparator, StepperTitle, StepperTrigger } from 'reka-ui'
</script>

<template>
  <StepperRoot>
    <StepperItem>
      <StepperTrigger>
        <StepperIndicator />
        <StepperTitle />
        <StepperDescription />
      </StepperTrigger>
      <StepperSeparator />
    </StepperItem>
  </StepperRoot>
</template>
```

## API Reference

### Root
Contains all stepper parts.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| modelValue | - | `number` | Controlled active step (v-model) |
| defaultValue | `1` | `number` | Default active step |
| orientation | `'horizontal'` | `'horizontal' \| 'vertical'` | Layout orientation |
| linear | `false` | `boolean` | Whether steps must be completed sequentially |

| Emit | Payload |
|------|---------|
| update:modelValue | `[payload: number]` |

| Slot Payload | Type |
|--------------|------|
| modelValue | `number \| undefined` |
| totalSteps | `number` |
| isNextDisabled | `boolean` |
| isPrevDisabled | `boolean` |
| isFirstStep | `boolean` |
| isLastStep | `boolean` |

### Item
Individual step container.

| Prop | Default | Type | Description |
|------|---------|------|-------------|
| step | - | `number` | Step index (required) |
| disabled | `false` | `boolean` | Prevents interaction |
| completed | `false` | `boolean` | Shows step as completed |

| Data Attribute | Value |
|----------------|-------|
| [data-state] | `"active" \| "inactive" \| "completed"` |
| [data-orientation] | `"vertical" \| "horizontal"` |
