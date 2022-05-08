. /etc/profile.d/qt5.rc &&

CFLAGS="-pipe ${CFLAGS} -D_REENTRANT -Wall -W -fPIC \$(DEFINES)" &&
CXXLIBS=" ${CXXLIBS} " &&
CXXFLAGS="-pipe ${CXXFLAGS} -I/usr/include/GL -D_REENTRANT -Wall -W -fPIC \$(DEFINES)" &&
DOC_DIR="/usr/share/doc/$MODULE" &&

sed -e 's#designerPlugin##' -i $MODULE-$VERSION.pro &&

/usr/lib/qt5/bin/qmake PREFIX=/usr DOC_DIR=$DOC_DIR $OPTS  &&

sedit "s@-lGL@-lGLU \0@" Makefile &&

default_make &&
devoke_installwatch &&
  
cd $SOURCE_DIRECTORY/designerPlugin &&
DOC_DIR="/usr/share/doc/$MODULE" &&
/usr/lib/qt5/bin/qmake PREFIX=/usr/lib/qt5/plugins DOC_DIR=$DOC_DIR &&
default_make
