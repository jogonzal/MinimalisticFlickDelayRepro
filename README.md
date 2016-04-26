# MinimalisticFlickDelayRepro
Minimalistic repro for "mousedown delay" in <canvas> issue in Chrome/Firefox when using the Microsoft Surface Stylus

Repro
----
1. Open index.html
2. On a Surface Pro 3 or 4, in Chrome or Firefox, try inking from left to right quickly with the stylus
		You can also try inking in a curve to notice the missing dots
3. For a video of this behavior, see the video attached (ReproChrome.mp4, ReproFireFox.mp4)

Expected
----
The inking is fluid

Actual
----
The inking is not fluid - the mousedown event is delayed an a significant number of mousemove events are missing.
Flick events show up when inking in the canvas. because the browser app is subscribed to "flick" events described here:
https://msdn.microsoft.com/en-us/library/ms703447%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396

This does not repro in IE or Edge. In fact, those browsers have turned off support for flick gestures completely. My opinion is Chrome and Firefox should do the same.

How to fix it
----
This can only be fixed in Firefox/Chrome code by disabling flicks in chrome and firefox (either completely or in a canvas element). The links above and below provides documentation on how to disable this behavior.
https://social.msdn.microsoft.com/Forums/windowsdesktop/en-US/8325ddd8-53df-49b7-ad78-525e4005464b/how-to-disableenable-pen-flicks-programatically?forum=tabletandtouch
