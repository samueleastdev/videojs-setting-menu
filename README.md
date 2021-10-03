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
<script src="node_modules/video.js/dist/video.js"></script>
<script src="node_modules/videojs-contrib-quality-levels/dist/videojs-contrib-quality-levels.js"></script>
<script src="node_modules/@samueleastdev/videojs-dash-hls-bitrate-switcher/dist/videojs-dash-hls-bitrate-switcher.js"></script>
<script src="dist/videojs-settings-menu.js"></script>
<script>
  (function (window, videojs) {
    var examplePlayer = (window.examplePlayer = videojs("vp", {
      techOrder: ["html5"],
      html5: {
        hls: {
          overrideNative: true,
          cacheEncryptionKeys: true,
        },
      },
      plugins: {
        dashHlsBitrateSwitcher: {
          support: "both",
        },
        settingsMenu: {
          items: [
            "AudioTrackButton",
            "ChaptersButton",
            "SubsCapsButton",
            "PlaybackRateMenuButton",
            "RatesButton",
          ],
          languages: {
            settings: "Settings",
            loading: "Loading",
            back: "Back",
            captions_off: "Captions Off",
            default_audio: "Default Audio",
            audio: "Audio",
            subtitles: "Subtitles",
            chapters: "Chapters",
            speed: "Speed",
            quality: "Quality",
          },
        },
      },
      crossOrigin: "anonymous",
      liveui: true,
      autoplay: true,
      muted: true,
      playbackRates: [0.25, 0.5, 0.75, 1, 1.25, 1.5, 1.75, 2],
      nativeControlsForTouch: false,
    }));

    document.getElementById("switch").addEventListener("click", (_evt) => {
      examplePlayer.src({
        src: "https://d2zihajmogu5jn.cloudfront.net/bipbop-advanced/bipbop_16x9_variant.m3u8",
        type: "application/x-mpegURL",
      });
    });
  })(window, window.videojs);
</script>
```

### Browserify/CommonJS

When using with Browserify, install videojs-settings-menu via npm and `require` the plugin as you would any other module.

```js
var videojs = require("video.js");

// The actual plugin function is exported by this module, but it is also
// attached to the `Player.prototype`; so, there is no need to assign it
// to a variable.
require("videojs-settings-menu");

var player = videojs("my-video");

player.settingsMenu();
```

### RequireJS/AMD

When using with RequireJS (or another AMD library), get the script in whatever way you prefer and `require` the plugin as you normally would:

```js
require(["video.js", "videojs-settings-menu"], function (videojs) {
  var player = videojs("my-video");

  player.settingsMenu();
});
```

## License

MIT. Copyright (c) Samuel East

[videojs]: http://videojs.com/
