
  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 \
          -DCMAKE_INSTALL_SYSCONFDIR=/etc  \
          -DBUILD_MARBLE_EXAMPLES=0        \
          -DBUILD_MARBLE_TESTS=0           \   
          -DMOBILE=0                       \
          -DBUILD_MARBLE_APPS=1" &&

  default_cmake_build
