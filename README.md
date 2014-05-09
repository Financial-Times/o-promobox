# o-promobox [![Build Status](https://travis-ci.org/Financial-Times/o-promobox.png?branch=master)](https://travis-ci.org/financial-times/o-promobox)

___
Styling for promoboxes
___

## Markup

Add the `o-promobox` class to the element you wish to apply the styling.  Typically a promobox will contain an image `o-promobox__image`, some paragraph, `<p>`, tags and a title `o-promobox__title`.

```html
<div class="o-promobox">
  <h3 class="o-promobox__title">My Promobox</h3>
  <img src="//my-image.png" />
  <p>My paragraph</p>
</div>
```

Note: it is up to the product developer to decide how to 'flow' other content around the promobox.  They might choose to `float: left;` the promobox or `display: inline` it - or the product developer may decide to display it full width.

## Themeable

Either extend the base classes to create a custom theme or use the [standard theme](http://build.origami.ft.com/files/o-promobox@0.0.6/demos/standard.html).


```html
<div class="o-promobox o-promobox--standard">
  ...
</div>
```

## Responsive

The module comes in two layouts.  The default, [full-width layout](http://build.origami.ft.com/files/o-promobox@0.0.6/demos/standard.html), recommended for smaller screens, and [a thinner 'skinny' layout](http://build.origami.ft.com/files/o-promobox@0.0.6/demos/standard-skinny.html) currently fixed to 167 pixels (for legacy reasons).

To enable responsivity either add the `o-promobox--responsive` class.

To be able to customise the breakpoints, follow the example below:-

```scss
@o-promobox-is-silent: false;
@import "o-promobox";

@media (max-width: 300px) {
  .o-promobox{
    @include o-promobox--skinny;
  }
}
```
