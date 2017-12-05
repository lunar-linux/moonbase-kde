
  patch_it $SOURCE2 1 &&
  patch_it $SOURCE3 1 &&

  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DQT_VERSION=5 -DQT_QMAKE_EXECUTABLE=/usr/lib/qt5/bin/qmake -DQTGSTREAMER_EXAMPLES=0" &&

  default_cmake_build
