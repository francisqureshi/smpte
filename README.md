# SMPTE Timecode Arithmetic for Zig 0.16.0+

Zig port of https://github.com/IgorRidanovic/smpte

## Frame Rates and Drop Frame

All fractional frame rates are rounded up to the nearest integer since all calculations must use integers. There is no need to specify 23.976 when calculating 23.976 timecode since this is covered by the default 24 value.

In fact, the s.fps = 29.97 in the above example will get rounded to 30, but we use 29.97 in the example for historical consistency and clarity--there is no such thing as 30 fps DF TC.

Remember that all timecode except DF is real time clock inaccurate.

We use Andrew Duncan/David Heidelberger method of calculating the drop frame values. See their excellent article at http://www.andrewduncan.net/timecodes/ and https://www.davidheidelberger.com/2010/06/10/drop-frame-timecode/.
