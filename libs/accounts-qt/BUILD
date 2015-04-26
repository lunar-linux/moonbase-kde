
  . /etc/profile.d/qt4.rc &&
  . /etc/profile.d/kde4.rc &&

  qmake prefix=/usr $OPTS &&
  default_build

  if in_depends $MODULE qt5 ; then
    . /etc/profile.d/qt5.rc &&
    . /etc/profile.d/kde4.rc &&
    /usr/lib/qt5/bin/qmake prefix=/usr $OPTS &&
    default_make
  fi
