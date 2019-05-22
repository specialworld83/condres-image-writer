imagewriter
===========

Utility for writing raw disk images &amp; hybrid isos to USB keys

Linux Installation
===========

    if [ -e /usr/bin/kdesu ]
	  then sed 's/\/usr\/bin\/xdg-su -c \/usr\/bin\//kdesu /' -i $pkgname.desktop
	  else sed 's/\/usr\/bin\/xdg-su -c \/usr\/bin\//xdg-su -s /' -i $pkgname.desktop
	fi
    }
	

Then run

    qmake-qt5 PREFIX="$pkgdir/usr" DEFINES=USEUDISKS2 imagewriter.pro
	make

Linux kiosk mode
===========

The imagewriter also has the capability to be used in "kiosks" that may have external harddrives.  To run in kiosk mode,
which both ignores large hard drives and marks unknown USB sticks as "Condres Image Writer", 
run imagewriter with the -k option.

in order to start the imagewriter with sudo, do the following:

    % xhost +SI:localuser:root

to allow root access to the current screen and then start the program with:
 
    % sudo DISPLAY=:0 imagewriter

