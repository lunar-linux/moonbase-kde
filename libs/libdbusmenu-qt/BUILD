
  . /etc/profile.d/qt4.rc &&

  export LDFLAGS="-L/usr/lib/qt4" &&
  OPTS+=" -DUSE_QT5=0" &&
  default_cmake_build &&

  if in_depends $MODULE qt5 ; then
    . /etc/profile.d/qt5.rc &&
    export LDFLAGS="-L/usr/lib/qt5" &&
    OPTS+=" -DUSE_QT5=1" &&
    default_cmake_build
  fi
