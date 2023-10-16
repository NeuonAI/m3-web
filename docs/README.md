### Buttons

`m3-button`

#### Element supports

`<a>`, `<button>`

#### Modifiers

`m3-button__filled-tonal` (variant: filled tonal)

`m3-button__outlined` (variant: outlined)

`m3-button__text` (variant: text)

```html

<button class="m3-button">
  <span class="m3-button--icon m3-sym">check</span> <!-- optional -->
  <span class="m3-button--label">Button</span>
</button>
```

### Checkbox

`m3-checkbox`

#### Element supports

`<input type="checkbox">`

```html
<!-- Standalone -->
<input class="m3-checkbox" type="checkbox">

<!-- With label -->
<label class="m3-checkbox-container">
  <input class="m3-checkbox" type="checkbox">
</label>
```

### Chip

`m3-chip`

#### Element supports

`<a>`, `<button>`

#### Modifiers

`m3-chip__filled-tonal` (variant: filled-tonal)

`m3-chip__filled-error` (variant: filled-error)

```html

<button class="m3-chip">
  <span class="m3-chip--label">Chip</span>
</button>
```

### Icon

`m3-sym`

#### Modifiers

`m3-sym__filled` (variant: filled)

#### Properties

`font-size`, `font-weight`

```html
<span class="m3-sym" style="font-size: 24px; font-weight: normal">home</span>
```

### Icon Button

`m3-icon-button`

#### Element supports

`<a>`, `<button>`

#### Modifiers

`m3-icon-button__filled` (variant: filled)

`m3-icon-button__filled-tonal` (variant: filled tonal)

`m3-icon-button__outlined` (variant: outlined)

`m3-icon-button__selected` (mode: selected)

```html

<button class="m3-icon-button">
  <span class="m3-icon-button--icon m3-sym">check</span>
</button>
```

### Navigation Rail

`m3-nav-rail`

### Item

#### Element supports

`<a>`, `<button>`

#### Modifiers

`m3-nav-rail-button__selected` (mode: selected)

```html

<nav class="m3-nav-rail">
  <a class="m3-nav-rail-button">
    <span class="m3-nav-rail-button--icon m3-sym">home</span>
    <span class="m3-nav-rail-button--label">Home</span>
  </a>
  <!-- more items -->
</nav>
```

### Radio Button

`m3-radio-button`

#### Element supports

`<input type="radio">`

```html
<!-- Standalone -->
<input class="m3-radio-button" type="radio">

<!-- With label -->
<label class="m3-radio-button-container">
  <input class="m3-radio-button" type="checkbox">
</label>
```

### Switch

`m3-switch`, `m3-switch__selected`

#### Usage guides

```html
<!-- minimal usage, without icon -->
<button class="m3-switch">
  <span class="m3-switch--handle"></span>
</button>
```

```html
<!-- switch with icon -->
<button class="m3-switch">
  <span class="m3-switch--handle"></span>
  <span class="m3-switch--icon m3-sym">check</span>
</button>
```

```html
<!-- persistent icon -->
<button class="m3-switch m3-switch__persistent-icon">
  <span class="m3-switch--handle"></span>
  <span class="m3-switch--icon m3-sym">check</span>
</button>
```

```html
<!-- selected state, works with or without icon -->
<button class="m3-switch m3-switch__selected">
  <span class="m3-switch--handle"></span>
</button>
```

> [!WARNING]
> Adding or removing icon element would cause it to appear or disappear
> without being animated. Consider using a modifier instead.

Switch works only on `<button>`.
