
  . /etc/profile.d/qt4.rc &&

  default_cmake_build &&

  if in_depends $MODULE qt5 ; then
    . /etc/profile.d/qt5.rc &&
    OPTS+=" -DBUILD_WITH_QT4=OFF" &&
    default_cmake_build
  fi
