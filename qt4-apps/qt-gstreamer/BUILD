
  . /etc/profile.d/qt4.rc &&

  patch_it $SOURCE2 1 &&

  OPTS+=" -DQTGSTREAMER_EXAMPLES=0" &&

  default_cmake_build &&

  if in_depends $MODULE qt5 ; then
    . /etc/profile.d/qt5.rc &&
    OPTS+=" -DQT_VERSION=5 -DQT_QMAKE_EXECUTABLE=/usr/lib/qt5/bin/qmake -DQTGSTREAMER_EXAMPLES=0" &&
    default_cmake_build
  fi
