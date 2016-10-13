**Looking for SASS-based `d2l-image-action`?** It's [over here](https://github.com/BrightspaceUI/image-action/tree/sass).

# d2l-image-action
[![Bower version][bower-image]][bower-url]
[![Build status][ci-image]][ci-url]

A [Polymer](https://www.polymer-project.org/1.0/)-based web component for D2L image actions, which are buttons (or links) associated with an image that perform an action when clicked.

![screenshot of image actions](/screenshot.png)

For further information on this and other D2L UI components, see the docs at [ui.valence.d2l.com](http://ui.valence.d2l.com/).

## Installation

`d2l-image-action` can be installed from [Bower][bower-url]:
```shell
bower install d2l-image-action
```

## Usage

Include the [webcomponents.js](http://webcomponents.org/polyfills/) "lite" polyfill (for browsers who don't natively support web components), then import `d2l-image-action.html`:

```html
<head>
	<script src="https://s.brightspace.com/lib/webcomponentsjs/0.7.21/webcomponents-lite.min.js"></script>
	<link rel="import" href="../d2l-image-action/d2l-image-action.html">
</head>
```

The native `<button>` element can now be extended to become an image-action:

```html
<button is="d2l-image-action">Print</button>
```

### Icons

As their name suggests, image-actions are intended to be used with an icon, specifically one which is `18px` by `18px` in size. To set the icon, use the `icon` attribute, which takes a reference to a [Polymer iron-iconset-svg](https://github.com/PolymerElements/iron-iconset-svg) source.

The [d2l-icons](https://github.com/BrightspaceUI/icons) component exposes all of the D2L icons as `iron-iconset-svg` sources -- simply import them using the `tier1` category (for 18x18 icons) and reference them by key:

```html
<link rel="import" href="../d2l-icons/tier1-icons.html">
<button is="d2l-image-action" icon="d2l-tier1:print">Print</button>
```

You can also create your own custom icon set -- simply follow [Polymer's documentation](https://github.com/PolymerElements/iron-iconset-svg).

### Link-based actions

Most of the time, image-actions are wired up to a `click` event, so the native `<button>` is the most semantically suitable element to use. Sometimes however, you may wish to perform a browser navigation when the action is clicked. In these cases, an anchor (`<a>`) element is more appropriate.

For link-based actions, extend the native `<a>` element with `d2l-image-action-link`:

```html
<a is="d2l-image-action-link"
	href="settings.html"
	icon="d2l-tier1:gear">Settings</a>
```

### Groups of image-actions

Often, multiple image-actions will appear together as a group. In order to properly space the actions out, wrap them in a `<d2l-image-action-group>` custom element:

```html
<d2l-image-action-group>
	<button is="d2l-image-action">Action 1</button>
	<a is="d2l-image-action-link">Action 2</a>
	<button is="d2l-image-action">Action 3</button>
</d2l-image-action-gorup>
```

### Usage in Production

In production, it's recommended to use a build tool like [Vulcanize](https://github.com/Polymer/vulcanize) to combine all your web components into a single import file. [More from the Polymer Docs: Optimize for Production](https://www.polymer-project.org/1.0/tools/optimize-for-production.html)...

## Coding styles

See the [Best Practices & Style Guide](https://github.com/Brightspace/valence-ui-docs/wiki/Best-Practices-&-Style-Guide) for information on naming conventions, plus information about the [EditorConfig](http://editorconfig.org) rules used in this repo.

[bower-url]: http://bower.io/search/?q=d2l-image-action
[bower-image]: https://img.shields.io/bower/v/d2l-image-action.svg
[ci-url]: https://travis-ci.org/BrightspaceUI/image-action
[ci-image]: https://travis-ci.org/BrightspaceUI/image-action.svg?branch=master
