
# GTK+ on OS X


## Integration Library
After the deprecation of the Carbon, the GTK+ started using the Cocoa implementation of the integrtion library -- GtkOSXApplication.

GtkOSXApplication is fully documented via [gtk-doc].

[gtk-doc]: http://gtk-osx.sourceforge.net/ige-mac-integration/

## Theming

The gtk-quartz-engine provided a more mac-like appearance to applications windows, but it had some major holes in what it rendered. Unfortunately, it is based on Carbon's HITheme interface (and parts of it still use the even-more-deprecated AppearanceManager). We can't recommend that you use it, and because of major changes to the theming architecture it doesn't work in Gtk+-3 (See [Gnome Wiki] for more details).

[Gnome Wiki]: http://live.gnome.org/GTK%2B/OSX/Integration

## Source Code

- Repository to maintain the configurations and modulesets for building GTK+ OS X with jhbuild:  
	`git clone git://git.gnome.org/gtk-osx`

- Create OS X Application Bundles from Gtk Quartz programs:  
	`git clone git://git.gnome.org/gtk-mac-bundler`

- GTK+ Integration for the Mac OS X desktop, like the menubar, dock and app bundles:  
	`git clone git://git.gnome.org/gtk-mac-integration`

- GDK Quartz:
	`http://git.gnome.org/browse/gtk+/tree/gdk/quartz`