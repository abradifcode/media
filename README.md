# Media [![Build Status](https://secure.travis-ci.org/css-recipes/media.png?branch=master)](http://travis-ci.org/css-recipes/media)

> Media queries shortcuts. Also include some predefined values.

## Getting Started

If you haven't used [css-recipes](http://css-recipes.putaindecode.io/) before, be sure to check out the [Getting Started](http://css-recipes.putaindecode.io/getting-started) guide, as it explains consume the recipes using Bower. Once you're familiar with that process, you may install this recipe with this command:

```shell
bower install css-recipe-media --save-dev
```

Once the recipe has been installed (& assuming `bower_components` folder is in your Sass import paths), it may be enabled inside your Sass file with this line:

```scss
@import "css-recipe-media/index"
```

Read more below to find alternative way to use this recipe.


## Component purpose

**This recipe is available as Sass (scss) only.**

The component just give you some media queries shortcuts with some predefined size.

## Browser support

_This component use [media queries](http://caniuse.com/#search=mediaqueries)._

## Availables Sass mixin(s) shortcuts

### Predefined media queries

+ `crp-Media-s()`
+ `crp-Media-m()`
+ `crp-Media-l()`
+ `crp-Media-xl()`

_ProTip™ : It's recommanded to use them with a mobile first approch, that give you the ability to handle 'xs' screen (default) & add/edit CSS rules in mixin `@content`. See usage section for an example._

### Screen size min & max (for width & height)

+ `crp-Media-min($min-size, $prop: 'width')`
+ `crp-Media-max($min-size, $prop: 'width')`
+ `crp-Media-gap($min-size, $max-size, $prop: 'width')`

+ `crp-Media-min-width($min-width)`
+ `crp-Media-max-width($max-width)`
+ `crp-Media-gap-width($min-width, $max-width)`

+ `crp-Media-min-height($min-height)`
+ `crp-Media-max-height($max-height)`
+ `crp-Media-gap-height($min-height, $max-height)`

### Orientation (portrait/horizontal & landscape/vertical)

+ `crp-Media-portrait`
+ `crp-Media-landscape`

### Resolution screen (hidpi, "retina" display)

```scss
$crp-Media-screen-default-dpi: 96 !default;
$crp-Media-pixel-ratio-breakpoint: 1.5 !default;
```

+ `crp-Media-resolution($ratio: $crp-Media-pixel-ratio-breakpoint, $minOrMax: 'min')`
+ `crp-Media-pixel-ratio($ratio: $crp-Media-pixel-ratio-breakpoint, $minOrMax: 'min')`
+ `crp-Media-highres($ratio: $crp-Media-pixel-ratio-breakpoint) (shortcut for pixel-ratio)`

### Available for you JavaScripts

+ `crp-Media-queries-for-js($name, $media-queries)`

```js
var size = window.getComputedStyle(document.body,':after').getPropertyValue('content');
if (size == 'widescreen') {
    // code for 'widescreen' !
}
```

### Usage examples

#### Sass use

_This recipes requires Sass `~3.2.0` or libsass `~0.?`_

```scss
selector {
    // my xs rules for iphone & similar
    
    @include crp-Media-s {
        // portrait ipad, landscape iphone & similar
    }
    
    @include crp-Media-m {
        // portrait ipad, landscape iphone, 
    }

    @include crp-Media-min-width(580px) {
        // custom rules
        
        @include landscape {
            // mediaCEPTION
        }
    }

    @include crp-Media-min-height(480px) {
        // some other rules depending on the height
    }
}
```

## Release History

 * 2013-09-06   v0.1.0   First release from CompassRecipes

---

Recipe submitted by [`MoOx` Maxime Thirouin](http://moox.io)