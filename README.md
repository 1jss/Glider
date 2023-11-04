This repository contains a Javascript port of John Calhoun's excellent classic Mac game Glider 4.0. The original Pascal source files for this game can be found here:
https://github.com/softdorothy/glider_4

The Javascript version is more or less a staight copy of the Pascal code. I have not bothered with the demo mode and have added some features such as a cheat mode with infinite lives etx and initial room selection. 

There will be some subtle differences caused by timing - the JS version relies on requestAnimationFrame for timing, whereas the Pascal version uses TickCount() and busy waiting in many places. Also, the Quickdraw and HTML5 Canvas primitives have some subtle differences at the edges.

Houses from John Calhoun's repo can be selected. The Hands of house does not work as designed, probably because of timing differences which I have not bothered to track down.

The original made extensive use of offscreen bitmaps for moving around things like balloons, toast, and fish. I tried to replicate this using an offscreen canvas, but it actually turned out to be slower than re-drawing the entire frame every time, especially in Safari, so I ended up doing this instead.

The original makes extensive use of Pascal with statements for structure members. I have tried to specify member variables explicitly, but may have missed a few, resulting in inadvertent creation of global variables. I have also had some problems caused by assigning reference variables such as Rect rather than taking a copy. A few of these may remain.
