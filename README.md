## Overview

This program acts as a watchdog timer to start other programs.
The other program must finish within a configurable timeout or
else the other program is killed.

It has been tested on Fedora, RHEL, and Mac OS X.
The source compiles without change on each of these OS's.

## Building

This section includes instructions for building
on both Linux and Mac OS X.

You need EiffelStudio to build this.
I use the GPL version available from http://www.eiffelstudio.com
on x86 and x86_64.

### Linux

1. Install the GPL version of EiffelStudio

    a. Extract the tar ball

    ```
    cd /usr/local
    sudo tar xvjf ~/Download/Eiffel66_gpl_83873-linux-x86-64.tar.bz2
    ```

     b. Modify `~/.bashrc` to include:

    ```
    #START_EIFFELSTUDIO
    export ISE_EIFFEL=/usr/local/Eiffel66
    export ISE_PLATFORM=linux-x86-64
    export PATH=$PATH:$ISE_EIFFEL/studio/spec/$ISE_PLATFORM/bin
    #STOP_EIFFELSTUDIO
    ```

    NOTE: The above `.bashrc` is for the current user. If you would
    prefer to have a system-wide initialization file for the latest
    version of EiffelStudio currently installed, 
    see https://github.com/jumanjiman/workstation/blob/master/bash-profile-scripts/src/eiffel-studio.sh[]

     c. Source `~/.bashrc`

2. Install `rpm-build`
3. Install `tito` from EPEL, Fedora, or https://github.com/dgoodwin/tito[]
4. Change into the `wd` directory and run `tito build --rpm`
5. Win!


### Mac OS X

