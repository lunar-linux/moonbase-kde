
  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 \
          -DCMAKE_INSTALL_LIBEXECDIR=lib \
          -DCMAKE_INSTALL_LIBDIR=lib \
          -DBUILD_FlatpakBackend=0 \
          -DBUILD_SnapBackend=0" &&

  default_cmake_build
