
  . /etc/profile.d/qt4.rc  &&

  OPTS+=" -DBUILD_WITH_QT4=1" &&

  default_cmake_build &&

  if module_installed qt5 ; then
    . /etc/profile.d/qt5.rc &&
    OPTS+=" -DBUILD_WITH_QT4=0" &&
    default_cmake_build
  fi
