
  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1   \
          -DBUILD_MARBLE_TOOLS=1             \
          -DBUILD_MARBLE_TESTS=1             \
          -DWITH_QextSerialPort=0            \
          -DWITH_liblocation=0               \
          -DBUILD_MARBLE_APPS=1" &&

  default_cmake_build &&

  ln -sf /usr/share/marble/cmake/FindMarble.cmake /usr/share/cmake-`lvu version cmake | cut -c 1-3`/Modules