1. Install Xcode from Apple
2. Install the GPL version of EiffelStudio using Mac Ports
   using the instructions from http://dev.eiffel.com/EiffelOnMac[]

    ```
    [pmorgan@mba02 ~]$ sudo port install eiffelstudio67
    ```

    The installation requires Internet access and takes a long time.
    Sample output while installing:

    ```
    --->  Computing dependencies for eiffelstudio67
    --->  Dependencies to be installed: gtk2 atk glib2 autoconf help2man p5-locale-gettext perl5 perl5.8 m4 automake dbus libtool pkgconfig zlib gtk-doc docbook-xml docbook-xml-4.1.2 xmlcatmgr docbook-xml-4.2 docbook-xml-4.3 docbook-xml-4.4 docbook-xml-4.5 docbook-xml-5.0 docbook-xsl gnome-doc-utils intltool gnome-common p5-getopt-long p5-pathtools p5-scalar-list-utils p5-xml-parser iso-codes libxslt libxml2 py26-libxml2 python26 bzip2 db46 gdbm openssl readline sqlite3 rarian getopt gdk-pixbuf2 jasper jpeg libpng tiff pango Xft2 fontconfig freetype xrender xorg-libX11 xorg-bigreqsproto xorg-inputproto xorg-kbproto xorg-libXau xorg-xproto xorg-libXdmcp xorg-libxcb xorg-libpthread-stubs xorg-xcb-proto xorg-util-macros xorg-xcmiscproto xorg-xextproto xorg-xf86bigfontproto xorg-xtrans xorg-renderproto cairo libpixman shared-mime-info xorg-libXcomposite xorg-compositeproto xorg-libXext xorg-libXfixes xorg-fixesproto xorg-libXcursor xorg-libXdamage xorg-damageproto xorg-libXi xorg-libXinerama xorg-xineramaproto xorg-libXrandr xorg-randrproto xorg-libXtst xorg-recordproto
    --->  Fetching perl5.8
    --->  Attempting to fetch perl-5.8.9.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/perl5.8
    --->  Verifying checksum(s) for perl5.8
    --->  Extracting perl5.8
    --->  Applying patches to perl5.8
    --->  Configuring perl5.8
    --->  Building perl5.8
    --->  Staging perl5.8 into destroot
    --->  Installing perl5.8 @5.8.9_3
    --->  Activating perl5.8 @5.8.9_3
    --->  Cleaning perl5.8
    --->  Fetching perl5
    --->  Verifying checksum(s) for perl5
    --->  Extracting perl5
    --->  Configuring perl5
    --->  Building perl5
    --->  Staging perl5 into destroot
    --->  Installing perl5 @5.8.9_0
    --->  Activating perl5 @5.8.9_0
    --->  Cleaning perl5
    --->  Fetching p5-locale-gettext
    --->  Attempting to fetch gettext-1.05.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/perl5
    --->  Verifying checksum(s) for p5-locale-gettext
    --->  Extracting p5-locale-gettext
    --->  Applying patches to p5-locale-gettext
    --->  Configuring p5-locale-gettext
    --->  Building p5-locale-gettext
    --->  Staging p5-locale-gettext into destroot
    --->  Installing p5-locale-gettext @1.05_3
    --->  Activating p5-locale-gettext @1.05_3
    --->  Cleaning p5-locale-gettext
    --->  Fetching help2man
    --->  Attempting to fetch help2man-1.38.2.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/help2man
    --->  Verifying checksum(s) for help2man
    --->  Extracting help2man
    --->  Configuring help2man
    --->  Building help2man
    --->  Staging help2man into destroot
    --->  Installing help2man @1.38.2_0
    --->  Activating help2man @1.38.2_0
    --->  Cleaning help2man
    --->  Fetching m4
    --->  Attempting to fetch m4-1.4.15.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/m4
    --->  Verifying checksum(s) for m4
    --->  Extracting m4
    --->  Configuring m4
    --->  Building m4
    --->  Staging m4 into destroot
    --->  Installing m4 @1.4.15_2
    --->  Activating m4 @1.4.15_2
    --->  Cleaning m4
    --->  Fetching autoconf
    --->  Attempting to fetch autoconf-2.68.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/autoconf
    --->  Verifying checksum(s) for autoconf
    --->  Extracting autoconf
    --->  Configuring autoconf
    --->  Building autoconf
    --->  Staging autoconf into destroot
    --->  Installing autoconf @2.68_1
    --->  Activating autoconf @2.68_1
    --->  Cleaning autoconf
    --->  Fetching automake
    --->  Attempting to fetch automake-1.11.1.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/automake
    --->  Verifying checksum(s) for automake
    --->  Extracting automake
    --->  Configuring automake
    --->  Building automake
    --->  Staging automake into destroot
    --->  Installing automake @1.11.1_0
    --->  Activating automake @1.11.1_0
    --->  Cleaning automake
    --->  Fetching libtool
    --->  Attempting to fetch libtool-2.4.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/libtool
    --->  Verifying checksum(s) for libtool
    --->  Extracting libtool
    --->  Configuring libtool
    --->  Building libtool
    --->  Staging libtool into destroot
    --->  Installing libtool @2.4_0
    --->  Activating libtool @2.4_0
    --->  Cleaning libtool
    --->  Fetching pkgconfig
    --->  Attempting to fetch pkg-config-0.25.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/pkgconfig
    --->  Verifying checksum(s) for pkgconfig
    --->  Extracting pkgconfig
    --->  Applying patches to pkgconfig
    --->  Configuring pkgconfig
    --->  Building pkgconfig
    --->  Staging pkgconfig into destroot
    --->  Installing pkgconfig @0.25_1
    --->  Activating pkgconfig @0.25_1
    --->  Cleaning pkgconfig
    --->  Fetching dbus
    --->  Attempting to fetch dbus-1.2.24.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/dbus
    --->  Verifying checksum(s) for dbus
    --->  Extracting dbus
    --->  Applying patches to dbus
    --->  Configuring dbus
    --->  Building dbus
    --->  Staging dbus into destroot
    --->  Installing dbus @1.2.24_1
    --->  Activating dbus @1.2.24_1
    
    ############################################################################
    # Startup items have been generated that will aid in
    # starting dbus with launchd. They are disabled
    # by default. Execute the following command to start them,
    # and to cause them to launch at startup:
    #
    # sudo launchctl load -w /Library/LaunchDaemons/org.freedesktop.dbus-system.plist
    # launchctl load -w /Library/LaunchAgents/org.freedesktop.dbus-session.plist
    ############################################################################
    
    --->  Cleaning dbus
    --->  Fetching zlib
    --->  Attempting to fetch zlib-1.2.5.tar.bz2 from http://www.zlib.net/
    --->  Verifying checksum(s) for zlib
    --->  Extracting zlib
    --->  Applying patches to zlib
    --->  Configuring zlib
    --->  Building zlib
    --->  Staging zlib into destroot
    --->  Installing zlib @1.2.5_0
    --->  Activating zlib @1.2.5_0
    --->  Cleaning zlib
    --->  Fetching glib2
    --->  Attempting to fetch glib-2.26.1.tar.bz2 from ftp://ftp.cse.buffalo.edu/pub/Gnome/sources/glib/2.26/
    --->  Verifying checksum(s) for glib2
    --->  Extracting glib2
    --->  Applying patches to glib2
    --->  Configuring glib2
    --->  Building glib2
    --->  Staging glib2 into destroot
    --->  Installing glib2 @2.26.1_0
    --->  Activating glib2 @2.26.1_0
    --->  Cleaning glib2
    --->  Fetching xmlcatmgr
    --->  Attempting to fetch xmlcatmgr-2.2.tar.gz from http://voxel.dl.sourceforge.net/xmlcatmgr
    --->  Verifying checksum(s) for xmlcatmgr
    --->  Extracting xmlcatmgr
    --->  Configuring xmlcatmgr
    --->  Building xmlcatmgr
    --->  Staging xmlcatmgr into destroot
    --->  Installing xmlcatmgr @2.2_1
    --->  Activating xmlcatmgr @2.2_1
    --->  Cleaning xmlcatmgr
    --->  Fetching docbook-xml-4.1.2
    --->  Attempting to fetch docbkx412.zip from http://www.oasis-open.org/docbook/xml/4.1.2/
    --->  Verifying checksum(s) for docbook-xml-4.1.2
    --->  Extracting docbook-xml-4.1.2
    --->  Configuring docbook-xml-4.1.2
    --->  Building docbook-xml-4.1.2
    --->  Staging docbook-xml-4.1.2 into destroot
    --->  Installing docbook-xml-4.1.2 @4.1.2_1
    --->  Activating docbook-xml-4.1.2 @4.1.2_1
    --->  Cleaning docbook-xml-4.1.2
    --->  Fetching docbook-xml-4.2
    --->  Attempting to fetch docbook-xml-4.2.zip from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/docbook-xml-4.2
    --->  Verifying checksum(s) for docbook-xml-4.2
    --->  Extracting docbook-xml-4.2
    --->  Configuring docbook-xml-4.2
    --->  Building docbook-xml-4.2
    --->  Staging docbook-xml-4.2 into destroot
    --->  Installing docbook-xml-4.2 @4.2_0
    --->  Activating docbook-xml-4.2 @4.2_0
    --->  Cleaning docbook-xml-4.2
    --->  Fetching docbook-xml-4.3
    --->  Attempting to fetch docbook-xml-4.3.zip from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/docbook-xml-4.3
    --->  Verifying checksum(s) for docbook-xml-4.3
    --->  Extracting docbook-xml-4.3
    --->  Configuring docbook-xml-4.3
    --->  Building docbook-xml-4.3
    --->  Staging docbook-xml-4.3 into destroot
    --->  Installing docbook-xml-4.3 @4.3_0
    --->  Activating docbook-xml-4.3 @4.3_0
    --->  Cleaning docbook-xml-4.3
    --->  Fetching docbook-xml-4.4
    --->  Attempting to fetch docbook-xml-4.4.zip from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/docbook-xml-4.4
    --->  Verifying checksum(s) for docbook-xml-4.4
    --->  Extracting docbook-xml-4.4
    --->  Configuring docbook-xml-4.4
    --->  Building docbook-xml-4.4
    --->  Staging docbook-xml-4.4 into destroot
    --->  Installing docbook-xml-4.4 @4.4_0
    --->  Activating docbook-xml-4.4 @4.4_0
    --->  Cleaning docbook-xml-4.4
    --->  Fetching docbook-xml-4.5
    --->  Attempting to fetch docbook-xml-4.5.zip from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/docbook-xml-4.5
    --->  Verifying checksum(s) for docbook-xml-4.5
    --->  Extracting docbook-xml-4.5
    --->  Configuring docbook-xml-4.5
    --->  Building docbook-xml-4.5
    --->  Staging docbook-xml-4.5 into destroot
    --->  Installing docbook-xml-4.5 @4.5_0
    --->  Activating docbook-xml-4.5 @4.5_0
    --->  Cleaning docbook-xml-4.5
    --->  Fetching docbook-xml-5.0
    --->  Attempting to fetch docbook-5.0.zip from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/docbook-xml-5.0
    --->  Verifying checksum(s) for docbook-xml-5.0
    --->  Extracting docbook-xml-5.0
    --->  Configuring docbook-xml-5.0
    --->  Building docbook-xml-5.0
    --->  Staging docbook-xml-5.0 into destroot
    --->  Installing docbook-xml-5.0 @5.0_0
    --->  Activating docbook-xml-5.0 @5.0_0
    --->  Cleaning docbook-xml-5.0
    --->  Fetching docbook-xml
    --->  Verifying checksum(s) for docbook-xml
    --->  Extracting docbook-xml
    --->  Configuring docbook-xml
    --->  Building docbook-xml
    --->  Staging docbook-xml into destroot
    --->  Installing docbook-xml @5.0_0
    --->  Activating docbook-xml @5.0_0
    --->  Cleaning docbook-xml
    --->  Fetching docbook-xsl
    --->  Attempting to fetch docbook-xsl-1.76.1.tar.bz2 from http://voxel.dl.sourceforge.net/docbook
    --->  Attempting to fetch docbook-xsl-doc-1.76.1.tar.bz2 from http://voxel.dl.sourceforge.net/docbook
    --->  Verifying checksum(s) for docbook-xsl
    --->  Extracting docbook-xsl
    --->  Configuring docbook-xsl
    --->  Building docbook-xsl
    --->  Staging docbook-xsl into destroot
    --->  Installing docbook-xsl @1.76.1_0
    --->  Activating docbook-xsl @1.76.1_0
    --->  Cleaning docbook-xsl
    --->  Fetching gnome-common
    --->  Attempting to fetch gnome-common-2.28.0.tar.bz2 from ftp://ftp.cse.buffalo.edu/pub/Gnome/sources/gnome-common/2.28/
    --->  Verifying checksum(s) for gnome-common
    --->  Extracting gnome-common
    --->  Applying patches to gnome-common
    --->  Configuring gnome-common
    --->  Building gnome-common
    --->  Staging gnome-common into destroot
    --->  Installing gnome-common @2.28.0_0
    --->  Activating gnome-common @2.28.0_0
    --->  Cleaning gnome-common
    --->  Fetching p5-getopt-long
    --->  Attempting to fetch Getopt-Long-2.38.tar.gz from ftp://mirror.hiwaay.net/CPAN/modules/by-module/Getopt
    --->  Verifying checksum(s) for p5-getopt-long
    --->  Extracting p5-getopt-long
    --->  Configuring p5-getopt-long
    --->  Building p5-getopt-long
    --->  Staging p5-getopt-long into destroot
    --->  Installing p5-getopt-long @2.38_0
    --->  Activating p5-getopt-long @2.38_0
    --->  Cleaning p5-getopt-long
    --->  Fetching p5-pathtools
    --->  Attempting to fetch PathTools-3.33.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/perl5
    --->  Verifying checksum(s) for p5-pathtools
    --->  Extracting p5-pathtools
    --->  Configuring p5-pathtools
    --->  Building p5-pathtools
    --->  Staging p5-pathtools into destroot
    --->  Installing p5-pathtools @3.33_0
    --->  Activating p5-pathtools @3.33_0
    --->  Cleaning p5-pathtools
    --->  Fetching p5-scalar-list-utils
    --->  Attempting to fetch Scalar-List-Utils-1.23.tar.gz from ftp://mirror.hiwaay.net/CPAN/modules/by-module/Scalar
    --->  Verifying checksum(s) for p5-scalar-list-utils
    --->  Extracting p5-scalar-list-utils
    --->  Configuring p5-scalar-list-utils
    --->  Building p5-scalar-list-utils
    --->  Staging p5-scalar-list-utils into destroot
    --->  Installing p5-scalar-list-utils @1.23_0
    --->  Activating p5-scalar-list-utils @1.23_0
    --->  Cleaning p5-scalar-list-utils
    --->  Fetching p5-xml-parser
    --->  Attempting to fetch XML-Parser-2.40.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/perl5
    --->  Verifying checksum(s) for p5-xml-parser
    --->  Extracting p5-xml-parser
    --->  Configuring p5-xml-parser
    --->  Building p5-xml-parser
    --->  Staging p5-xml-parser into destroot
    --->  Installing p5-xml-parser @2.40_0
    --->  Activating p5-xml-parser @2.40_0
    --->  Cleaning p5-xml-parser
    --->  Fetching intltool
    --->  Attempting to fetch intltool-0.40.6.tar.bz2 from ftp://ftp.cse.buffalo.edu/pub/Gnome/sources/intltool/0.40/
    --->  Verifying checksum(s) for intltool
    --->  Extracting intltool
    --->  Configuring intltool
    --->  Building intltool
    --->  Staging intltool into destroot
    --->  Installing intltool @0.40.6_0
    --->  Activating intltool @0.40.6_0
    --->  Cleaning intltool
    --->  Fetching iso-codes
    --->  Attempting to fetch iso-codes_3.23.orig.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/iso-codes
    --->  Verifying checksum(s) for iso-codes
    --->  Extracting iso-codes
    --->  Configuring iso-codes
    --->  Building iso-codes
    --->  Staging iso-codes into destroot
    --->  Installing iso-codes @3.23_0
    --->  Activating iso-codes @3.23_0
    --->  Cleaning iso-codes
    --->  Fetching libxml2
    --->  Attempting to fetch libxml2-2.7.8.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/libxml2
    --->  Verifying checksum(s) for libxml2
    --->  Extracting libxml2
    --->  Configuring libxml2
    --->  Building libxml2
    --->  Staging libxml2 into destroot
    --->  Installing libxml2 @2.7.8_0
    --->  Activating libxml2 @2.7.8_0
    --->  Cleaning libxml2
    --->  Fetching libxslt
    --->  Attempting to fetch libxslt-1.1.26.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/libxslt
    --->  Verifying checksum(s) for libxslt
    --->  Extracting libxslt
    --->  Configuring libxslt
    --->  Building libxslt
    --->  Staging libxslt into destroot
    --->  Installing libxslt @1.1.26_0
    --->  Activating libxslt @1.1.26_0
    --->  Cleaning libxslt
    --->  Fetching bzip2
    --->  Attempting to fetch bzip2-1.0.6.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/bzip2
    --->  Verifying checksum(s) for bzip2
    --->  Extracting bzip2
    --->  Applying patches to bzip2
    --->  Configuring bzip2
    --->  Building bzip2
    --->  Staging bzip2 into destroot
    --->  Installing bzip2 @1.0.6_0
    --->  Activating bzip2 @1.0.6_0
    --->  Cleaning bzip2
    --->  Fetching db46
    --->  Attempting to fetch patch.4.6.21.1 from http://download.oracle.com/berkeley-db/patches/db/4.6.21/
    --->  Attempting to fetch patch.4.6.21.2 from http://download.oracle.com/berkeley-db/patches/db/4.6.21/
    --->  Attempting to fetch patch.4.6.21.3 from http://download.oracle.com/berkeley-db/patches/db/4.6.21/
    --->  Attempting to fetch patch.4.6.21.4 from http://download.oracle.com/berkeley-db/patches/db/4.6.21/
    --->  Attempting to fetch db-4.6.21.tar.gz from http://download-east.oracle.com/berkeley-db/
    --->  Verifying checksum(s) for db46
    --->  Extracting db46
    --->  Applying patches to db46
    --->  Configuring db46
    --->  Building db46
    --->  Staging db46 into destroot
    --->  Installing db46 @4.6.21_6
    --->  Activating db46 @4.6.21_6
    --->  Cleaning db46
    --->  Fetching gdbm
    --->  Attempting to fetch gdbm-1.8.3.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/gdbm
    --->  Verifying checksum(s) for gdbm
    --->  Extracting gdbm
    --->  Configuring gdbm
    --->  Building gdbm
    --->  Staging gdbm into destroot
    --->  Installing gdbm @1.8.3_2
    --->  Activating gdbm @1.8.3_2
    --->  Cleaning gdbm
    --->  Fetching openssl
    --->  Attempting to fetch openssl-1.0.0c.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/openssl
    --->  Verifying checksum(s) for openssl
    --->  Extracting openssl
    --->  Applying patches to openssl
    --->  Configuring openssl
    --->  Building openssl
    --->  Staging openssl into destroot
    --->  Installing openssl @1.0.0c_0
    --->  Activating openssl @1.0.0c_0
    --->  Cleaning openssl
    --->  Fetching readline
    --->  Attempting to fetch readline61-001 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/readline
    --->  Attempting to fetch readline61-002 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/readline
    --->  Attempting to fetch readline-6.1.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/readline
    --->  Verifying checksum(s) for readline
    --->  Extracting readline
    --->  Applying patches to readline
    --->  Configuring readline
    --->  Building readline
    --->  Staging readline into destroot
    --->  Installing readline @6.1.002_0
    --->  Activating readline @6.1.002_0
    --->  Cleaning readline
    --->  Fetching sqlite3
    --->  Attempting to fetch sqlite-3.7.3.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/sqlite3
    --->  Verifying checksum(s) for sqlite3
    --->  Extracting sqlite3
    --->  Configuring sqlite3
    --->  Building sqlite3
    --->  Staging sqlite3 into destroot
    --->  Installing sqlite3 @3.7.3_0
    --->  Activating sqlite3 @3.7.3_0
    --->  Cleaning sqlite3
    --->  Fetching python26
    --->  Attempting to fetch Python-2.6.6.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/python26
    --->  Verifying checksum(s) for python26
    --->  Extracting python26
    --->  Applying patches to python26
    --->  Configuring python26
    --->  Building python26
    --->  Staging python26 into destroot
    --->  Installing python26 @2.6.6_1
    --->  Activating python26 @2.6.6_1
    
    To fully complete your installation and make python 2.6 the default,  please run:
     	sudo port install python_select
     	sudo python_select python26
    
    --->  Cleaning python26
    --->  Fetching py26-libxml2
    --->  Attempting to fetch libxml2-python-2.6.21.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/python
    --->  Verifying checksum(s) for py26-libxml2
    --->  Extracting py26-libxml2
    --->  Applying patches to py26-libxml2
    --->  Configuring py26-libxml2
    --->  Building py26-libxml2
    --->  Staging py26-libxml2 into destroot
    --->  Installing py26-libxml2 @2.6.21_0
    --->  Activating py26-libxml2 @2.6.21_0
    --->  Cleaning py26-libxml2
    --->  Fetching getopt
    --->  Attempting to fetch getopt-1.1.4.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/getopt
    --->  Verifying checksum(s) for getopt
    --->  Extracting getopt
    --->  Applying patches to getopt
    --->  Configuring getopt
    --->  Building getopt
    --->  Staging getopt into destroot
    --->  Installing getopt @1.1.4_1
    --->  Activating getopt @1.1.4_1
    --->  Cleaning getopt
    --->  Fetching rarian
    --->  Attempting to fetch rarian-0.8.1.tar.bz2 from ftp://ftp.cse.buffalo.edu/pub/Gnome/sources/rarian/0.8/
    --->  Verifying checksum(s) for rarian
    --->  Extracting rarian
    --->  Configuring rarian
    --->  Building rarian
    --->  Staging rarian into destroot
    --->  Installing rarian @0.8.1_0
    --->  Activating rarian @0.8.1_0
    --->  Cleaning rarian
    --->  Fetching gnome-doc-utils
    --->  Attempting to fetch gnome-doc-utils-0.20.2.tar.bz2 from ftp://ftp.cse.buffalo.edu/pub/Gnome/sources/gnome-doc-utils/0.20/
    --->  Verifying checksum(s) for gnome-doc-utils
    --->  Extracting gnome-doc-utils
    --->  Configuring gnome-doc-utils
    --->  Building gnome-doc-utils
    --->  Staging gnome-doc-utils into destroot
    --->  Installing gnome-doc-utils @0.20.2_0
    --->  Activating gnome-doc-utils @0.20.2_0
    --->  Cleaning gnome-doc-utils
    --->  Fetching gtk-doc
    --->  Attempting to fetch gtk-doc-1.15.tar.bz2 from ftp://ftp.cse.buffalo.edu/pub/Gnome/sources/gtk-doc/1.15/
    --->  Verifying checksum(s) for gtk-doc
    --->  Extracting gtk-doc
    --->  Configuring gtk-doc
    --->  Building gtk-doc
    --->  Staging gtk-doc into destroot
    --->  Installing gtk-doc @1.15_1
    --->  Activating gtk-doc @1.15_1
    --->  Cleaning gtk-doc
    --->  Fetching atk
    --->  Attempting to fetch atk-1.30.0.tar.bz2 from ftp://ftp.cse.buffalo.edu/pub/Gnome/sources/atk/1.30/
    --->  Verifying checksum(s) for atk
    --->  Extracting atk
    --->  Configuring atk
    --->  Building atk
    --->  Staging atk into destroot
    --->  Installing atk @1.30.0_0
    --->  Activating atk @1.30.0_0
    --->  Cleaning atk
    --->  Fetching jpeg
    --->  Attempting to fetch jpegsrc.v8b.tar.gz from ftp://ftp.uu.net/graphics/jpeg/
    --->  Attempting to fetch jpegsrc.v8b.tar.gz from http://www.ijg.org/files/
    --->  Verifying checksum(s) for jpeg
    --->  Extracting jpeg
    --->  Configuring jpeg
    --->  Building jpeg
    --->  Staging jpeg into destroot
    --->  Installing jpeg @8b_0
    --->  Activating jpeg @8b_0
    --->  Cleaning jpeg
    --->  Fetching jasper
    --->  Attempting to fetch jasper-1.900.1.zip from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/jasper
    --->  Verifying checksum(s) for jasper
    --->  Extracting jasper
    --->  Applying patches to jasper
    --->  Configuring jasper
    --->  Building jasper
    --->  Staging jasper into destroot
    --->  Installing jasper @1.900.1_7
    --->  Activating jasper @1.900.1_7
    --->  Cleaning jasper
    --->  Fetching libpng
    --->  Attempting to fetch libpng-1.2.44.tar.bz2 from http://voxel.dl.sourceforge.net/libpng
    --->  Verifying checksum(s) for libpng
    --->  Extracting libpng
    --->  Configuring libpng
    --->  Building libpng
    --->  Staging libpng into destroot
    --->  Installing libpng @1.2.44_0
    --->  Activating libpng @1.2.44_0
    --->  Cleaning libpng
    --->  Fetching tiff
    --->  Attempting to fetch tiff-3.9.4.tar.gz from http://dl.maptools.org/dl/libtiff/
    --->  Attempting to fetch tiff-3.9.4.tar.gz from ftp://ftp5.freebsd.org/pub/FreeBSD/ports/distfiles/
    --->  Verifying checksum(s) for tiff
    --->  Extracting tiff
    --->  Configuring tiff
    --->  Building tiff
    --->  Staging tiff into destroot
    --->  Installing tiff @3.9.4_0
    --->  Activating tiff @3.9.4_0
    --->  Cleaning tiff
    --->  Fetching gdk-pixbuf2
    --->  Attempting to fetch gdk-pixbuf-2.22.1.tar.bz2 from ftp://ftp.cse.buffalo.edu/pub/Gnome/sources/gdk-pixbuf/2.22/
    --->  Verifying checksum(s) for gdk-pixbuf2
    --->  Extracting gdk-pixbuf2
    --->  Configuring gdk-pixbuf2
    --->  Building gdk-pixbuf2
    --->  Staging gdk-pixbuf2 into destroot
    --->  Installing gdk-pixbuf2 @2.22.1_0
    --->  Activating gdk-pixbuf2 @2.22.1_0
    --->  Cleaning gdk-pixbuf2
    --->  Fetching freetype
    --->  Attempting to fetch freetype-2.4.4.tar.bz2 from http://voxel.dl.sourceforge.net/freetype
    --->  Attempting to fetch freetype-doc-2.4.4.tar.bz2 from http://voxel.dl.sourceforge.net/freetype
    --->  Verifying checksum(s) for freetype
    --->  Extracting freetype
    --->  Applying patches to freetype
    --->  Configuring freetype
    --->  Building freetype
    --->  Staging freetype into destroot
    --->  Installing freetype @2.4.4_0
    --->  Activating freetype @2.4.4_0
    --->  Cleaning freetype
    --->  Fetching fontconfig
    --->  Attempting to fetch fontconfig-2.8.0.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/fontconfig
    --->  Verifying checksum(s) for fontconfig
    --->  Extracting fontconfig
    --->  Applying patches to fontconfig
    --->  Configuring fontconfig
    --->  Building fontconfig
    --->  Staging fontconfig into destroot
    --->  Installing fontconfig @2.8.0_0
    --->  Activating fontconfig @2.8.0_0
    --->  Cleaning fontconfig
    --->  Fetching xorg-bigreqsproto
    --->  Attempting to fetch bigreqsproto-1.1.1.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-bigreqsproto
    --->  Verifying checksum(s) for xorg-bigreqsproto
    --->  Extracting xorg-bigreqsproto
    --->  Configuring xorg-bigreqsproto
    --->  Building xorg-bigreqsproto
    --->  Staging xorg-bigreqsproto into destroot
    --->  Installing xorg-bigreqsproto @1.1.1_0
    --->  Activating xorg-bigreqsproto @1.1.1_0
    --->  Cleaning xorg-bigreqsproto
    --->  Fetching xorg-inputproto
    --->  Attempting to fetch inputproto-2.0.1.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-inputproto
    --->  Verifying checksum(s) for xorg-inputproto
    --->  Extracting xorg-inputproto
    --->  Configuring xorg-inputproto
    --->  Building xorg-inputproto
    --->  Staging xorg-inputproto into destroot
    --->  Installing xorg-inputproto @2.0.1_0
    --->  Activating xorg-inputproto @2.0.1_0
    --->  Cleaning xorg-inputproto
    --->  Fetching xorg-kbproto
    --->  Attempting to fetch kbproto-1.0.5.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-kbproto
    --->  Verifying checksum(s) for xorg-kbproto
    --->  Extracting xorg-kbproto
    --->  Configuring xorg-kbproto
    --->  Building xorg-kbproto
    --->  Staging xorg-kbproto into destroot
    --->  Installing xorg-kbproto @1.0.5_0
    --->  Activating xorg-kbproto @1.0.5_0
    --->  Cleaning xorg-kbproto
    --->  Fetching xorg-xproto
    --->  Attempting to fetch xproto-7.0.20.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-xproto
    --->  Verifying checksum(s) for xorg-xproto
    --->  Extracting xorg-xproto
    --->  Configuring xorg-xproto
    --->  Building xorg-xproto
    --->  Staging xorg-xproto into destroot
    --->  Installing xorg-xproto @7.0.20_0
    --->  Activating xorg-xproto @7.0.20_0
    --->  Cleaning xorg-xproto
    --->  Fetching xorg-libXau
    --->  Attempting to fetch libXau-1.0.6.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXau
    --->  Verifying checksum(s) for xorg-libXau
    --->  Extracting xorg-libXau
    --->  Configuring xorg-libXau
    --->  Building xorg-libXau
    --->  Staging xorg-libXau into destroot
    --->  Installing xorg-libXau @1.0.6_0
    --->  Activating xorg-libXau @1.0.6_0
    --->  Cleaning xorg-libXau
    --->  Fetching xorg-libXdmcp
    --->  Attempting to fetch libXdmcp-1.1.0.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXdmcp
    --->  Verifying checksum(s) for xorg-libXdmcp
    --->  Extracting xorg-libXdmcp
    --->  Configuring xorg-libXdmcp
    --->  Building xorg-libXdmcp
    --->  Staging xorg-libXdmcp into destroot
    --->  Installing xorg-libXdmcp @1.1.0_0
    --->  Activating xorg-libXdmcp @1.1.0_0
    --->  Cleaning xorg-libXdmcp
    --->  Fetching xorg-libpthread-stubs
    --->  Attempting to fetch libpthread-stubs-0.3.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libpthread-stubs
    --->  Verifying checksum(s) for xorg-libpthread-stubs
    --->  Extracting xorg-libpthread-stubs
    --->  Configuring xorg-libpthread-stubs
    --->  Building xorg-libpthread-stubs
    --->  Staging xorg-libpthread-stubs into destroot
    --->  Installing xorg-libpthread-stubs @0.3_0
    --->  Activating xorg-libpthread-stubs @0.3_0
    --->  Cleaning xorg-libpthread-stubs
    --->  Fetching xorg-xcb-proto
    --->  Attempting to fetch xcb-proto-1.6.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-xcb-proto
    --->  Verifying checksum(s) for xorg-xcb-proto
    --->  Extracting xorg-xcb-proto
    --->  Configuring xorg-xcb-proto
    --->  Building xorg-xcb-proto
    --->  Staging xorg-xcb-proto into destroot
    --->  Installing xorg-xcb-proto @1.6_0+python26
    --->  Activating xorg-xcb-proto @1.6_0+python26
    --->  Cleaning xorg-xcb-proto
    --->  Fetching xorg-libxcb
    --->  Attempting to fetch libxcb-1.7.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libxcb
    --->  Verifying checksum(s) for xorg-libxcb
    --->  Extracting xorg-libxcb
    --->  Configuring xorg-libxcb
    --->  Building xorg-libxcb
    --->  Staging xorg-libxcb into destroot
    --->  Installing xorg-libxcb @1.7_0+python26
    --->  Activating xorg-libxcb @1.7_0+python26
    --->  Cleaning xorg-libxcb
    --->  Fetching xorg-util-macros
    --->  Attempting to fetch util-macros-1.11.0.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-util-macros
    --->  Verifying checksum(s) for xorg-util-macros
    --->  Extracting xorg-util-macros
    --->  Configuring xorg-util-macros
    --->  Building xorg-util-macros
    --->  Staging xorg-util-macros into destroot
    --->  Installing xorg-util-macros @1.11.0_0
    --->  Activating xorg-util-macros @1.11.0_0
    --->  Cleaning xorg-util-macros
    --->  Fetching xorg-xcmiscproto
    --->  Attempting to fetch xcmiscproto-1.2.1.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-xcmiscproto
    --->  Verifying checksum(s) for xorg-xcmiscproto
    --->  Extracting xorg-xcmiscproto
    --->  Configuring xorg-xcmiscproto
    --->  Building xorg-xcmiscproto
    --->  Staging xorg-xcmiscproto into destroot
    --->  Installing xorg-xcmiscproto @1.2.1_0
    --->  Activating xorg-xcmiscproto @1.2.1_0
    --->  Cleaning xorg-xcmiscproto
    --->  Fetching xorg-xextproto
    --->  Attempting to fetch xextproto-7.1.2.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-xextproto
    --->  Verifying checksum(s) for xorg-xextproto
    --->  Extracting xorg-xextproto
    --->  Configuring xorg-xextproto
    --->  Building xorg-xextproto
    --->  Staging xorg-xextproto into destroot
    --->  Installing xorg-xextproto @7.1.2_0
    --->  Activating xorg-xextproto @7.1.2_0
    --->  Cleaning xorg-xextproto
    --->  Fetching xorg-xf86bigfontproto
    --->  Attempting to fetch xf86bigfontproto-1.2.0.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-xf86bigfontproto
    --->  Verifying checksum(s) for xorg-xf86bigfontproto
    --->  Extracting xorg-xf86bigfontproto
    --->  Configuring xorg-xf86bigfontproto
    --->  Building xorg-xf86bigfontproto
    --->  Staging xorg-xf86bigfontproto into destroot
    --->  Installing xorg-xf86bigfontproto @1.2.0_0
    --->  Activating xorg-xf86bigfontproto @1.2.0_0
    --->  Cleaning xorg-xf86bigfontproto
    --->  Fetching xorg-xtrans
    --->  Attempting to fetch xtrans-1.2.6.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-xtrans
    --->  Verifying checksum(s) for xorg-xtrans
    --->  Extracting xorg-xtrans
    --->  Configuring xorg-xtrans
    --->  Building xorg-xtrans
    --->  Staging xorg-xtrans into destroot
    --->  Installing xorg-xtrans @1.2.6_0
    --->  Activating xorg-xtrans @1.2.6_0
    --->  Cleaning xorg-xtrans
    --->  Fetching xorg-libX11
    --->  Attempting to fetch libX11-1.4.0.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libX11
    --->  Verifying checksum(s) for xorg-libX11
    --->  Extracting xorg-libX11
    --->  Configuring xorg-libX11
    --->  Building xorg-libX11
    --->  Staging xorg-libX11 into destroot
    --->  Installing xorg-libX11 @1.4.0_1
    --->  Activating xorg-libX11 @1.4.0_1
    --->  Cleaning xorg-libX11
    --->  Fetching xorg-renderproto
    --->  Attempting to fetch renderproto-0.11.1.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-renderproto
    --->  Verifying checksum(s) for xorg-renderproto
    --->  Extracting xorg-renderproto
    --->  Configuring xorg-renderproto
    --->  Building xorg-renderproto
    --->  Staging xorg-renderproto into destroot
    --->  Installing xorg-renderproto @0.11.1_0
    --->  Activating xorg-renderproto @0.11.1_0
    --->  Cleaning xorg-renderproto
    --->  Fetching xrender
    --->  Attempting to fetch libXrender-0.9.6.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xrender
    --->  Verifying checksum(s) for xrender
    --->  Extracting xrender
    --->  Configuring xrender
    --->  Building xrender
    --->  Staging xrender into destroot
    --->  Installing xrender @0.9.6_0
    --->  Activating xrender @0.9.6_0
    --->  Cleaning xrender
    --->  Fetching Xft2
    --->  Attempting to fetch libXft-2.2.0.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/Xft2
    --->  Verifying checksum(s) for Xft2
    --->  Extracting Xft2
    --->  Configuring Xft2
    --->  Building Xft2
    --->  Staging Xft2 into destroot
    --->  Installing Xft2 @2.2.0_0
    --->  Activating Xft2 @2.2.0_0
    --->  Cleaning Xft2
    --->  Fetching libpixman
    --->  Attempting to fetch pixman-0.20.0.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/libpixman
    --->  Verifying checksum(s) for libpixman
    --->  Extracting libpixman
    --->  Configuring libpixman
    --->  Building libpixman
    --->  Staging libpixman into destroot
    --->  Installing libpixman @0.20.0_0
    --->  Activating libpixman @0.20.0_0
    --->  Cleaning libpixman
    --->  Fetching cairo
    --->  Attempting to fetch cairo-1.10.0.tar.gz from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/cairo
    --->  Verifying checksum(s) for cairo
    --->  Extracting cairo
    --->  Applying patches to cairo
    --->  Configuring cairo
    --->  Building cairo
    --->  Staging cairo into destroot
    --->  Installing cairo @1.10.0_1
    --->  Activating cairo @1.10.0_1
    --->  Cleaning cairo
    --->  Fetching pango
    --->  Attempting to fetch pango-1.28.3.tar.bz2 from ftp://ftp.cse.buffalo.edu/pub/Gnome/sources/pango/1.28
    --->  Verifying checksum(s) for pango
    --->  Extracting pango
    --->  Applying patches to pango
    --->  Configuring pango
    --->  Building pango
    --->  Staging pango into destroot
    --->  Installing pango @1.28.3_0
    --->  Activating pango @1.28.3_0
    --->  Cleaning pango
    --->  Fetching shared-mime-info
    --->  Attempting to fetch shared-mime-info-0.90.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/shared-mime-info
    --->  Verifying checksum(s) for shared-mime-info
    --->  Extracting shared-mime-info
    --->  Configuring shared-mime-info
    --->  Building shared-mime-info
    --->  Staging shared-mime-info into destroot
    --->  Installing shared-mime-info @0.90_0
    --->  Activating shared-mime-info @0.90_0
    --->  Cleaning shared-mime-info
    --->  Fetching xorg-compositeproto
    --->  Attempting to fetch compositeproto-0.4.2.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-compositeproto
    --->  Verifying checksum(s) for xorg-compositeproto
    --->  Extracting xorg-compositeproto
    --->  Configuring xorg-compositeproto
    --->  Building xorg-compositeproto
    --->  Staging xorg-compositeproto into destroot
    --->  Installing xorg-compositeproto @0.4.2_0
    --->  Activating xorg-compositeproto @0.4.2_0
    --->  Cleaning xorg-compositeproto
    --->  Fetching xorg-libXext
    --->  Attempting to fetch libXext-1.2.0.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXext
    --->  Verifying checksum(s) for xorg-libXext
    --->  Extracting xorg-libXext
    --->  Configuring xorg-libXext
    --->  Building xorg-libXext
    --->  Staging xorg-libXext into destroot
    --->  Installing xorg-libXext @1.2.0_0
    --->  Activating xorg-libXext @1.2.0_0
    --->  Cleaning xorg-libXext
    --->  Fetching xorg-fixesproto
    --->  Attempting to fetch fixesproto-4.1.2.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-fixesproto
    --->  Verifying checksum(s) for xorg-fixesproto
    --->  Extracting xorg-fixesproto
    --->  Configuring xorg-fixesproto
    --->  Building xorg-fixesproto
    --->  Staging xorg-fixesproto into destroot
    --->  Installing xorg-fixesproto @4.1.2_0
    --->  Activating xorg-fixesproto @4.1.2_0
    --->  Cleaning xorg-fixesproto
    --->  Fetching xorg-libXfixes
    --->  Attempting to fetch libXfixes-4.0.5.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXfixes
    --->  Verifying checksum(s) for xorg-libXfixes
    --->  Extracting xorg-libXfixes
    --->  Configuring xorg-libXfixes
    --->  Building xorg-libXfixes
    --->  Staging xorg-libXfixes into destroot
    --->  Installing xorg-libXfixes @4.0.5_0
    --->  Activating xorg-libXfixes @4.0.5_0
    --->  Cleaning xorg-libXfixes
    --->  Fetching xorg-libXcomposite
    --->  Attempting to fetch libXcomposite-0.4.3.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXcomposite
    --->  Verifying checksum(s) for xorg-libXcomposite
    --->  Extracting xorg-libXcomposite
    --->  Configuring xorg-libXcomposite
    --->  Building xorg-libXcomposite
    --->  Staging xorg-libXcomposite into destroot
    --->  Installing xorg-libXcomposite @0.4.3_0
    --->  Activating xorg-libXcomposite @0.4.3_0
    --->  Cleaning xorg-libXcomposite
    --->  Fetching xorg-libXcursor
    --->  Attempting to fetch libXcursor-1.1.11.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXcursor
    --->  Verifying checksum(s) for xorg-libXcursor
    --->  Extracting xorg-libXcursor
    --->  Configuring xorg-libXcursor
    --->  Building xorg-libXcursor
    --->  Staging xorg-libXcursor into destroot
    --->  Installing xorg-libXcursor @1.1.11_0
    --->  Activating xorg-libXcursor @1.1.11_0
    --->  Cleaning xorg-libXcursor
    --->  Fetching xorg-damageproto
    --->  Attempting to fetch damageproto-1.2.1.tar.bz2 from http://distfiles.macports.org/xorg-damageproto
    --->  Verifying checksum(s) for xorg-damageproto
    --->  Extracting xorg-damageproto
    --->  Configuring xorg-damageproto
    --->  Building xorg-damageproto
    --->  Staging xorg-damageproto into destroot
    --->  Installing xorg-damageproto @1.2.1_0
    --->  Activating xorg-damageproto @1.2.1_0
    --->  Cleaning xorg-damageproto
    --->  Fetching xorg-libXdamage
    --->  Attempting to fetch libXdamage-1.1.3.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXdamage
    --->  Verifying checksum(s) for xorg-libXdamage
    --->  Extracting xorg-libXdamage
    --->  Configuring xorg-libXdamage
    --->  Building xorg-libXdamage
    --->  Staging xorg-libXdamage into destroot
    --->  Installing xorg-libXdamage @1.1.3_0
    --->  Activating xorg-libXdamage @1.1.3_0
    --->  Cleaning xorg-libXdamage
    --->  Fetching xorg-libXi
    --->  Attempting to fetch libXi-1.4.0.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXi
    --->  Verifying checksum(s) for xorg-libXi
    --->  Extracting xorg-libXi
    --->  Configuring xorg-libXi
    --->  Building xorg-libXi
    --->  Staging xorg-libXi into destroot
    --->  Installing xorg-libXi @1.4.0_0
    --->  Activating xorg-libXi @1.4.0_0
    --->  Cleaning xorg-libXi
    --->  Fetching xorg-xineramaproto
    --->  Attempting to fetch xineramaproto-1.2.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-xineramaproto
    --->  Verifying checksum(s) for xorg-xineramaproto
    --->  Extracting xorg-xineramaproto
    --->  Configuring xorg-xineramaproto
    --->  Building xorg-xineramaproto
    --->  Staging xorg-xineramaproto into destroot
    --->  Installing xorg-xineramaproto @1.2_0
    --->  Activating xorg-xineramaproto @1.2_0
    --->  Cleaning xorg-xineramaproto
    --->  Fetching xorg-libXinerama
    --->  Attempting to fetch libXinerama-1.1.1.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXinerama
    --->  Verifying checksum(s) for xorg-libXinerama
    --->  Extracting xorg-libXinerama
    --->  Configuring xorg-libXinerama
    --->  Building xorg-libXinerama
    --->  Staging xorg-libXinerama into destroot
    --->  Installing xorg-libXinerama @1.1.1_0
    --->  Activating xorg-libXinerama @1.1.1_0
    --->  Cleaning xorg-libXinerama
    --->  Fetching xorg-randrproto
    --->  Attempting to fetch randrproto-1.3.2.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-randrproto
    --->  Verifying checksum(s) for xorg-randrproto
    --->  Extracting xorg-randrproto
    --->  Configuring xorg-randrproto
    --->  Building xorg-randrproto
    --->  Staging xorg-randrproto into destroot
    --->  Installing xorg-randrproto @1.3.2_0
    --->  Activating xorg-randrproto @1.3.2_0
    --->  Cleaning xorg-randrproto
    --->  Fetching xorg-libXrandr
    --->  Attempting to fetch libXrandr-1.3.1.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXrandr
    --->  Verifying checksum(s) for xorg-libXrandr
    --->  Extracting xorg-libXrandr
    --->  Configuring xorg-libXrandr
    --->  Building xorg-libXrandr
    --->  Staging xorg-libXrandr into destroot
    --->  Installing xorg-libXrandr @1.3.1_0
    --->  Activating xorg-libXrandr @1.3.1_0
    --->  Cleaning xorg-libXrandr
    --->  Fetching gtk2
    --->  Attempting to fetch gtk+-2.22.1.tar.bz2 from ftp://ftp.cse.buffalo.edu/pub/Gnome/sources/gtk+/2.22/
    --->  Verifying checksum(s) for gtk2
    --->  Extracting gtk2
    --->  Applying patches to gtk2
    --->  Configuring gtk2
    --->  Building gtk2
    --->  Staging gtk2 into destroot
    --->  Installing gtk2 @2.22.1_0+x11
    --->  Activating gtk2 @2.22.1_0+x11
    --->  Cleaning gtk2
    --->  Fetching xorg-recordproto
    --->  Attempting to fetch recordproto-1.14.1.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-recordproto
    --->  Verifying checksum(s) for xorg-recordproto
    --->  Extracting xorg-recordproto
    --->  Configuring xorg-recordproto
    --->  Building xorg-recordproto
    --->  Staging xorg-recordproto into destroot
    --->  Installing xorg-recordproto @1.14.1_0
    --->  Activating xorg-recordproto @1.14.1_0
    --->  Cleaning xorg-recordproto
    --->  Fetching xorg-libXtst
    --->  Attempting to fetch libXtst-1.2.0.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/xorg-libXtst
    --->  Verifying checksum(s) for xorg-libXtst
    --->  Extracting xorg-libXtst
    --->  Configuring xorg-libXtst
    --->  Building xorg-libXtst
    --->  Staging xorg-libXtst into destroot
    --->  Installing xorg-libXtst @1.2.0_0
    --->  Activating xorg-libXtst @1.2.0_0
    --->  Cleaning xorg-libXtst
    --->  Fetching eiffelstudio67
    --->  Attempting to fetch PorterPackage_67_85123.tar from http://iweb.dl.sourceforge.net/eiffelstudio
    --->  Attempting to fetch eiffel_launcher_20091003.tar.bz2 from http://ykf.ca.distfiles.macports.org/MacPorts/mpdistfiles/eiffelstudio67
    --->  Verifying checksum(s) for eiffelstudio67
    --->  Extracting eiffelstudio67
    --->  Configuring eiffelstudio67
    --->  Building eiffelstudio67
    --->  Staging eiffelstudio67 into destroot
    --->  Installing eiffelstudio67 @6.7.85123_0
    --->  Activating eiffelstudio67 @6.7.85123_0
     ################################################################################## 
     To complete the installation you have to add the following to your .bashrc or .profile file : 
     export ISE_PLATFORM=macosx-x86-64 
     export ISE_EIFFEL=/Applications/MacPorts/Eiffel67 
     export GOBO=$ISE_EIFFEL/library/gobo/svn 
     export PATH=$PATH:$ISE_EIFFEL/studio/spec/$ISE_PLATFORM/bin:$GOBO/../spec/$ISE_PLATFORM/bin 
     ################################################################################## 
    
    --->  Cleaning eiffelstudio67
    ```

3. Modify `~/.bashrc`

    ```
    export ISE_PLATFORM=macosx-x86-64
    export ISE_EIFFEL=/Applications/MacPorts/Eiffel67
    export GOBO=$ISE_EIFFEL/library/gobo/svn
    export PATH=$PATH:$ISE_EIFFEL/studio/spec/$ISE_PLATFORM/bin:$GOBO/../spec/$ISE_PLATFORM/bin
    ```

4. Source `~/.bashrc`

5. Build `wd` from the command-line using the provided `Makefile`

    a. `make clean`

    b. `make melt`

    c. `make freeze`

    d. `make finalize`

6. Alternatively, run `estudio` and open the `wd` project

    a. The project configuration is in the `src` directory

    b. Finalize the project to build an optimized binary

7. Win!
