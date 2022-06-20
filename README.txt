A quick guide:

1. Open the .mfa file with Clickteam Fusion 2.5 (equivelant or better)
2. While in the program, choose the "Main" frame, and run it
3. You can zoom in and out of the fractal, by clicking left and right mouse
buttons respectively

Your program must have the following extensions (tho you should have them by default):
- kcdraw.mfx (Draw object)
- kcwctrl.mfx (Window Control object)


Changing formula:

1. Go into either event editor, or event list editor
2. Under line 29, there should be 5 event groups:
	- Mandelbrot
	- Celctic fractal
	- Burning ship
	- Mandelbrot heart
	- Mandelbrot paprika
3. To change formula, simply activate one of the groups, 
while deactivating others

Make sure, that only one group of events is activated before
running the program (otherwise you risk freezing your pc).



Changing parameters:

In the frame editor, there are few active objects, whose
alterable variables mandate the basic functions of the program.

Not all of them are settings; some carry variables needed for
calculations and whatnot. Also, not all of them should be
tempered with, as they may cause logic errors.

For selected objects and values, you may change:

Visuals:
	ScanBuffor (default 1) - determines the length of gaps between rendering lines. Having more than one, causes program to not complete the final rendered "photo" of the set.
	DesignatedResolution (default 1) - determines at what resolution, should the final photo of the set be rendered.

DrawingSettings:
	Resolution (default 128) - determines at what resolution, the set will be rendered. Doesn't do much; since after rendering, another photo will be rendered with greater resolution (until a photo with DesignatedResolution resolution will be rendered)
	SampleRates (default 200) - iterations, at which the stability of certain point on the set will be determined. The greater the SampleRates, the greater processing power needed for rendering. SampleRates are dynamically reseted with each zoom in/out (look at the lines 62, 63, and 66)
	RenderSpeed (default 1000) - amount of pixels, for which the set is rendered in one centisecond



Changing rendering systems:

There are two rendering systems, located in two event groups.
In order to switch between them, one group must be active, while
other deactivated.

PixelatedPreview (line 17)
It draws the lower resolution photos first; with each photo, it
increases the resolution, until DesignatedResolution is met.
After rendering photo in DesignatedResolution, rendering processes
are halted.

Plotter (line 22)
The first, and now obsolete rendering system. It draws photos
in their DesignatedResolution right away, and has no code,
that would halt rendering processes.