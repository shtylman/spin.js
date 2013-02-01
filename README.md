# spin.js

An animated CSS3 loading spinner with VML fallback for IE.

 * No images, no external CSS
 * No dependencies
 * Highly configurable
 * Resolution independent
 * Uses VML as fallback in old IEs
 * Uses @keyframe animations, falling back to setTimeout()
 * Works in all major browsers, including IE6
 * Small footprint (~1.9K gzipped)
 * MIT License

## example

```javascript
var Spinner = require('spin');

var target = document.createElement('div');
target.setAttribute('style', 'height: 60px');

var spinner = new Spinner({
    color:'#ddd',
    lines: 12,
    top: 10,
    left: 10
}).spin(target);

target // =>
```

The `spin()` method creates the necessary HTML elements and starts the animation. If a target element is passed as argument, the spinner is added as first child and horizontally and vertically centered.

## options

The following options are available for the spinner constructor. Shown with their defaults.

```
lines: 13, // The number of lines to draw
length: 7, // The length of each line
width: 4, // The line thickness
radius: 10, // The radius of the inner circle
corners: 1, // Corner roundness (0..1)
rotate: 0, // The rotation offset
color: '#000', // #rgb or #rrggbb
speed: 1, // Rounds per second
trail: 60, // Afterglow percentage
shadow: false, // Whether to render a shadow
hwaccel: false, // Whether to use hardware acceleration
className: 'spinner', // The CSS class to assign to the spinner
zIndex: 2e9, // The z-index (defaults to 2000000000)
top: 'auto', // Top position relative to parent in px
left: 'auto' // Left position relative to parent in px
```

## api

### spin([target])
I called with a target, it will append and center itself into the target. If called without a target, just starts the spinner.

The spinner container is exposed through the `.el` property if you wish to manually add it.

```javascript
var Spinner = require('spin');

// default spinner
var spinner = new Spinner().spin();

var target = document.createElement('div');

// access spinner element with spinner.el
target.appendChild(spinner.el);

target // =>
```

### stop()
Removes the UI elements from the DOM and stops the animation. Stopped spinners may be reused by calling spin() again.

## demo

For an interactive demo and a list of all supported options please refer to the [project's homepage](http://fgnass.github.com/spin.js).
