cd QGLViewer &&

qmake PREFIX=/usr $OPTS  &&

sedit "s@-lGL@-lGLU \0@" Makefile &&

default_make &&
devoke_installwatch &&
  
cd $SOURCE_DIRECTORY/designerPlugin &&
qmake &&
default_make
