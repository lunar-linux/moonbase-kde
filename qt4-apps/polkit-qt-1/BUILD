

  source /etc/profile.d/qt4.rc   &&
  source /etc/profile.d/kde4.rc  &&

  OPTS+=" -DUSE_QT4=1 -DUSE_QT5=0" &&

  default_cmake_build

# Do the qt5 part
  if in_depends $MODULE qt5 ; then
    . /etc/profile.d/qt5.rc &&
    . /etc/profile.d/kde4.rc &&
    OPTS+=" -DUSE_QT4=0 -DUSE_QT5=1" &&
    default_cmake_build
  fi
