  source /etc/profile.d/qt5.rc   &&

  export CFLAGS+=" -Wno-error $CFLAGS" &&
  export CXXFLAGS+=" -Wno-error $CXXFLAGS" &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

  default_cmake_build
