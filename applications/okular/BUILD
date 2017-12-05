
  . /etc/profile.d/qt5.rc   &&

  sedit "s:ghostview MODULE:ghostview:" generators/spectre/CMakeLists.txt &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 -DBUILD_TESTING=OFF" &&

  default_cmake_build
