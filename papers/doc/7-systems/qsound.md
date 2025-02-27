# Capcom QSound (DL-1425)

This chip was used in Capcom's CP System Dash, CP System II and ZN arcade PCBs.

It supports 16 PCM channels and uses the patented (now expired) QSound stereo expansion algorithm, as the name implies.

Because the chip lacks sample interpolation, it's recommended that you try to play samples at around 24038 Hz to avoid aliasing. This is especially important for e.g. cymbals.

The QSound chip also has a small echo buffer, somewhat similar to the SNES, although with a very basic (and non-adjustable) filter. It is however possible to adjust the feedback and length of the echo buffer. The initial values can be set in the "Configure system" dialog.

There are also 3 ADPCM channels, however they cannot be used in Furnace yet. They have been reserved in case this feature is added later. ADPCM samples are limited to 8012 Hz.

# effects

- `08xx`: Set panning. Valid range is 00-20. 00 for full left, 10 for center and 20 for full right. It is also possible to bypass the QSound algorithm by using the range 30-50.
- `10xx`: Set echo feedback level. This effect will apply to all channels.
- `11xx`: Set echo level.
- `3xxx`: Set the length of the echo delay buffer.
