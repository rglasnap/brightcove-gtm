# Google Tag Manager Plugin for the Brightcove player

*Note this is not compatible with the Brightcove Smart Player which uses a different plugin architecture and API.*

This plugin was adapted from the [Google Analytics plugin for Brightcove Player](https://github.com/BrightcoveOS/videojs-ga-videocloud)

Main changes from the original:

- Aligned progress events with the Smart Player GA plugin
- Sends events and information to the data layer instead of events directly to GA
- Removed support for the iFrame version for now until I'm able to get that working

## Instructions
Go to my website at http://bit.ly/1OY4tcb for full instructions

## Options

Provide options to the plugin in the player configuraiton using `ga` as the name.

####eventNames

Override or localise the names of the event actions.

**default:**
```
{
  "video_load": "Video Load",
  "percent_played": "Percent played",
  "start": "Media Begin",
  "seek_start": "Seek start",
  "seek_end": "Seek end",
  "play": "Media Play",
  "pause": "Media Pause",
  "error": "Error",
  "fullscreen_exit": "Fullscreen Entered",
  "fullscreen_exit": "Fullscreen Exited",
  "resize": "Resize",
  "volume_change": "Volume Change",
  "player_load": "Player Load",
  "end": "Media Complete"
}
```

####videoCategory

This is the ```category``` sent to GTM. 

**default:** ```'Brightcove Player'```

####eventLabel

This is the ```label``` sent to GA. 

**default:** `VIDEO_ID | VIDEO_NAME`.

####eventsToTrack

The events you want to track. For example `start` (playback started for the first time) and `end` are probably more interesting than `play` and `pause`.

**default:**
```
[ 'player_load', 'video_load', 'percent_played', 'start', 'end', 'seek', 'play', 'pause', 'resize', 'volume_change', 'error', 'fullscreen']
```

* `player_load` Player has loaded.
* `video_load` Video has loaded. Will fire again when a new video is loaded.
* `percent_played` Every *x*% of the video, with the percentage as a value, where *x* is defined by `percentsPlayedInterval`. Default is 25.
* `start` Playback has started. Once per video load.
* `end` Playback has completed. Once per video load.

####percentsPlayedInterval

This options goes with the ```percents_played``` event. Every ```percentsPlayedInterval``` percents an event will be sent to GA.

**default:** 25


## TODO

- [ ] Support iFrame version
