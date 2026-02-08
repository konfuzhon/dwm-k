# dwm-k
## kon's simple nord dynamic window manager
(eww, it's X11)

## Requirements
In order to build dwm you need the Xlib header files.

Void
```bash
sudo xbps-install -S base-devel xorg xinit libX11-devel libXft-devel libXinerama-devel libXrandr-devel
```

## Installation
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root)
```bash
make clean install
```

## Running dwm
Add the following line to your .xinitrc to start dwm using startx
```bash
exec dwm
```

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.
```bash
DISPLAY=foo.bar:1 exec dwm
```

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc
```bash
while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
do
sleep 1
done &
exec dwm
```

## Configuration
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.

To do this, do the following
```bash
cd <containing directory of dwm source>
rm -f config.h
vi config.def.h # Or a text editor of your choice
```
