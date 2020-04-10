# @haaretz/sass-type

> Typographic scale with css custom properties

## Installation

```sh
yarn add --dev @haaretz/css-type
```
or with npm:
```sh
yarn install --save-dev @haaretz/css-type
```

## Usage

```scss
@import '~@haaretz/css-type'
```

### Configuration

`@haaretz/sass-type` exposes the following configuration variables:

#### `$htz-typescale-steps`
A map enabling or disabling the generation of typographic
scale custom properties on a pre-step basis  
**type:** `map`  
**default:**
```scss
$htz-typescale-steps: (
  -4: false,
  -3: false,
  -2: false,
  -1: false,
  0: false,
  1: false,
  2: false,
  3: false,
  4: false,
  5: false,
  6: false,
  7: false,
  8: false,
  9: false,
  10: false,
  11: false,
  12: false,
  13: false,
  14: false,
) !default;
```

### Usage

#### `generate-typography-custum-props`

Generate the custom props used by the `type` mixin, based on the configuration
of `$htz-typescale-steps`. **Must be used _after_ `$htz-typescale-steps` was
defined.**  
**Type:** `mixin`  
**Example:**
```scss
@include generate-typography-custum-props();
// -> :root { /* custom property declerations */ }
```

#### `type`
Output font-size and line-height definitions for a defined step 
in the typographic scale.  
**Type:** `mixin`  
**Params:**  
  `$step` (`number`): The step in the typographic scale to be used.  
  `$line` (`number`): _OPTIONAL_. Overrides the default line-height for
  the step with a number of vertical rhythm units.
