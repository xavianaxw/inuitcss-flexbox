[![Build Status](https://travis-ci.org/xavianaxw/inuitcss-flexbox.svg?branch=master)](https://travis-ci.org/xavianaxw/inuitcss-flexbox) [![npm version](https://badge.fury.io/js/inuitcss-flexbox.svg)](https://badge.fury.io/js/inuitcss-flexbox)

[Browser Support](https://caniuse.com/#search=flexbox)

# What is InuitCSS?

# ![inuitcss](http://inuitcss.com/img/logo-small.png)

**Extensible, scalable, Sass-based, OOCSS framework for large and long-lasting
UI projects.**

inuitcss is a framework in its truest sense: it does not provide you with UI and
design out of the box, instead, it provides you with a solid architectural
baseline upon which to complete your own work.

[https://github.com/inuitcss/inuitcss](https://github.com/inuitcss/inuitcss)

## and [inuitcss-flexbox](https://github.com/xavianaxw/inuitcss-flexbox) is for?

To replace `o-layout` with flexbox for modern browsers!

## Installation

You can use inuitcss in your project by installing it using a package manager
(recommended):

**npm:**

```
$ npm install inuitcss --save
```

**yarn:**

```
$ yarn add inuitcss
```

You can download inuitcss and save it into your project’s `css/` directory. This
method is not recommended because you lose the ability to easily and quickly
manage and update inuitcss as a dependency.

## Getting started

Once you are done setting up your project with [inuitcss](https://github.com/inuitcss/inuitcss/tree/master), you should end up with something like this.

```scss
// SETTINGS
@import 'settings/settings.config';
@import 'settings/settings.core';
@import 'settings/settings.global';

// TOOLS
@import 'tools/tools.font-size';
@import 'tools/tools.clearfix';
@import 'tools/tools.hidden';
@import 'sass-mq/mq';

// GENERIC
@import 'generic/generic.box-sizing';
@import 'generic/generic.normalize';
@import 'generic/generic.reset';
@import 'generic/generic.shared';

// ELEMENTS
@import 'elements/elements.page';
@import 'elements/elements.headings';
@import 'elements/elements.images';
@import 'elements/elements.tables';

// OBJECTS
@import 'objects/objects.wrapper';
@import 'objects/objects.layout';
@import 'objects/objects.media';
@import 'objects/objects.flag';
@import 'objects/objects.list-bare';
@import 'objects/objects.list-inline';
@import 'objects/objects.box';
@import 'objects/objects.block';
@import 'objects/objects.ratio';
@import 'objects/objects.crop';
@import 'objects/objects.tables';
@import 'objects/objects.pack';

// UTILITIES
$inuit-offsets: true;

@import 'utilities/utilities.clearfix';
@import 'utilities/utilities.widths';
@import 'utilities/utilities.headings';
@import 'utilities/utilities.spacing';
@import 'utilities/utilities.print';
@import 'utilities/utilities.hide';
```

From here you want to look for the following lines in your main scss file.

```scss
@import 'objects/objects.layout';
@import 'utilities/utilities.widths';
```

and replacing them with [inuitcss-flexbox](https://github.com/xavianaxw/inuitcss-flexbox)'s `objects.flex` and `utilities.widths`
```scss
@import 'objects/objects.flex';
@import 'utilities/utilities.widths';
```

and you're good to go!

## Core functionality

By default, [inuitcss-flexbox](https://github.com/xavianaxw/inuitcss-flexbox) inherits the following variables from [inuitcss](https://github.com/inuitcss/inuitcss/tree/master) to keep it as similar to inuitcss's vanilla package.

```scss
// settings.global.scss
$inuit-global-line-height:  24px !default;
$inuit-global-spacing-unit: round($inuit-global-line-height) !default;

$inuit-global-spacing-unit-factor-tiny:   0.25 !default;
$inuit-global-spacing-unit-factor-small:  0.5  !default;
$inuit-global-spacing-unit-factor-large:  2    !default;
$inuit-global-spacing-unit-factor-huge:   4    !default;

// utilities.widths.scss
$inuit-fractions: 1 2 3 4 5 !default;
$inuit-offsets: false !default;
$inuit-widths-delimiter: \/ !default;
$inuit-widths-breakpoint-separator: \@ !default;
```

Thus, by changing your settings.global configuration, it will directly affect `objects.flex` and `utilities.widths` off the bat with minimal changes.

## Basic Usage

```html
<div class="o-wrapper">
  <div class="o-flex">
    <div class="o-flex__item">1</div>
    <div class="o-flex__item">2</div>
    <div class="o-flex__item">3</div>
  </div>
</div>
```

## Modifiers

### Layouts

| Class | Description |
| ----- | ----------- |
| `o-flex--auto` | Ensures all `o-flex__item` have the same width and takes up full width of container |
| `o-flex--grids` | Our grid structure. Used alongside `utilities.widths` e.g. `<div class="o-flex__item u-1/2">1</div>` |
| `o-flex--grids-stretched` | Modifier for `o-flex--grids` to force height of all `o-flex__item` to match one another |

### Directions

| Class | Description |
| ----- | ----------- |
| `o-flex--reversed` | Reverse direction of `o-flex__item` starting from right to left |
| `o-flex--column` | Changing direction of `o-flex__item` starting from top to bottom |
| `o-flex--column-reversed` | The reverse of `o-flex--column` |

### Positioning

| Class | Description |
| ----- | ----------- |
| `o-flex--centered` | Center all `o-flex__item` horizontally and vertically |
| `o-flex--centered-v` | Center all `o-flex__item` vertically only |
| `o-flex--centered-h` | Center all `o-flex__item` vertically only |
| `o-flex--lock-left` | Locks `o-flex__item` to left side |
| `o-flex--lock-right` | Locks `o-flex__item` to right side |
| `o-flex--lock-top` | Locks `o-flex__item` to top side |
| `o-flex--lock-bottom` | Locks `o-flex__item` to bottom side |
| `o-flex--lock-top-left` | Locks `o-flex__item` to top left side |
| `o-flex--lock-top-right` | Locks `o-flex__item` to top right side |
| `o-flex--lock-bottom-left` | Locks `o-flex__item` to bottom left side |
| `o-flex--lock-bottom-right` | Locks `o-flex__item` to bottom right side |

### Wrapping

| Class | Description |
| ----- | ----------- |
| `o-flex--nowrap` | Sets the following property `flex-wrap: nowrap` |
| `o-flex--wrap` | **(default)** Sets the following property `flex-wrap: wrap` |
| `o-flex--wrap-reverse` | Sets the following property `flex-wrap: wrap-reverse` |

### Spacing

| Class | Description |
| ----- | ----------- |
| `o-flex--space-between` | Sets the following property `justify-content: space-between` |
| `o-flex--space-around` | Sets the following property `justify-content: space-around` |

## Mixins `v.0.0.6` onwards!

[Direction](#directions)
`@include inuit-flex-direction();`

[Position](#positioning)
`@include inuit-flex-position();`

[Wrapping](#wrapping)
`@include inuit-flex-wrap();`

[Spacing](#spacing)
`@include inuit-flex-spacing();`

**NOTE:** *Do not wrap values with singlequotes!*

How to use?

```scss
.block {
  @include inuit-flex-direction(row);
  @include inuit-flex-position(lock-bottom);
  @include inuit-flex-spacing(space-between);

  // @include mq() is from 'sass-mq'. A package dependency in inuitcss by default
  @include mq($from: tablet) {
    @include inuit-flex-direction(row-reverse);
    @include inuit-flex-position(lock-top-right);
    @include inuit-flex-wrap(nowrap);
  }
}
```

## Need More Examples?

A page with more examples on how to use [inuitcss-flexbox](https://github.com/xavianaxw/inuitcss-flexbox) will be released soon. Stay tuned!

## Something not right?
Create a [Pull Request](https://github.com/xavianaxw/inuitcss-flexbox/compare) or submit an [issue](https://github.com/xavianaxw/inuitcss-flexbox/issues/new) so I can fix them!
