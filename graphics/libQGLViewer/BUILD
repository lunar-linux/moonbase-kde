. /etc/profile.d/qt5.rc &&

/usr/lib/qt5/bin/qmake PREFIX=/usr $OPTS  &&

sedit "s@-lGL@-lGLU \0@" Makefile &&

default_make &&
devoke_installwatch &&
  
cd $SOURCE_DIRECTORY/designerPlugin &&
/usr/lib/qt5/bin/qmake PREFIX=/usr/lib/qt5/plugins &&
default_make &&
rm -rf /usr/designer &&

if in_depends $MODULE qt4 ; then
devoke_installwatch &&
/usr/bin/qmake PREFIX=/usr $OPTS  &&

sedit "s@-lGL@-lGLU \0@" Makefile &&

default_make &&
devoke_installwatch &&

cd $SOURCE_DIRECTORY/designerPlugin &&
/usr/bin/qmake &&
default_make
fi
