**Looking for SASS-based `d2l-image-action`?** It's [over here](https://github.com/BrightspaceUI/image-action/tree/sass).

# d2l-image-action
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/BrightspaceUI/image-action)
[![Bower version][bower-image]][bower-url]
[![Build status][ci-image]][ci-url]

[Polymer](https://www.polymer-project.org/1.0/)-based web component for D2L image actions, which are buttons or links associated with an image that perform an action when clicked.

![screenshot of image actions](/screenshot.gif)

For further information on this and other Brightspace UI components, see the docs at [ui.developers.brightspace.com](http://ui.developers.brightspace.com/).

## Installation

`d2l-image-action` can be installed from [Bower][bower-url]:
```shell
bower install d2l-image-action
```

## Usage

Include the [webcomponents.js](http://webcomponents.org/polyfills/) "lite" polyfill (for browsers who don't natively support web components), then import `d2l-image-action.html` to get all three image-action web components:

```html
<head>
	<script src="bower_components/webcomponentsjs/webcomponents-lite.js"></script>
	<link rel="import" href="bower_components/d2l-image-action/d2l-image-action.html">
</head>
```

### Button-based actions

Use `<d2l-image-action-button>` in cases where an action is being performed, and not a navigation. Actions are typically done using a `click` event handler. Think about times you'd use a native `<button>` element instead of an `<a>`.

```html
<d2l-image-action-button icon="d2l-tier1:print">Print</d2l-image-action-button>
```

### Link-based actions

Alternatively, if you wish to perform a browser navigation when the action is clicked, use `<d2l-image-action-link>`. Think of places you'd use a native `<a>` element instead of a `<button>`.

```html
<d2l-image-action-link
	href="settings.html"
	icon="d2l-tier1:gear">Settings</d2l-image-action-link>
```

### Icons

As their name suggests, image-actions are intended to be used with an icon, specifically one which is `18px` by `18px` in size. To set the icon, use the `icon` attribute, which takes a reference to a [Polymer iron-iconset-svg](https://github.com/PolymerElements/iron-iconset-svg) source.

The [d2l-icons](https://github.com/BrightspaceUI/icons) component exposes all of the D2L icons as `iron-iconset-svg` sources -- simply import them using the `tier1` category (for 18x18 icons) and reference them by key:

```html
<link rel="import" href="bower_components/d2l-icons/tier1-icons.html">
<button is="d2l-image-action" icon="d2l-tier1:print">Print</button>
```

You can also create your own custom icon set -- simply follow [Polymer's documentation](https://github.com/PolymerElements/iron-iconset-svg).

### Groups of image-actions

Often, multiple image-actions will appear together as a group. In order to properly space the actions out, wrap them in a `<d2l-image-action-group>` custom element:

```html
<d2l-image-action-group>
	<d2l-image-action-button>Action 1</d2l-image-action-button>
	<d2l-image-action-link>Action 2</d2l-image-action-link>
	<d2l-image-action-button>Action 3</d2l-image-action-button>
</d2l-image-action-gorup>
```

## Developing, Testing and Contributing

After cloning the repo, run `npm install` to install dependencies.

If you don't have it already, install the [Polymer CLI](https://www.polymer-project.org/2.0/docs/tools/polymer-cli) globally:

```shell
npm install -g polymer-cli
```

To start a [local web server](https://www.polymer-project.org/2.0/docs/tools/polymer-cli-commands#serve) that hosts the demo page and tests:

```shell
polymer serve
```

To lint ([eslint](http://eslint.org/) and [Polymer lint](https://www.polymer-project.org/2.0/docs/tools/polymer-cli-commands#lint)):

```shell
npm run lint
```

[bower-url]: http://bower.io/search/?q=d2l-image-action
[bower-image]: https://badge.fury.io/bo/d2l-image-action.svg
[ci-url]: https://travis-ci.org/BrightspaceUI/image-action
[ci-image]: https://travis-ci.org/BrightspaceUI/image-action.svg
