
  patch_it $SOURCE2 1 &&
  sedit "s:add_definitions(-D_BSD_SOURCE):add_definitions(-D_BSD_SOURCE -D_DEFAULT_SOURCE):" cmake/modules/TelepathyDefaults.cmake &&

  . /etc/profile.d/qt4.rc &&
  OPTS+=" -DDESIRED_QT_VERSION=4 -DENABLE_EXAMPLES=0 -DENABLE_TESTS=0" &&
  default_cmake_build &&

  . /etc/profile.d/qt5.rc &&
  OPTS+=" -DDESIRED_QT_VERSION=5 -DENABLE_EXAMPLES=0 -DENABLE_TESTS=0" &&
  default_cmake_build
