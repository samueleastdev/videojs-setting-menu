# videojs-settings-menu

VideoJS settings menu for Quality, Chapters, Subtitles, Playback rates and more

## Table of Contents

<!-- START doctoc -->
<!-- END doctoc -->
## Installation

```sh
npm install --save videojs-settings-menu
```

## Usage

To include videojs-settings-menu on your website or web application, use any of the following methods.

### `<script>` Tag

This is the simplest case. Get the script in whatever way you prefer and include the plugin _after_ you include [video.js][videojs], so that the `videojs` global is available.

```html
<script src="//path/to/video.min.js"></script>
<script src="//path/to/videojs-settings-menu.min.js"></script>
<script>
  var player = videojs('my-video');

  player.settingsMenu();
</script>
```

### Browserify/CommonJS

When using with Browserify, install videojs-settings-menu via npm and `require` the plugin as you would any other module.

```js
var videojs = require('video.js');

// The actual plugin function is exported by this module, but it is also
// attached to the `Player.prototype`; so, there is no need to assign it
// to a variable.
require('videojs-settings-menu');

var player = videojs('my-video');

player.settingsMenu();
```

### RequireJS/AMD

When using with RequireJS (or another AMD library), get the script in whatever way you prefer and `require` the plugin as you normally would:

```js
require(['video.js', 'videojs-settings-menu'], function(videojs) {
  var player = videojs('my-video');

  player.settingsMenu();
});
```

## License

MIT. Copyright (c) Samuel East


[videojs]: http://videojs.com/
