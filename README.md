# o-promobox [![Build Status](https://circleci.com/gh/Financial-Times/o-promobox.png?style=shield&circle-token=9303143d394812726e632cae33c93b9d7840edff)](https://circleci.com/gh/Financial-Times/o-promobox)

**This module has been deprecated**

___
Styling for promoboxes
___

## Markup

Add the `o-promobox` class to the element you wish to apply the styling.  Typically a promobox will contain an image `o-promobox__image`, some paragraph, `<p>`, tags and a title `o-promobox__title`.

```html
<div class="o-promobox">
	<h3 class="o-promobox__title">My Promobox</h3>
	<img class="o-promobox__image" src="//my-image.png" alt="" />
	<p>My paragraph</p>
</div>
```

Note: it is up to the product developer to decide how to 'flow' other content around the promobox.  They might choose to `float: left;` the promobox or `display: inline` it - or the product developer may decide to display it full width.

## Themes

### [Standard theme](https://origami-build.ft.com/v2/files/o-promobox/demos/standard.html)

```html
<div class="o-promobox o-promobox--standard">
	<h3 class="o-promobox__title">My Promobox</h3>
	<img class="o-promobox__image" src="//my-image.png" alt="" />
	<p>My paragraph</p>
</div>
```

### Your own theme

You can create your own modifiers, for example: `.o-promobox--my-theme`.

```html
<div class="o-promobox o-promobox--my-theme">
	<h3 class="o-promobox__title">My Promobox</h3>
	<img class="o-promobox__image" src="//my-image.png" alt="" />
	<p>My paragraph</p>
</div>
```

```scss
.o-promobox--my-theme {
	font-family: oFontsGetFontFamilyWithFallbacks(MillerDisplay);
	color: #ffffff;
	background-color: oColorsGetPaletteColor(claret);

	.o-promobox__title {
		font-size: 14px;
		line-height: 18px;
		border-bottom: 1px solid currentColor;
	}
	p {
		font-size: 12px;
		line-height: 16px;
	}
}
```

## Responsive

The module comes in two layouts.  The default, [full-width layout](https://origami-build.ft.com/v2/files/o-promobox/demos/standard.html), recommended for smaller screens, and [a thinner 'skinny' layout](https://origami-build.ft.com/v2/files/o-promobox/demos/standard-skinny.html) currently fixed to 167 pixels (for legacy reasons).

To [enable responsivity](https://origami-build.ft.com/v2/files/o-promobox/demos/custom-responsivity.html), follow the example below:-

### On a specific element

```html
<div class="o-promobox o-promobox--custom-responsivity">
	<h3 class="o-promobox__title">My Promobox</h3>
	<img class="o-promobox__image" src="//my-image.png" alt="" />
	<p>My paragraph</p>
</div>
```

```scss
@o-promobox-is-silent: false;
@import 'o-promobox/main';

@media (min-width: 300px) {
	.o-promobox--custom-responsivity {
		@include oPromobox($skinny: true);

		.o-promobox__image {
			@include oPromoboxImage($fullwidth: true);
		}
	}
}
```

### Context-based

```html
<div class="my-sidebar">
	<div class="o-promobox">
		<h3 class="o-promobox__title">My Promobox</h3>
		<img class="o-promobox__image" src="//my-image.png" alt="" />
		<p>My paragraph</p>
	</div>
</div>
```

```scss
@o-promobox-is-silent: false;
@import 'o-promobox/main';

@media (min-width: 300px) {
	.my-sidebar {
		.o-promobox {
			@include oPromobox($skinny: true);
		}
		.o-promobox__image {
			@include oPromoboxImage($fullwidth: true);
		}
	}
}
```

----

## License

Copyright (c) 2016 Financial Times Ltd. All rights reserved.

This software is published under the [MIT licence](http://opensource.org/licenses/MIT).
