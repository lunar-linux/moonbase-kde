
  patch_it $SOURCE2 1 &&
  patch_it $SOURCE3 1 &&

  if in_depends $MODULE qt4 ;  then
    . /etc/profile.d/qt4.rc &&
    OPTS+=" -DQTGSTREAMER_EXAMPLES=0" &&
    default_cmake_build
  fi &&

  . /etc/profile.d/qt5.rc &&
  OPTS+=" -DQT_VERSION=5 -DQT_QMAKE_EXECUTABLE=/usr/lib/qt5/bin/qmake -DQTGSTREAMER_EXAMPLES=0" &&
  default_cmake_build
