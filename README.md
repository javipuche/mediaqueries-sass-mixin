# Mediaqueries Sass Mixin

**Mixin** sencillo para usar **Mediaqueries** en **Sass** de manera fácil y personalizable, inspirado en el framework Foundation de ZURB.

## Cómo instarlo

```
bower install mediaqueries-sass-mixin
```

## Doc

**Breakpoints personalizados**

Puedes cambiar los breakpoints que vienen por defecto y/o añadir nuevos de la siguiente manera:

```
// Default breakpoints

$breakpoints: (
    small: 544px,
    medium: 768px,
    large: 1024px,
    xlarge: 1200px,
    xxlarge: 1440px,
) !default;

// Custom breakpoints

$breakpoints: (
    example: pixels
) !default;
```

**Sintaxis**

Una vez configurados los breakpoints, puedes usarlos de la siguiente manera:

```
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

    // Para pantallas retina

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
