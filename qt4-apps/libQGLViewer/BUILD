cd QGLViewer &&

qmake $OPTS  &&

sedit "s@-lGL@-lGLU \0@" Makefile &&

default_make &&
  
cd $SOURCE_DIRECTORY/designerPlugin &&
qmake &&
default_make
