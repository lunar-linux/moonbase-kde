
 . /etc/profile.d/qt4.rc &&
 . /etc/profile.d/qt5.rc &&

  qmake PREFIX=/usr $OPTS &&
  default_make &&

  make clean &&

  /usr/lib/qt5/bin/qmake $OPTS &&
  default_make
