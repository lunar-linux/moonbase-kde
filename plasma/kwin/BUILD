
  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

#  sedit "20i #include <stdlib.h>" plugins/qpa/main.cpp main_wayland.cpp &&
  sedit "s:add_subdirectory(qpa)::" plugins/CMakeLists.txt &&
  default_cmake_build
