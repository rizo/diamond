# Enlightenment Foundation Libraries

The Enlightenment Foundation Libraries, or EFL, is a set of open source graphical software libraries that grew out of the Enlightenment window manager project and is developed by Enlightenment.org with some sponsorship from Samsung, Profusion and Free.fr.[1] The project's focus is to make the EFL a flexible yet powerful and easy to use set of tools to extend the capabilities of both the Enlightenment window manager and other software projects based on the EFL. The libraries were created for version 0.17 of the window manager. The libraries are meant to be portable and optimized to be functional even on devices such as PDAs.

## Core components

### Evas

Evas is the EFL canvas library, for creating areas, or windows, that applications can draw on in an X Window System. The EFL uses hardware-acceleration where possible to allow it to work faster, but is also designed to work on lower-end hardware, falling back to lower color and quality for graphics if necessary. Unlike most canvas libraries, it is primarily image-based (as opposed to vector-based) and fully state-aware (the vast majority of canvases are stateless, requiring the programmer to keep track of state).

### Edje

Edje is a library that attempts to separate the user interface from the application. It allows applications to be skinnable, so that it is possible to change the GUI of an application without changing the application itself. Edje-based applications use files which contain the specifications for the GUI layout that is to be used. Edje themes are contained using EET generated files.

### Ecore

Ecore is an event abstraction, and modular convenience library, intended to simplify a number of common tasks. It is modular, so applications need only call the minimal required libraries for a job. Ecore simplifies working with X, Evas, and also a few other things, such as network communications and thread.

### Embryo

Embryo implements a scripting language used by other parts of the EFL, such as Edje. The language has a C-like syntax, and was based on the SMALL language.

### EET

EET is a library that is designed to store and load all type of data, locally or through a network stream. It is designed to be light-weight, efficient and quick. EET forms the basis of theme files in the EFL, i.e. if you want to install a theme for Enlightenment or another themable EFL app, you would be installing an EET-format file, which contains all of the theme graphics and configuration and do not need to be extracted onto the filesystem in order to be used.

It is also the basis for all IPC communication and all configuration. Even if it's a binary file format, it is possible to dump/undump it on the fly to see what's going from a human point of view.

### Eina

Eina is the base library of all data types used by the EFL. It is designed to reduce CPU use as much as possible without using too much memory. It provides list (and inlined list), hash, red-black tree, shared string, rectangle, array, iterator and accessor, memory pool, module, fixed point and magic check helper.

The library itself is small and could easily be used without any other EFL libraries.

## Helper components

### Ethumb

Ethumb is a library for creating thumbnails of many types of images, designed to be compliant with freedesktop.org's Thumbnail Managing Standard. Epsilon supports all of the file formats that Evas supports, including PNG, JPEG , TIFF, GIF, etc.

### Emotion

Emotion is a library providing video-playing capabilities through the use of smart-objects. Emotion provides several video backends. The best-supported one is libxine, a well-established video-playing library, but gstreamer and vlc backends are also provided. Thus, Emotion supports all of the video formats that video libraries support, including Ogg Theora, DivX, MPEG2, etc.

### Elementary

Elementary is a widget set based on the EFL that makes heavy use of Evas and Edje to provide a fast, stable, and scalable library that can be used to create both rich and fast applications that can be used on anything from every day desktop computers to small PDA's and set-top boxes. It is designed to fully expose the capability of the EFL.

### EIO

EIO provide asynchronous file system operation, like listing the content of directory, copying and moving directory and files around. It rely on Ecore thread ability and prevent if correctly used any lock in the interface when browsing local file content.

## Defunct/deprecated EFL components

* ETK (Not maintained anymore and job's better done by Elementary)
* EWL (Not maintained anymore and job's better done by Elementary)
* EWD (features now added to Ecore)
* Estyle (features have been absorbed by Etox)
* Etox (obsolete)
* Ebits (replaced by Edje)
* Evoak (dead)
* Imlib2[citation needed]
* EDB (replaced by EET)
* EXML
* EPEG (feature obsoleted by Evas)
* Epsylon (replaced by Ethumb)
* Engrave (feature have been absorbed by Edje)
* Esmart (Not maintained and job's better done by Elementary)

## EFL-based applications

* engage: an engaging Mac OS X-style taskbar
* elicit: a color-picking tool for graphic designers
* evidence: a file manager (no longer strictly necessary now that EFM is stable enough to use)
* entice: an enticing image viewer
* entrance: an entrancing login manager
* express: an instant messaging client
* euphoria: an XMMS2 front-end
* erss: a desktop RSS feed reader
* Enlightenment: the X window manager
* examine: an application configuration program
* iconbar: like engage
* enotes: a desktop sticky-note program
* equate: a desktop calculator
* eke: an RSS feed aggregator
* envision: a video-player front-end
* elation: a DVD-player front-end
* embrace: a mail checker
* elapse : an enlightenment clock
* elinguish: a BitTorrent client
* eclips: possibly defunct
* Exhibit: An EFL/Etk-based image viewer
* E-Stickies: An EFL/Etk-based sticky notes app
* Extrackt: An EFL/Etk-based CD ripper and encoder
* Edje-Editor: An EFL/Etk-based Edje file editor and designer
* Enity: An Etk-based tool to create quick apps using scripts
* Canola 2: a multimedia application for Internet tablets
* ePeriodique: An Elementary-based periodic table of elements

Most of the above programs are available only in CVS and are not complete or stable.

## References

[1]: http://enlightenment.org/p.php?p=about/sponsors&l=en

## External links

[Documentation of EFL](http://web.enlightenment.org/p.php?p=docs&l=en)
[Wiki page with diagrams on trac.enlightenment.org](http://trac.enlightenment.org/e/wiki/EFLOverview)