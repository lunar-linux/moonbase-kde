
  . /etc/profile.d/qt5.rc &&

  patch_it $SOURCE2 1 &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 -DENABLE_OPENCV3=1" &&

  default_cmake_build
