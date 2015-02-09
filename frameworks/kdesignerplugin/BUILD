
  source /etc/profile.d/qt5.rc &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

  sedit "88,92d" CMakeLists.txt &&

  default_cmake_build
