## Options

Passed to the `Sketch.create` method.

* `fullscreen` Default: `true`; when `false`, you can pass `width: 500, height: 500` to specify a size.
* `autostart` Default: `true` Otherwise call `start()`
* `autoclear` Default: `true` Whether to clear the context before each call to `draw`. Otherwise call `clear()`
* `autopause` Default: `true` Whether to pause the animation on window blur and resume on focus
* `container` Default: `document.body` Where to put the sketch context
* `interval` Default: `1` The update / draw interval (`2` will update every 2 frames, etc)
* `globals` Default: `true` Add global properties and methods to the `window`
* `retina` Default: `false` Resize for best appearance on retina displays. Can be slow due to so many pixels!
* `type` Default `Sketch.CANVAS` Possible values: `Sketch.CANVAS`, `Sketch.WEB_GL` and `Sketch.DOM`

## Class Methods

* `create` Creates and returns a new sketch. Arguments: `options` Optional hash including any number of the above options
* `augment` Augments an existing context, giving it sketch properties and functionality. This is called internally by `create` once a new context is created. Arguments: `context` The context to augment
* `install` Installs sketch globals into the context provided. This is called internally by `create` on `self` unless the `globals` flag is set to `false`. Arguments: `context` The context to install globals into

## Instance Methods

* `start`
* `stop`
* `toggle`
* `clear`
* `destroy`

## Overridable Instance Methods

Implement these methods on your sketch instance (or pass them to `create` inside the `options` hash).

* `setup`
* `update`
* `draw`
* `touchstart`
* `touchmove`
* `touchend`
* `mouseover`
* `mousedown`
* `mousemove`
* `mouseout`
* `mouseup`
* `click`
* `keydown`
* `keyup`
* `resize`

## Instance Properties

* `mouse` Contains `x`, `y`, `ox`, `oy`, `dx` and `dy`, representing the mouse or primary touch.
* `touches` List of current touches with same structure as `mouse`. On the desktop, the 0th element represents the mouse.
* `dragging` Whether the mouse is down / the user is dragging
* `running` Whether the animation loop is running (modified by the `start` and `stop` methods)
* `width` Current viewport width
* `height` Current viewport height
* `keys` A hash of booleans indicating whether each key is currently pressed, e.g `sketch.keys.SPACE`
* `millis` The total runtime of the sketch in milliseconds
* `now` The current time in milliseconds
* `dt` The delta time between the current and previous frame in milliseconds

## Constants

* `CANVAS` Enumeration for the Canvas `type`
* `WEBGL` Enumeration for the WebGL `type`
* `DOM` Enumeration for the DOM `type`
* `instances` A list of all current Sketch instances

## Global Properties

These are safely mixed into the window object for quick access, e.g: `sin( random( TWO_PI ) )`. You can prevent this happening by passing `globals:false` when calling `create` and/or add this properties to any object yourself by calling `Sketch.install( context )`

### Methods

* `random` Accepts single values, ranges and Arrays, e.g: `random( 10, 20 )` or `random( colours )`
* `lerp` Arguments: `min` `max` `amount`. Interpolate between `min` and `max` by the factor `amount`
* `map` Arguments: `num` `minA` `maxA` `minB` `maxB`. Map `num` from the range `minA`/`maxA` to the range `minB`/`maxB`

### Math Constants

* `PI`
* `TWO_PI`
* `HALF_PI`
* `QUARTER_PI`
* `E`
* `LN10`
* `LN2`
* `LOG2E`
* `LOG10E`
* `SQRT1_2`
* `SQRT2`

### Math functions

* `abs`
* `acos`
* `asin`
* `atan`
* `ceil`
* `cos`
* `exp`
* `floor`
* `log`
* `round`
* `sin`
* `sqrt`
* `tan`
* `atan2`
* `pow`
* `max`
* `min`