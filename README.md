# OSX
I got this version to work on my OSX. I choose an arbitrary old version of gtkwave that still had the gtkwave3-gtk3 folder. Newer versions may work I haven't tried.

## Versions
* OSX Sonoma 14.6.1
* based on gtkwave at 7b972229b3b674a97702ff63064f714e69b53bb9 (Nov 2022)

# Steps
```
brew install gtk+3 gtk-mac-integration tcl-tk xz automake
# git clone
cd gtkwave3-gtk3/
./autogen.sh
./configure --enable-gtk3 --prefix=$(pwd)/myinstall --enable-struct-pack "CFLAGS=-I$(brew --prefix)/include -O2 -g" LDFLAGS=-L$(brew --prefix)/lib --no-create --no-recursion --with-tcl=$(brew --prefix)/opt/tcl-tk/lib --with-tk=$(brew --prefix)/opt/tcl-tk/lib
./config.status
make -j4
make install
./myinstall/bin/gtkwave
```

## References
* https://www.reddit.com/r/FPGA/comments/16tqja3/gtkwave_on_macos_sonoma/



# GTKWave
GTKWave is a fully featured GTK+ based wave viewer for Unix and Win32 which reads LXT, LXT2, VZT, FST, and GHW files as well as standard Verilog VCD/EVCD files and allows their viewing.

This repository contains two versions of GTKWave:
* [`gtkwave3-gtk3`](/gtkwave3-gtk3) with support for GTK+ 2 and GTK+ 3
* [`gtkwave3`](/gtkwave3) with support for GTK+ 1 and GTK+ 2
