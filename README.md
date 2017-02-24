# Mediaqueries Sass Mixin

**Mixin** sencillo para usar **Mediaqueries** en **Sass** de manera fácil y personalizable.

## Cómo instalarlo

```
bower instscreen mediaqueries-sass-mixin
```

Una vez descargado solo tienes que importarlo al principio de tu proyecto:

```scss
@import "mediaqueries-sass-mixin";
```

## Documentación

**Configuración por defecto**

Puedes cambiar la configuración por defecto de la siguiente manera:

```scss

// Font size base para convertir los pixeles en ems
$mq-font-size: 16px !default;

// Media type por defecto
$mq-media-type: 'screen' !default;

// Default breakpoints

$breakpoints: (
    small: 544px,
    medium: 768px,
    large: 1024px,
    xlarge: 1200px,
    xxlarge: 1440px,
) !default;
```

**Sintaxis**

Una vez configurados los breakpoints, puedes usarlos de la siguiente manera:

```scss
body{
    // De móvil a escritorio

    @include breakpoint(small) {
        background: red;
    }

    // De escritorio a móvil

    @include breakpoint(small down) {
        background: green;
    }

    // Del breakpoint seleccionado al siguiente

    @include breakpoint(small only) {
        background: blue;
    }

    // Para pantscreenas retina

    @include breakpoint(retina) {
        background: grey;
    }

    // Para orientación portrait

    @include breakpoint(portrait) {
        background: yellow;
    }

    // Para orientación landscape

    @include breakpoint(landscape) {
        background: purple;
    }
}
```

Esto da como resultado el siguiente código CSS:

```css
@media screen and (min-width: 34em) {
    body {
        background: red;
    }
}
@media screen and (max-width: 33.9375em) {
    body {
        background: green;
    }
}
@media screen and (min-width: 34em) and (max-width: 47.9375em) {
    body {
        background: blue;
    }
}
@media screen and (-webkit-min-device-pixel-ratio: 2), screen and (min-resolution: 192dpi) {
    body {
        background: grey;
    }
}
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

**Valores personalizados**

También acepta valores personalizados en pixeles o ems.

```scss
body{
    // En pixels 544px/544 (con o sin 'px').
    // En ems 34em (con 'em').

    // De móvil a escritorio.

    @include breakpoint(544px) {
        background: red;
    }

    // De escritorio a móvil.

    @include breakpoint(544px down) {
        background: green;
    }

    // De el tamaño elegido al siguiente breakpoint definido (si existe).

    @include breakpoint(544px only) {
        background: blue;
    }

    // Rango personalizado

    @include breakpoint(654px 935px) {
        background: grey;
    }
}
```

Esto da como resultado el siguiente código CSS:

```css
@media screen and (min-width: 34em) {
  background: red;
}
@media screen and (max-width: 33.9375em) {
  background: green;
}
@media screen and (min-width: 34em) and (max-width: 47.9375em) {
  background: blue;
}
@media screen and (min-width: 40.875em) and (max-width: 58.375em) {
  background: grey;
}
```

##License

Licensed under the MIT License
