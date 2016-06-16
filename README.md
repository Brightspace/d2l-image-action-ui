# vui-image-action
[![Bower version][bower-image]][bower-url]
[![NPM version][npm-image]][npm-url]
[![Build status][ci-image]][ci-url]
[![Dependency Status][dependencies-image]][dependencies-url]

This component contains [SASS mixins](http://sass-lang.com/) and CSS that you can use to style image actions.

An Image Action is a link associated with an image that performs an action when clicked.

![screenshot of image actions](/screenshots/multiple.png)


## Installation

`vui-image-action` can be installed from [Bower][bower-url]:
```shell
bower install vui-image-action
```

Or alternatively from [NPM][npm-url]:
```shell
npm install vui-image-action
```

Depending on which installation method you choose, use that path when doing the SASS import:

```scss
@import 'bower_components/vui-image-action/image-action.scss';
// or...
@import "node_modules/vui-image-action/image-action.scss";
```

## Usage

An Image Action must have a `<img>` element for the image, and a `<span>` element describing the action. These elements should be enclosed in a `<a>` that performs the action when clicked.

HTML:
```html
<a href="#">
	<img src="img/help.svg" alt="">
	<span>Action</span>
</a>
```

SCSS:
```scss
a {
	@include vui-image-action;
}
```

Multiple Image Actions can be grouped in a list.

HTML:
```html
<ul>
	<li>
		<a href="#">
			<img src="img/print.svg" alt="">
			<span>Print</span>
		</a>
	</li>
	<li>
		<a href="#">
			<img src="img/settings.svg" alt="">
			<span>Settings</span>
		</a>
	</li>
</ul>
```
SCSS:
```scss
ul {
	@include vui-image-action-list;
}
a {
	@include vui-image-action;
}
```


For further information on this component and other VUI components, see the docs at [ui.valence.d2l.com](http://ui.valence.d2l.com/).

#### Coding styles
See the [VUI Best Practices & Style Guide](https://github.com/Brightspace/valence-ui-docs/wiki/Best-Practices-&-Style-Guide) for information on VUI naming conventions, plus information about the [EditorConfig](http://editorconfig.org) rules used in this repo.

[bower-url]: http://bower.io/search/?q=vui-image-action
[bower-image]: https://img.shields.io/bower/v/vui-image-action.svg
[npm-url]: https://www.npmjs.org/package/vui-image-action
[npm-image]: https://img.shields.io/npm/v/vui-image-action.svg
[ci-url]: https://travis-ci.org/Brightspace/d2l-image-action-ui
[ci-image]: https://travis-ci.org/Brightspace/d2l-image-action-ui.svg?branch=master
[dependencies-url]: https://david-dm.org/brightspace/d2l-image-action-ui
[dependencies-image]: https://img.shields.io/david/Brightspace/d2l-image-action-ui.svg
