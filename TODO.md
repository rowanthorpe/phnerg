TODO
====

* for v0.2:
    * Move `## EDIT THESE` variables out of both scripts into a separate
      config file
    * A lot of `camera-mirror` is just copy-pasta that I managed to wrangle
      for a quick result, because I didn't have time to deep-grok all the
      ins-and-outs of wnck/gtk/gdk. There is probably a lot of redundant
      and suboptimal code. Clean it up and trim it down.
    * Get `camera-mirror` to work (feature-equivalence) only using ffmpeg
      (to remove vlc dependency). This first means doing all the window
      manipulations purely from python, not relying on vlc flags.
    * Get lossless-vp9/flac/mkv working (and playing back by something other
      than ffplay) instead of dirac/flac/mkv
