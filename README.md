# Media queries Sass Mixin

A **Sass Mixin** that helps you to create **media queries**.

## How to install

### NPM

```
npm install mediaqueries-sass-mixin --save
```

### Bower

```
bower install mediaqueries-sass-mixin --save
```

## How to use

Import the file in your main Sass file and customize default settings.

```scss
@import "mediaqueries-sass-mixin";
```

## Documentation

### Default Config

Change the default settings:

```scss

// Base font size to convert from px to rem
$mq-font-size: 16px !default;

// Default media type
$mq-media-type: 'screen' !default;

// Default breakpoints
$mq-breakpoints: (
    small: 544px,
    medium: 768px,
    large: 1024px,
    xlarge: 1200px,
    xxlarge: 1440px,
) !default;
```

### Syntax

#### SCSS

```scss
body {
    /**
     * Mobile first by default
     */
    @include breakpoint(small) {
        background: red;
    }
}
```

#### CSS Output

```css
@media screen and (min-width: 34em) {
    body {
        background: red;
    }
}
```

#### Options

```css
/**
 * Mobile First
 * @include breakpoint(small)
 */
@media screen and (min-width: 34em) {
    body {
        background: red;
    }
}

/**
 * Desktop First
 * @include breakpoint(small)
 */
@media screen and (max-width: 33.9375em) {
    body {
        background: green;
    }
}

/**
 * Thinking in Mobile first
 * From this breakpoint(small) to next (in this case to medium)
 * @include breakpoint(small only)
 */
@media screen and (min-width: 34em) and (max-width: 47.9375em) {
    body {
        background: blue;
    }
}

/**
 * Retina
 * @include breakpoint(retina)
 */
@media screen and (-webkit-min-device-pixel-ratio: 2), screen and (min-resolution: 192dpi) {
    body {
        background: grey;
    }
}

/**
 * Orientation
 * @include breakpoint(portrait) or @include breakpoint(landscape)
 */
@media screen and (orientation: portrait) {
    body {
        background: yellow;
    }
}
@media screen and (orientation: landscape) {
    body {
        background: purple;
    }
}
```

#### Custom units

Accept custom pixels and ems too:

```scss
body{
    /* Pixels with or without 'px' */
    @include breakpoint(544px) {
        background: red;
    }

    /* Ems with 'em' always */
    @include breakpoint(34em) {
        background: green;
    }

    /* You can use 'only' if you want */
    @include breakpoint(544px only) {
        background: blue;
    }

    /**
     * Ranges
     * Pixels/Pixels or Pixels/Ems or Ems/Ems
     */
    @include breakpoint(544px 40em) {
        background: grey;
    }
}
```

## License

Licensed under the MIT License
