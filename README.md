# AngularJS Theme Switcher

## Features

* Add option to select themes in your angular application
* Configurable via app configuration.

## Demo

Check out angular-themer in action at the <a href="http://fdomig.github.io/angular-themer">demo page</a>.

## Installation

You can install angular-themer with:

`bower install angular-themer`

Alternatively you could download the `src` folder manually and include it in your project.

````
<html>
	<head>
	    <title>angular-themer demo</title>
    	<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.2.1/angular.js"></script>
    	<script src="../src/themer.js"></script>
    	<!-- Include selected theme -->
    	<link themer-link>
	</head>
	<body>
		...
		<!-- include switcher element -->
    	<div themer-switcher></div>
		...
	</body>
	</head>
</html>
````
In your module, add themer dependency and configure.

````
angular.module('yourModule', ['angular-themer'])
	.config(['themerProvider', function (themerProvider) {
		var styles = [
			{ key: 'DARK', label: 'Dark Theme', href: 'dark.css'},
			{ key: 'LIGHT', label: 'Light Theme', href: ['light.css', 'fonts.css']}
		];
		themerProvider.setStyles(styles);
		themerProvider.setSelected(styles[0].key);
	}])
;
````

The `href` property can be either a string for a single css file or an array of strings for
multiple css files.

## Changelog

### 0.2.2

* Removed `setSelected()`; added `setSelected(key)` instead
* Added `key` to each style
* Added watchers to watch internal changes

### 0.2.1

* First usable version
* Configuration at bootstrap