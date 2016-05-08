
  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 \
          -DBUILD_MARBLE_EXAMPLES=0        \
          -DBUILD_MARBLE_TESTS=0           \   
          -DMOBILE=0                       \
          -DBUILD_MARBLE_APPS=1" &&

  default_cmake_build &&

  ln -sf /usr/share/marble/cmake/FindMarble.cmake /usr/share/cmake-`lvu version cmake | cut -c 1-3`/Modules
