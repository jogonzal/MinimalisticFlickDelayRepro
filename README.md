# MinimalisticFlickDelayRepro
Minimalistic repro for "mousedown delay" in <canvas> issue in Microsoft Surface (Repro's in Chrome/Firefox)

Repro
----
1. Open index.html
2. On a Surface Pro 3 or 4, in Chrome or Firefox, try inking from left to right quickly

Expected
----
The inking is fluid

Actual
----
The inking is not fluid because the browser app is subscribed to "flick" events described here:
https://msdn.microsoft.com/en-us/library/ms703447%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396

This does not repro in IE or Edge. In fact, those browsers have turned off support for flick gestures completely. My opinion is Chrome and Firefox should do the same.

How to fix it
----
This can only be fixed in Firefox/Chrome code by disabling flicks in chrome and firefox (either completely or in a canvas element). The links above and below provides documentation on how to disable this behavior.
https://social.msdn.microsoft.com/Forums/windowsdesktop/en-US/8325ddd8-53df-49b7-ad78-525e4005464b/how-to-disableenable-pen-flicks-programatically?forum=tabletandtouch
