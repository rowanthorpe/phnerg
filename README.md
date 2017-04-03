phnerg
======

A tool to record your desktop to a timestamp-named `matroska` file with
lossless `dirac` and `flac` codecs, with optional draggable camera-mirror
during recording, as efficiently as possible.

This is most useful when you want low-resource-consuming lossless realtime
recording for later editing and/or high-quality lossy compression using
multiple passes, as opposed to mediocre realtime lossy compression and/or
generational loss due to lossy de/encoding when editing. Due to that (and
using `ffmpeg` for grabbing, minimal `python`/`gtk` for launching `cvlc`
camera-mirror) it uses minimal resources and reduces the risk of dropped
frames.

`webm` container format was not used as it only supports lossy audio codecs
(`vorbis` and `opus`). As `webm` is just a subset/profile of `matroska`, I
attempted encoding `vp9` (`webm`'s best video codec) in lossless-mode with
`flac` audio to `matroska`, but had many obscure problems with creation and
viewing, so have stuck with `dirac` for video for now.

Quick Start
-----------

* Copy `phnerg` to somewhere in your `$PATH`
* If you intend to use the camera-mirror functionality (default):
    * Ensure python3 is installed
    * Copy `camera-mirror` to the same directory as `phnerg`
* edit both files to modify the `## EDIT THESE` variables to your liking
* run phnerg with any of the following args if you need them:
    * dual: record dual-screen instead of just primary
    * mono: record single audio channel instead of stereo
    * nocamera: don't launch a camera-mirror
    * noscale: don't scale the image down, use native resolution (generally
      this will create enormous files)

License
-------

Copyright © 2017 Rowan Thorpe <rowan@rowanthorpe.com>

`phnerg` uses the GPLv3 license, check the COPYING file.

Any additional contributions are noted in the AUTHORS.md file.

Tips
----

* If doing CPU-intensive stuff while recording on a laptop, you may need to
  either use an external microphone placed at least a few inches away from it
  (or mute your microphone if you don't need to record external sound) to avoid
  the sound of the fans drowning out other sound.
* `camera-mirror` can be run standalone (just run it from the commandline with
  no args).