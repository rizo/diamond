

## Quartz (graphics layer)

Quartz specifically refers to a pair of Mac OS X technologies, each part of the Core Graphics framework: Quartz 2D and Quartz Compositor. It includes both a 2D renderer in Core Graphics and the composition engine that sends instructions to the graphics card. Because of this vertical nature, Quartz is often interchanged synonymously with Core Graphics.[1]
In a more general sense, the term Quartz or Quartz technologies can refer to almost every part of the Mac OS X graphics model from the rendering layer down to the compositor. In this use, the term covers Core Image and Core Video as well.[2]

### Quartz 2D & Quartz Compositor

Quartz 2D is the primary two-dimensional (2D) text and graphics rendering library: It directly supports Aqua by displaying two-dimensional graphics to create the user interface, including on-the-fly rendering and anti-aliasing. Quartz can render text with sub-pixel precision; graphics are limited to more traditional anti-aliasing, which is the default mode of operation but can be turned off.[3] In Mac OS X v10.4, Apple introduced Quartz 2D Extreme, which allows Quartz 2D to use supported GPUs for rendering. In Mac OS X 10.4, Quartz 2D Extreme is not enabled by default, because it may lead to video redraw issues or kernel panics.[4] As of Mac OS X v10.5 Quartz 2D Extreme has been renamed to QuartzGL - however it still remains disabled by default, as there are some situations where it can degrade performance, or experience visual glitches; it is a per-application setting which can be turned on if the developer wishes.
Quartz Compositor is the compositing engine used by Quartz 2D and other renderers, such as OpenGL, Core Image, and QuickTime. In Mac OS X 10.2 and later, Quartz Compositor uses the processors (GPUs) on supported graphics cards to vastly improve composition performance. This technology is known as Quartz Extreme, and is enabled automatically on systems with supported graphics cards.[5]
[edit]Use of PDF

