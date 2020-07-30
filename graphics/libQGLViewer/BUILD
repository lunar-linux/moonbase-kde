. /etc/profile.d/qt5.rc &&

CFLAGS="-pipe ${CFLAGS} -D_REENTRANT -Wall -W -fPIC \$(DEFINES)" &&
CXXLIBS=" ${CXXLIBS} " &&
CXXFLAGS="-pipe ${CXXFLAGS} -I/usr/include/GL -D_REENTRANT -Wall -W -fPIC \$(DEFINES)" &&

sed -e 's#designerPlugin##' -i $MODULE-$VERSION.pro &&

/usr/lib/qt5/bin/qmake PREFIX=/usr DOC_DIR=/usr/share/doc $OPTS  &&

sedit "s@-lGL@-lGLU \0@" Makefile &&

default_make &&
devoke_installwatch &&
  
cd $SOURCE_DIRECTORY/designerPlugin &&
/usr/lib/qt5/bin/qmake PREFIX=/usr/lib/qt5/plugins &&
default_make
