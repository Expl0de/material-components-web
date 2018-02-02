<!--docs:
title: "Select Label"
layout: detail
section: components
excerpt: "The label is a text caption or description for the select."
iconId: text_field
path: /catalog/input-controls/text-field/label/
-->

# Select Label

Select labels display the type of input a field requires. Every select should have a label. Labels are aligned with the input line and always visible. They can be resting (when a field is inactive and empty) or floating. The label is a text caption or description for the select.

## Design & API Documentation

<ul class="icon-list">
  <li class="icon-list-item icon-list-item--spec">
    <a href="https://material.io/guidelines/components/text-fields.html#text-fields-layout">Material Design guidelines: Selects Layout</a>
  </li>
</ul>

## Usage

### HTML Structure

```html
<label class="mdc-select__label" for="my-select-id">Hint text</label>
```

### Usage within `mdc-text-field`

```html
<div class="mdc-text-field">
  <input type="text" id="my-select-id" class="mdc-select__input">
  <label class="mdc-select__label" for="my-select-id">Hint text</label>
  <div class="mdc-select__bottom-line"></div>
</div>
```

#### Avoid Dynamic ID Generation

It's also possible to wrap `mdc-select__input` within a `<label>` to avoid dynamic id generation:

```html
<label class="mdc-text-field">
  <input type="text" class="mdc-select__input">
  <span class="mdc-select__label">Hint Text</span>
  <div class="mdc-select__bottom-line"></div>
</label>
```

> _NOTE_: Only place an `mdc-select__label` inside of a select _if you plan on using
> Javascript_. Otherwise, the label must go outside of the text-field, as shown below.

#### Single Line, CSS Only

```html
<label for="text-field-no-js">Select with no JS: </label>
<div class="mdc-text-field">
  <input type="text" id="text-field-no-js" class="mdc-select__input" placeholder="Hint text">
  <div class="mdc-select__bottom-line"></div>
</div>
```

### CSS Classes

CSS Class | Description
--- | ---
`mdc-select__label` | Mandatory
`mdc-select__label--float-above` | Indicates the label is floating above the select
`mdc-select__label--shake` | Shakes the label

### `MDCSelectLabel`

##### `MDCSelectLabel.foundation`

This allows the parent `MDCSelect` component to access the public methods on the `MDCSelectLabelFoundation` class.

### `MDCSelectLabelAdapter`

Method Signature | Description
--- | ---
`addClass(className: string) => void` | Adds a class to the label element
`removeClass(className: string) => void` | Removes a class from the label element
`getWidth() => number` | Returns the width of the label element

### `MDCSelectLabelFoundation`

Method Signature | Description
--- | ---
`getWidth() => number` | Returns the width of the label element
`styleShake(isValid: boolean, isFocused: boolean)` | Styles the label to produce the shake effect when needed.
`styleFloat(value: string, isFocused: boolean, isBadInput: boolean)` | Styles the label to float or defloat as necessary.