It is widely stated that Quartz "uses PDF" internally (notably by Apple in Quartz's early developer documentation[6]), often by people making comparisons with the Display PostScript technology used in NeXTSTEP (of which Mac OS X is a descendant) and OPENSTEP. Quartz's internal imaging model correlates well with the PDF object graph, making it easy to output PDF to multiple devices.[7]
[edit]


## Quartz Compositor

Quartz Compositor is the windowing system in Mac OS X. It is responsible for presenting and maintaining rasterized, rendered graphics from the rest of the Core Graphics framework and other renderers in the Quartz technologies family. Internally, it is also known as WindowServer.[1]

Quartz Compositor is the sole facilitator for the placement of rendered bitmaps into the memory of the graphics card. The bitmap output from Quartz 2D, OpenGL, Core Image, QuickTime, or other process is written to a specific memory location, or backing store. The Compositor then reads the data from the backing stores and assembles each into one image for the display, writing that image to the frame buffer memory of the graphics card. Quartz Compositor only accepts raster data, and is the only process that can directly access the graphics frame buffer.[2]
In managing individual windows, Quartz Compositor accepts a bitmap image of the window's contents from its renderer, along with its position. The choice of the renderer is up to the individual application, although most use Quartz 2D. Quartz Compositor then acts as a "visual mixing board," by adding the given window to the whole scene for the display.
In its role as window manager, Quartz Compositor also has an event queue which receives events, such as key strokes and mouse clicks. The Quartz Compositor takes the events from the queue, determines which process owns the window where the event occurred, and passes the event on to the process.[3]


Quartz Extreme

Mac OS X v10.2 introduced Quartz Extreme: graphics processor (GPU) acceleration for the Quartz Compositor. With Quartz Extreme, no central processor (CPU) cycles are utilized for scene composition. Quartz Compositor runs using the graphics processor (GPU) by encapsulating each rendered backing store in an OpenGL texture map or surface. The GPU then composes the surfaces and maps to provide the final image, which is delivered to its frame buffer.
Quartz Extreme only uses OpenGL commands, and requires a graphics card connected to an AGP 2X or faster bus (including AGP 4X, 8X, and PCI Express), supporting textures and maps of arbitrary size, since many of the renderers have no size limitation (Quartz 2D for example).[2] It is automatically enabled on Mac systems with one of the following types of graphics cards:[4]
AMD (ATI) Radeon, AGP-based, 16MB VRAM minimum, or better
NVIDIA GeForce2 MX, 16MB VRAM minimum, or better
[edit]QuartzGL

QuartzGL (called Quartz 2D Extreme when it was introduced in Mac OS X Tiger) is GPU acceleration for the Quartz 2D API. As of Mac OS X Snow Leopard, it is still not enabled by default. However, it has been possible to enable it, using the Quartz Debug application included in the Apple Developer Tools. QuartzGL will be disabled once again upon quitting the Quartz Debug utility. A workaround is to force quit the Quartz Debug application, which will leave QuartzGL enabled system-wide.
All graphics cards capable of supporting Core Image also support QuartzGL.
As of August 2011, no non Apple web browser fully support GPU hardware acceleration based QuartzGL for rendering contents. [5] Firefox 12.0 will support hardware acceleration on OSX 10.7/10.6. [6] Mac OS X 10.7, however, includes an edition of the Safari browser with full hardware acceleration support.


## Quartz 2D

Quartz 2D is the primary two-dimensional graphics rendering API for Mac OS X, part of the Core Graphics framework.

### Overview

Quartz 2D is available to all Mac OS X application environments, and provides resolution-independent and device-independent rendering of bitmap graphics, text, and vectors both on-screen and in preparation for printing. Its responsibilities within the graphics layer include:[1]
Rendering text using Apple Type Services (ATS)
Displaying, manipulating, and rendering PDF documents
Converting PostScript data to PDF data, and vice-versa
Displaying, manipulating, and rendering bitmap images via ImageIO
Providing color management via ColorSync
Displaying the elements of the Aqua user interface
[edit]Drawing in Quartz 2D

Quartz 2D expands the drawing functions associated with QuickDraw. The most notable difference is that Quartz 2D eliminates output device and resolution specificity.
The drawing model utilized by Quartz 2D is based on PDF specification 1.4.[2] Drawing takes place using a Cartesian coordinate system, where text, vectors, or bitmap images are placed on a grid.[3] However, drawing output is not sent directly to the output device. Quartz 2D uses graphics contexts, environments in which drawing takes place. Each graphics context defines how the drawing should be presented: in a window, sent to a printer, an OpenGL layer, or off-screen. Each context rasterizes the drawing at the desired resolution without altering the data that defines the drawing. Thus, contexts are the mechanism by which Quartz 2D employs resolution- and device-independence. For example, a window context may rasterize an object to the appropriate screen resolution to create actual graphics on the display. The same object can be sent to a printing context at a much higher resolution. This permits the same graphics commands to yield output on any device using the most appropriate resolution.[4]

### History

Quartz 2D is similar to NeXT's Display PostScript in its use of contexts. It first appeared as the 2D graphics rendering library called Core Graphics Rendering; along with Core Graphics Services (Compositing), it was wrapped into the initial incarnation of Quartz.[5] Quartz (and its renderer) were first demonstrated at WWDC in May 1999.[6]
Presently, the name Quartz 2D more precisely defines the 2D rendering capabilities of Core Graphics (Quartz). With the release of Mac OS X 10.2, marketing attention focused on Quartz Extreme, the composition layer, leaving the term "Quartz" to refer to the Core Graphics framework or just its 2D renderer. Presently, Quartz technologies can describe all of the rendering and compositing technologies introduced by Mac OS X (including Core Image for example).
Prior to Mac OS X 10.4, QuickDraw rendering outperformed that of Quartz 2D. Mac OS X 10.4 rectified this, substantially increasing the standard rendering performance of Quartz 2D. Mac OS X 10.4 also introduced Quartz 2D Extreme: optional graphics processor (GPU) acceleration for Quartz 2D, although it is not an officially supported feature. Quartz 2D Extreme is disabled by default in Mac OS X 10.4 because it may lead to video redraw issues or kernel panics.[7] In Mac OS X 10.5, Quartz 2D Extreme was renamed QuartzGL.

Quartz 2D is an advanced, two-dimensional drawing engine available for iOS application development and to all Mac OS X application environments outside of the kernel. Quartz 2D provides low-level, lightweight 2D rendering with unmatched output fidelity regardless of display or printing device. Quartz 2D is resolution- and device-independent; you don’t need to think about the final destination when you use the Quartz 2D application programming interface (API) for drawing.

The Quartz 2D API is easy to use and provides access to powerful features such as transparency layers, path-based drawing, offscreen rendering, advanced color management, anti-aliased rendering, and PDF document creation, display, and parsing.

The Quartz 2D API is part of the Core Graphics framework, so you may see Quartz referred to as Core Graphics or, simply, CG.

This document is intended for iOS and Mac OS X developers who need to perform any of the following tasks:

Draw graphics
Provide graphics editing capabilities in an application
Create or display bitmap images
Work with PDF documents

	