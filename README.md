# Boiled Page badge component

Badge SCSS component for Boiled Page frontend framework. It is intended to highlight additional information.

## Install

Place `_badge.scss` file to `/assets/css/components` directory, and add its path to components block in `assets/css/app.scss` file.

## Usage

### Classes

Class name | Description | Example
---------- | ----------- | -------
`badge` | Applies a badge. | `<span class="badge"></span>`

### Examples

#### Example 1

The following example shows a badge.

```html
<span class="badge">Badge</span>
```

### Extension ideas

#### Scheme colored badges

Add `generate-badge` to each scheme in SCSS variables with the value of true or false. Then you can use badges in colors of enabled schemes.

```scss
/* Badge component extensions */
span.badge {

  // Scheme colored badges
  @each $scheme in map-keys($schemes) {
    @if (map-val($schemes, $scheme, generate-badge)) {
      &.badge--#{$scheme} {
        background-color: map-val($schemes, $scheme, bg-color);
        color: map-val($schemes, $scheme, fg-bold-color) !important;
      }
    }
  }
}
```
